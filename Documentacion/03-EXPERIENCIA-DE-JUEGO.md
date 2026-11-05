# 03 — Experiencia y recorrido del jugador

## 1. Primera sesión

1. Pantalla de bienvenida e identidad de Pet Club.
2. Presentación de novedades o eventos (si corresponde).
3. Registro o inicio de sesión.
4. Creación y personalización de la mascota.
5. Introducción breve al mundo.
6. Tutorial guiado con opción de omitir.
7. Primera misión.
8. Entrada al hogar.

## 2. Sesiones siguientes

1. Recuperar la sesión si el usuario sigue autenticado.
2. Cargar la partida desde el servidor.
3. Calcular el tiempo transcurrido desde la última actualización válida.
4. Actualizar las necesidades de la mascota según las reglas del juego.
5. Mostrar el estado de la mascota y permitir continuar.

La actualización de necesidades deberá ser validada por el servidor y no depender del reloj del dispositivo.

## 3. Hogar como centro

Elementos principales:
- Mascota visible e interactiva.
- Selector de habitaciones.
- Acceso al inventario.
- Indicadores de higiene, hambre y diversión.
- Monedas y nivel.
- Acciones de cuidado.
- Modo decoración.
- Acceso al mapa.
- Acceso a misiones, colecciones y perfil.

## 4. Navegación

- **Mapa:** selección de lugares de la ciudad.
- **Escenas:** casa, tiendas y espacios de actividad.
- **Ventanas superpuestas:** inventario, configuración y paneles informativos.
- **Modo decoración:** edición de objetos dentro de la habitación.

## 5. Lugares de la ciudad

### Zona comercial
- Mueblería: muebles clasificados por ambiente.
- Supermercado: alimentos, bebidas y snacks.
- Tienda de artículos: juguetes, regalos, peluches y colecciones.
- Tienda de ropa: prendas, accesorios y disfraces.
- Tienda de construcción: paredes, pisos, puertas, ventanas y habitaciones.
- Estilista: cambios de apariencia de la mascota.
- Tienda de exteriores: plantas, jardinería, pesca y muebles exteriores.
- Boutique: artículos destacados y especiales.
- Tienda misteriosa: cajas sorpresa con reglas transparentes.

### Zona de entretenimiento
- Cafetería.
- Plaza y parque.
- Arcade con minijuegos.
- Estadio con desafíos deportivos.
- Río y muelle de pesca.

## 6. Ciclo principal

```text
Entrar al juego
   ↓
Revisar y cuidar la mascota
   ↓
Decorar o personalizar
   ↓
Explorar la ciudad
   ↓
Comprar / jugar / completar misiones
   ↓
Obtener monedas y objetos
   ↓
Actualizar la casa y las colecciones
   ↺
```

## 7. Principios de interacción

- Las acciones principales deben ser fáciles de encontrar.
- Los controles táctiles deben tener un tamaño cómodo.
- La decoración debe permitir seleccionar, mover y confirmar objetos.
- Las compras deben mostrar precio y confirmación antes de descontar monedas.
- El jugador debe recibir feedback claro cuando una acción se guarda o falla.
- Las animaciones deben acompañar la interacción sin bloquear controles.
