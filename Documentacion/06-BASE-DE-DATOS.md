# 06 — Modelo inicial de base de datos

## 1. Objetivo

Definir las entidades principales y sus relaciones antes de crear migraciones. Este modelo es conceptual: los nombres, tipos, restricciones y cardinalidades se revisarán durante el diseño técnico.

## 2. Entidades propuestas

| Entidad | Responsabilidad |
|---|---|
| User | Cuenta y datos de autenticación del jugador. |
| Pet | Mascota asociada al jugador. |
| PetAppearance | Rasgos y opciones de apariencia. |
| PetNeed | Valores actuales de higiene, hambre y diversión. |
| House | Hogar del jugador. |
| Room | Habitaciones de una casa. |
| FurnitureItem | Definición de un mueble u objeto decorativo. |
| RoomItem | Instancia de un objeto colocada en una habitación y su posición. |
| InventoryItem | Objetos que posee el jugador. |
| CurrencyBalance | Saldos de monedas por tipo. |
| Transaction | Registro de compras, recompensas y movimientos de moneda. |
| Store | Tiendas y catálogos. |
| Product | Artículos ofrecidos en una tienda. |
| Mission | Definición de una misión. |
| PlayerMission | Estado de una misión para un jugador. |
| Collection | Definición de una colección. |
| CollectionEntry | Objetos que forman parte de una colección. |
| PlayerCollectionItem | Objetos de colección obtenidos por un jugador. |

## 3. Relaciones principales

- User 1 a 1 Pet (primera versión; sujeto a decisión).
- User 1 a 1 House.
- House 1 a muchos Room.
- Room 1 a muchos RoomItem.
- FurnitureItem 1 a muchos RoomItem.
- User 1 a muchos InventoryItem.
- User 1 a muchos Transaction.
- Store 1 a muchos Product.
- User 1 a muchos PlayerMission.
- Mission 1 a muchos PlayerMission.

## 4. Reglas de integridad

- Las entidades dependientes deberán tener claves foráneas válidas.
- El saldo no podrá modificarse sin una operación validada.
- Una compra deberá registrar el movimiento de moneda y la entrega del objeto de forma consistente.
- Las cantidades de inventario no podrán ser negativas.
- Los objetos colocados deberán pertenecer al inventario o contar con una regla válida de colocación.
- Los valores de necesidades deberán respetar sus límites.
- Las operaciones críticas deberán registrar fecha y datos suficientes para auditoría.

## 5. Campos comunes a evaluar

- Identificador.
- Fecha de creación.
- Fecha de última modificación.
- Estado o indicador de activo cuando corresponda.

No todas las tablas necesitan todos estos campos; se decidirá según su responsabilidad.

## 6. Diagrama conceptual inicial

```text
User ── Pet ── PetNeed
  |
  +── House ── Room ── RoomItem ── FurnitureItem
  |
  +── InventoryItem
  |
  +── CurrencyBalance
  |
  +── Transaction
  |
  +── PlayerMission ── Mission
```

## 7. Pendientes de análisis

- Si una cuenta podrá tener varias mascotas.
- Si las necesidades se almacenan como valores actuales o se derivan de eventos y marcas de tiempo.
- Cómo se representarán artículos apilables y no apilables.
- Cómo se gestionarán objetos únicos, duplicados y artículos temporales.
- Qué historial de transacciones se conservará.
- Cómo se versionarán los datos de partidas.
