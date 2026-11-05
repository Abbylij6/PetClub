# 02 — Requisitos funcionales y no funcionales

## 1. Alcance

Este documento registra requisitos iniciales. Se refinarán durante el análisis y se vincularán con historias de usuario y tareas en Jira. Los requisitos marcados como futuros no forman parte del primer prototipo.

## 2. Requisitos funcionales

|  ID   |           Requisito                                                       | Prioridad inicial |
|-------|---------------------------------------------------------------------------|-------------------|
| RF-01 | El sistema permitirá registrar una cuenta con correo y contraseña.        | Alta              |
| RF-02 | El sistema permitirá iniciar y cerrar sesión.                             | Alta              |
| RF-03 | El jugador podrá crear una mascota de la especie original.                | Alta              |
| RF-04 | El jugador podrá personalizar rasgos y colores con vista previa.          | Alta              |
| RF-05 | El sistema guardará la mascota asociada a la cuenta.                      | Alta              |
| RF-06 | La mascota tendrá necesidades de higiene, hambre y diversión.             | Alta              |
| RF-07 | El jugador podrá realizar acciones de cuidado.                            | Alta              |
| RF-08 | El jugador podrá visualizar su casa y una habitación inicial.             | Alta              |
| RF-09 | El jugador podrá colocar, mover y retirar muebles de su inventario.       | Alta              |
| RF-10 | El sistema guardará la distribución de los objetos de la habitación.      | Alta              |
| RF-11 | El jugador podrá consultar su inventario.                                 | Media             |
| RF-12 | El jugador podrá recorrer un mapa y acceder a lugares habilitados.        | Media             |
| RF-13 | El jugador podrá comprar objetos con monedas si cumple las condiciones.   | Media             |
| RF-14 | El sistema validará saldo y disponibilidad antes de confirmar una compra. | Alta              |
| RF-15 | El jugador podrá completar misiones y recibir recompensas.                | Media             |
| RF-16 | El jugador podrá consultar colecciones y objetos obtenidos.               | Media             |
| RF-17 | El jugador podrá consultar eventos y novedades.                           | Baja              |
| RF-18 | El jugador podrá visitar casas de amigos.                                 | Futuro            |
| RF-19 | El jugador podrá enviar regalos a amigos.                                 | Futuro            |

## 3. Requisitos no funcionales

| ID | Requisito |
|---|---|
| RNF-01 | La interfaz deberá adaptarse a distintos tamaños de pantalla. |
| RNF-02 | Las contraseñas nunca se almacenarán en texto plano. |
| RNF-03 | El servidor validará las operaciones sensibles; el cliente no será fuente de verdad para monedas o compras. |
| RNF-04 | El progreso deberá persistir en una base de datos y poder recuperarse luego de cerrar sesión. |
| RNF-05 | El sistema deberá manejar errores de red sin perder silenciosamente el progreso confirmado. |
| RNF-06 | Las operaciones críticas deberán validar autenticación y autorización. |
| RNF-07 | La interfaz deberá mantener una navegación clara y consistente. |
| RNF-08 | Las escenas 2D deberán optimizarse para equipos y móviles compatibles. |
| RNF-09 | El código deberá organizarse por responsabilidades y contar con documentación. |
| RNF-10 | Las fechas y tiempos de juego deberán calcularse de forma consistente en servidor. |
| RNF-11 | Se deberán evitar pérdidas y duplicaciones de compras ante reintentos. |
| RNF-12 | Se deberán contemplar accesibilidad básica: contraste, textos legibles y controles identificables. |

## 4. Reglas de negocio iniciales

- Una cuenta tendrá una partida principal en la primera versión; se revisará si se necesitan múltiples mascotas o partidas.
- Cada mascota tendrá tres necesidades principales: higiene, hambre y diversión.
- Las necesidades podrán disminuir con el tiempo, pero existirán límites para evitar daño irreversible.
- El saldo de monedas se validará en el backend.
- Una compra confirmada deberá descontar moneda y entregar el objeto como una operación consistente.
- Los objetos adquiridos se registrarán en el inventario.
- Los artículos especiales no serán obligatorios para completar el progreso principal.
- Las funciones sociales se aplazarán hasta contar con controles de privacidad y seguridad.

## 5. Criterios de aceptación

Un requisito se considerará terminado cuando:
1. Cumpla su descripción y reglas de negocio.
2. Tenga validaciones de entrada y manejo de errores.
3. Haya sido probado en los escenarios principales y alternativos.
4. No rompa funcionalidades existentes.
5. La documentación relacionada esté actualizada.
6. El cambio haya sido revisado e integrado mediante Pull Request.
