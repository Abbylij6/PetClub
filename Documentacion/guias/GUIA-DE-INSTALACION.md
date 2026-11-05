# Guía de instalación y preparación del entorno

## 1. Requisitos iniciales

Instalar las herramientas necesarias para trabajar en el proyecto:

- Git.
- Visual Studio Code.
- Node.js LTS compatible con la versión de Vite que se utilice.
- .NET SDK 8 o la versión que defina el proyecto al iniciar el backend.
- SQL Server (cuando se implemente persistencia).
- Una herramienta para administrar SQL Server, por ejemplo SSMS o Azure Data Studio si está disponible.
- Navegador actualizado.

Las versiones exactas se fijarán al crear los proyectos frontend y backend. No instalar herramientas adicionales antes de necesitarlas.

## 2. Verificar instalaciones

En PowerShell:

```powershell
git --version
node --version
npm --version
dotnet --version
```

Si un comando no se reconoce, revisar que la herramienta esté instalada y que su ruta esté disponible en PATH. Reiniciar la terminal después de instalar.

## 3. Clonar el repositorio

```powershell
git clone https://github.com/Abbylij6/PetClub.git
cd PetClub
```

## 4. Abrir en Visual Studio Code

Desde la carpeta del proyecto:

```powershell
code .
```

Si `code` no se reconoce, abrir VS Code y seleccionar **File → Open Folder**.

## 5. Preparación del frontend (cuando comience esa etapa)

La creación de React + Vite se realizará dentro de `frontend/`. Los comandos definitivos se agregarán cuando se decida la versión de Node y la configuración del proyecto.

## 6. Preparación del backend (cuando comience esa etapa)

El backend se creará dentro de `backend/` con ASP.NET Core Web API. Se documentarán SDK, paquetes NuGet, cadena de conexión de desarrollo y comandos de migración al iniciar esa etapa.

## 7. Base de datos

La cadena de conexión local se guardará en configuración de desarrollo excluida de Git o en variables de entorno. Nunca publicar contraseñas ni credenciales reales en archivos versionados.

## 8. Antes de comenzar a trabajar

```powershell
git status
git branch --show-current
git pull origin develop
```

Si todavía no existe `develop`, seguir la sección correspondiente de la Guía de Git y GitHub para crearla una sola vez.
