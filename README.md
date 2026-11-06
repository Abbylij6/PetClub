# Pet Club

Juego de mascotas virtuales multiplataforma. El jugador podrá crear una criatura fantástica original, cuidarla, personalizar su apariencia, decorar su hogar, explorar una ciudad, participar en actividades y coleccionar objetos.

> **Estado:** planificación y documentación. El desarrollo de funcionalidades todavía no comenzó.

## Objetivos

- Crear una experiencia de mascota virtual accesible desde navegador y, a futuro, dispositivos móviles.
- Ofrecer personalización, decoración, exploración, actividades y progresión.
- Guardar el progreso en la nube para continuar desde distintos dispositivos.
- Construir un universo, criaturas, ilustraciones y recursos originales.

## Funcionalidades previstas

- Creación y personalización de una especie original de criatura fantástica.
- Necesidades de higiene, hambre y diversión.
- Casa personalizable con habitaciones, muebles y objetos.
- Ciudad con tiendas, cafetería, plaza, arcade, estadio y zona de pesca.
- Inventario, monedas, misiones, logros, colecciones y eventos.
- Funciones sociales en una etapa futura.

## Tecnologías previstas

| Área | Tecnología |
|---|---|
| Frontend | JavaScript, React, Vite |
| Motor 2D | PixiJS |
| Estilos | CSS |
| Backend | C#, ASP.NET Core Web API |
| Persistencia | SQL Server, Entity Framework Core |
| Tiempo real (futuro) | SignalR |
| Empaquetado móvil (a evaluar) | Capacitor |
| Diseño | Figma |
| Gestión | Git, GitHub y Jira |

La selección tecnológica podrá ajustarse durante el diseño técnico.

## Arquitectura conceptual

```text
Jugador
  ↓
Frontend (React + PixiJS)
  ↓ solicitudes HTTP
Backend (ASP.NET Core Web API)
  ↓
Base de datos (SQL Server)
```

El frontend presenta la experiencia y captura las acciones del jugador. El backend valida reglas, permisos, compras y progresión. La base de datos conserva cuentas y partidas.

## Documentación

- [Visión del proyecto](Documentacion/01-VISION-DEL-PROYECTO.md)
- [Requisitos funcionales y no funcionales](Documentacion/02-REQUISITOS.md)
- [Experiencia y recorrido del jugador](Documentacion/03-EXPERIENCIA-DE-JUEGO.md)
- [Diseño visual](Documentacion/04-DISENO-VISUAL.md)
- [Arquitectura técnica](Documentacion/05-ARQUITECTURA.md)
- [Modelo de datos inicial](Documentacion/06-BASE-DE-DATOS.md)
- [Roadmap](Documentacion/07-ROADMAP.md)
- [Registro de decisiones](Documentacion/08-REGISTRO-DE-DECISIONES.md)
- [Guías de desarrollo](Documentacion/guias/README.md)

## Organización del repositorio

```text
PetClub/
├── README.md
├── .gitignore
└── docs/
    ├── 01-VISION-DEL-PROYECTO.md
    ├── 02-REQUISITOS.md
    ├── 03-EXPERIENCIA-DE-JUEGO.md
    ├── 04-DISENO-VISUAL.md
    ├── 05-ARQUITECTURA.md
    ├── 06-BASE-DE-DATOS.md
    ├── 07-ROADMAP.md
    ├── 08-REGISTRO-DE-DECISIONES.md
    └── guias/
        ├── README.md
        ├── GUIA-DE-DESARROLLO.md
        ├── GUIA-DE-GIT-Y-GITHUB.md
        └── GUIA-DE-INSTALACION.md
```

## Cómo contribuir

Antes de modificar archivos, leer las guías de `docs/guias/`. No trabajar directamente sobre `main`: crear una rama para cada cambio y proponer su integración mediante Pull Request.

## Principios del proyecto

1. La experiencia principal debe poder disfrutarse sin realizar pagos.
2. La moneda especial no debe bloquear la progresión esencial.
3. La ausencia del jugador no debe causar daños irreversibles a la mascota.
4. Las funciones sociales se incorporarán después de estabilizar el núcleo del juego.
5. Se priorizarán accesibilidad, rendimiento, seguridad y guardado confiable.
6. Las referencias a juegos existentes sirven como inspiración de género; no se copiarán marcas, personajes, ilustraciones, interfaces ni recursos protegidos.
