# Guía de desarrollo — Pet Club

## 1. Objetivo

Establecer una forma de trabajo consistente para que los cambios sean comprensibles, revisables y seguros.

## 2. Reglas generales

- No desarrollar directamente sobre `main`.
- No subir contraseñas, tokens, claves ni cadenas de conexión reales.
- No subir carpetas generadas como `node_modules`, `bin` u `obj`.
- Mantener los nombres de variables, clases, métodos y archivos de código en inglés.
- Mantener la documentación del proyecto en español, salvo términos técnicos habituales.
- Hacer cambios pequeños y relacionados con una sola finalidad.
- Probar antes de crear un Pull Request.
- No usar `git push --force` en ramas compartidas.
- No aceptar todos los cambios de un conflicto sin revisarlos.

## 3. Ramas

Se propone el siguiente flujo:

- `main`: versión estable del proyecto.
- `develop`: rama de integración del trabajo terminado y revisado.
- `feature/nombre`: nueva funcionalidad.
- `fix/nombre`: corrección de errores.
- `docs/nombre`: documentación.
- `refactor/nombre`: reorganización interna sin cambiar el comportamiento.
- `chore/nombre`: mantenimiento y configuración.

Las ramas de trabajo se crean desde `develop` y los Pull Requests se dirigen a `develop`. Cuando exista una versión estable, se prepara un Pull Request de `develop` hacia `main`.

Si `develop` todavía no existe, crearla una sola vez desde `main` y publicarla en GitHub.

## 4. Convención de commits

Usar mensajes breves, en inglés y en modo imperativo. Prefijos sugeridos:

- `feat:` nueva funcionalidad.
- `fix:` corrección.
- `docs:` documentación.
- `style:` formato o estilos sin cambio funcional.
- `refactor:` refactorización.
- `test:` pruebas.
- `chore:` mantenimiento.

Ejemplos:
- `docs: add project vision`
- `feat: add pet creation screen`
- `fix: validate inventory quantity`
- `test: add pet needs service tests`

## 5. Flujo para cada tarea

1. Actualizar la rama base.
2. Crear una rama de trabajo.
3. Implementar un cambio acotado.
4. Ejecutar pruebas y revisar el diff.
5. Guardar cambios con commits claros.
6. Publicar la rama en GitHub.
7. Crear Pull Request hacia `develop`.
8. Atender observaciones y actualizar la rama.
9. Esperar aprobación y validaciones.
10. Integrar mediante el método acordado por el equipo.
11. Eliminar la rama de trabajo cuando ya no sea necesaria.

## 6. Calidad mínima antes de integrar

- El proyecto compila.
- Las pruebas relevantes pasan.
- No se agregan secretos.
- No se introducen archivos generados.
- Se revisan los cambios y archivos modificados.
- Se actualiza la documentación si corresponde.
- El Pull Request explica qué cambia y cómo probarlo.

## 7. Seguridad

Los secretos se guardan en variables de entorno o mecanismos seguros de configuración. Los archivos locales con credenciales deben estar excluidos mediante `.gitignore`. Si un secreto se publica accidentalmente, eliminarlo del código no basta: debe revocarse o rotarse.

## 8. Resolución de conflictos

- Leer qué archivos y líneas entraron en conflicto.
- Comparar la intención de ambos cambios.
- Resolver manualmente con el editor de conflictos.
- Ejecutar pruebas.
- Revisar `git diff`.
- Continuar el merge o rebase según el flujo elegido.

No usar `git reset --hard`, `git clean -fd` ni `git push --force` como soluciones improvisadas: pueden eliminar trabajo.
