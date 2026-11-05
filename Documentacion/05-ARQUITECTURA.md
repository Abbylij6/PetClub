# 05 — Arquitectura técnica

## 1. Objetivo

Separar presentación, lógica de negocio y persistencia para que el juego pueda evolucionar sin concentrar todas las responsabilidades en una sola aplicación.

## 2. Arquitectura conceptual

```text
Navegador / dispositivo
        |
        v
Frontend: React + Vite
        |
        +---- UI, navegación, formularios
        |
        +---- PixiJS: escenas 2D, sprites, animaciones
        |
        | HTTP / JSON
        v
Backend: ASP.NET Core Web API
        |
        +---- Autenticación y autorización
        +---- Reglas de juego
        +---- Mascotas y necesidades
        +---- Inventario, compras y monedas
        +---- Misiones y progreso
        |
        v
Persistencia: Entity Framework Core
        |
        v
SQL Server
```

## 3. Responsabilidades

### Frontend
- Presentar pantallas, menús y formularios.
- Gestionar navegación y estado visual.
- Renderizar escenas 2D con PixiJS.
- Enviar solicitudes al backend.
- Mostrar resultados y errores.
- No decidir por sí mismo saldos, premios ni validez de compras.

### Backend
- Validar datos recibidos.
- Autenticar usuarios y autorizar operaciones.
- Aplicar reglas de negocio.
- Calcular resultados confiables.
- Controlar monedas, compras e inventario.
- Exponer endpoints documentados.

### Base de datos
- Persistir cuentas, mascotas, habitaciones, objetos y progreso.
- Mantener relaciones e integridad referencial.
- Registrar operaciones que requieran trazabilidad.

## 4. Tecnologías previstas

- React y Vite.
- PixiJS.
- C# y ASP.NET Core Web API.
- Entity Framework Core.
- SQL Server.
- SignalR como opción futura para funciones en tiempo real.
- Capacitor como opción futura para empaquetado móvil.

## 5. Organización futura del código

```text
PetClub/
├── docs/
├── frontend/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   ├── features/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── game/
│   │   └── styles/
│   └── package.json
└── backend/
    ├── PetClub.sln
    └── src/
        ├── PetClub.Api/
        ├── PetClub.Application/
        ├── PetClub.Domain/
        └── PetClub.Infrastructure/
```

Esta estructura es una propuesta inicial y podrá ajustarse al tamaño real del proyecto.

## 6. Comunicación

El frontend consumirá endpoints HTTP que intercambian JSON. El backend será responsable de validar y persistir cambios. Las operaciones de compra y recompensa deberán ser atómicas y protegidas contra reintentos duplicados.

## 7. Seguridad básica

- Contraseñas protegidas mediante mecanismos seguros de hashing.
- Tokens y sesiones tratados de forma segura.
- Validación de permisos en servidor.
- Secretos y cadenas de conexión fuera del repositorio.
- Validación de datos en frontend y backend.
- Limitación de solicitudes sensibles cuando sea necesario.
- No confiar en valores enviados por el cliente para monedas, precios o premios.

## 8. Decisiones pendientes

- Estrategia de autenticación y renovación de sesión.
- Modelo de guardado y sincronización.
- Frecuencia de actualización de necesidades.
- Estrategia de carga de assets y caché.
- Hosting, backups y despliegue.
- Si el backend se organizará como monolito modular o en varios servicios.

No se implementarán servicios distribuidos antes de que exista una necesidad real.
