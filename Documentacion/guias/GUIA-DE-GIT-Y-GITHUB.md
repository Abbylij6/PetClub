# Guía de Git y GitHub

## 1. Conceptos básicos

- **Git:** herramienta de control de versiones que registra cambios.
- **GitHub:** plataforma que aloja repositorios Git y permite colaborar.
- **Repositorio:** carpeta del proyecto cuyo historial controla Git.
- **Commit:** registro de un conjunto de cambios.
- **Branch (rama):** línea de trabajo independiente.
- **Remote:** repositorio remoto, normalmente llamado `origin`.
- **Pull Request (PR):** propuesta para integrar una rama en otra después de revisión.

## 2. Instalar y configurar Git

Comprobar instalación:

```powershell
git --version
```

Configurar identidad (usar el nombre y correo que correspondan a la cuenta):

```powershell
git config --global user.name "Tu Nombre"
git config --global user.email "tu-correo@example.com"
```

Ver configuración:

```powershell
git config --global --list
```

## 3. Clonar el repositorio

Clonar una sola vez en la computadora:

```powershell
git clone https://github.com/Abbylij6/PetClub.git
cd PetClub
```

`clone` descarga el repositorio y crea la carpeta local. No es necesario volver a clonar para cada sesión.

## 4. Revisar el estado

```powershell
git status
```

Muestra la rama actual y los archivos modificados, nuevos o preparados para commit.

Ver ramas locales y remotas:

```powershell
git branch
git branch -a
```

Ver remotos:

```powershell
git remote -v
```

## 5. Crear y cambiar de rama

Actualizar primero la rama de integración:

```powershell
git switch develop
git pull origin develop
```

Crear una rama nueva desde `develop`:

```powershell
git switch -c docs/complete-project-guides
```

Cambiar a una rama existente:

```powershell
git switch develop
```

Publicar por primera vez una rama nueva:

```powershell
git push -u origin docs/complete-project-guides
```

`-u` establece el seguimiento entre la rama local y la remota. En los siguientes envíos bastará con `git push`.

Si `develop` todavía no existe, crearla una sola vez desde `main`:

```powershell
git switch main
git pull origin main
git switch -c develop
git push -u origin develop
```

## 6. Guardar cambios

Ver qué cambió:

```powershell
git status
git diff
```

Preparar todos los cambios del directorio actual:

```powershell
git add .
```

O preparar un archivo específico:

```powershell
git add docs/README.md
```

Crear un commit:

```powershell
git commit -m "docs: add development guides"
```

Un commit guarda una versión en el historial local. Todavía no la sube a GitHub.

## 7. Subir cambios (push)

```powershell
git push
```

Envía los commits locales a la rama remota vinculada. Si es la primera publicación de una rama, usar `git push -u origin nombre-de-rama`.

## 8. Descargar cambios (pull)

```powershell
git pull origin develop
```

Descarga e integra los cambios de `develop` en la rama local actual. Antes de ejecutarlo, comprobar `git status` y guardar o apartar los cambios locales para evitar conflictos.

Para actualizar `main`:

```powershell
git switch main
git pull origin main
```

Importante: `git pull` afecta la rama en la que estás parado. Comprobar siempre `git branch --show-current`.

## 9. Actualizar la rama de trabajo con develop

Antes de terminar una tarea, integrar los cambios recientes de `develop` en tu rama:

```powershell
git switch develop
git pull origin develop
git switch feature/my-feature
git merge develop
```

Resolver cualquier conflicto y volver a probar. En equipos que acuerden usar rebase, documentar ese flujo y no mezclar criterios sin coordinación.

## 10. Crear un Pull Request

1. Subir la rama con `git push`.
2. Abrir el repositorio en GitHub.
3. Seleccionar **Compare & pull request** o ir a **Pull requests → New pull request**.
4. Elegir como base `develop`.
5. Elegir como compare la rama de trabajo.
6. Escribir un título claro y describir los cambios.
7. Indicar cómo probarlos y adjuntar capturas si ayudan.
8. Solicitar revisión.
9. Corregir observaciones y volver a subir commits a la misma rama.
10. Una vez aprobado, integrar el PR según las reglas del proyecto.

No crear PR hacia `main` para trabajo cotidiano. `main` se reserva para versiones estables.

## 11. Plantilla para Pull Request

```markdown
## Descripción
¿Qué se cambió y por qué?

## Cambios realizados
- 
- 

## Cómo probar
1.
2.

## Verificaciones
- [ ] Compila correctamente.
- [ ] Pruebas relevantes ejecutadas.
- [ ] No se agregaron secretos.
- [ ] Documentación actualizada.

## Capturas (si corresponde)
```

## 12. Resolver conflictos

Un conflicto ocurre cuando Git no puede combinar automáticamente cambios sobre una misma parte de un archivo.

Pasos:
1. Ejecutar `git status` para identificar archivos en conflicto.
2. Abrirlos en VS Code.
3. Revisar las secciones marcadas `<<<<<<<`, `=======` y `>>>>>>>`.
4. Elegir o combinar manualmente los cambios correctos.
5. Eliminar las marcas de conflicto.
6. Guardar y probar el proyecto.
7. Marcar como resuelto:

```powershell
git add ruta/del/archivo
```

8. Si se estaba realizando un merge:

```powershell
git commit
```

No elegir automáticamente “Accept Current” o “Accept Incoming” sin entender qué contiene cada versión.

## 13. Comandos útiles

```powershell
# Rama actual
git branch --show-current

# Historial resumido
git log --oneline --graph --decorate -10

# Ver diferencias sin preparar
git diff

# Ver diferencias preparadas
git diff --staged

# Descargar referencias remotas sin integrar
git fetch origin

# Ver estado
git status
```

## 14. Errores que debemos evitar

- Trabajar directamente en `main`.
- Hacer `git add .` sin revisar antes qué archivos se incluirán.
- Subir `node_modules`, `bin`, `obj`, archivos de compilación o secretos.
- Hacer commits enormes con cambios no relacionados.
- Hacer `git pull` sin saber en qué rama estamos.
- Crear Pull Requests hacia la rama equivocada.
- Usar `git push --force` en ramas compartidas.
- Borrar archivos o descartar cambios sin comprobar si contienen trabajo útil.

## 15. Flujo resumido de una tarea

```powershell
git switch develop
git pull origin develop
git switch -c feature/pet-creation
# realizar cambios
git status
git diff
git add .
git commit -m "feat: add pet creation"
git push -u origin feature/pet-creation
# Crear Pull Request en GitHub: feature/pet-creation -> develop
```
