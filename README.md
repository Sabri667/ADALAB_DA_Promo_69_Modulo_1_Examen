# ✨ TiendaOnline · Gestión de Inventario Profesional

> **Documentación Definitiva** – Sistema completo para la administración de productos, stock y valoración de inventario.

## 🎯 Descripción

**TiendaOnline** es una clase en Python que modela una tienda virtual con un enfoque limpio y extensible. Permite gestionar un inventario de productos (nombre, precio, cantidad) y operar sobre él con métodos intuitivos. Ideal para integrar en sistemas de punto de venta, ejercicios de programación o prototipos comerciales.

## 💎 Atributos

| Atributo         | Tipo               | Propósito                                                                 | Inicialización |
|------------------|--------------------|---------------------------------------------------------------------------|----------------|
| `inventario`     | `list` de `dict`   | Lista de productos. Cada producto: `{'nombre': str, 'precio': float, 'cantidad': int}` | `[]` |
| `ventas_totales` | `float`            | Acumulador de ingresos por ventas (reservado para futuras expansiones)    | `0.0` |

## 🛠️ Métodos

### `agregar_producto(nombre, precio, cantidad)`
Añade un nuevo producto o actualiza el stock si ya existe.

| Parámetro  | Tipo    | Descripción                          |
|------------|---------|--------------------------------------|
| `nombre`   | `str`   | Identificador único del producto     |
| `precio`   | `float` | Precio unitario en dólares ($)         |
| `cantidad` | `int`   | Unidades a añadir (stock inicial o extra) |

### `ver_inventario()`
Muestra en consola el listado completo con formato:


-------------------------ALTERNATIVA----------------------------

# 🛒 TiendaOnline - Sistema de Gestión de Inventario

> **Preliminar** – Documentación inicial de la clase `TiendaOnline` para la gestión de productos, stock y ventas.

## 📌 Descripción

`TiendaOnline` es una clase en Python que modela una tienda virtual. Permite administrar un inventario de productos (cada uno con nombre, precio y cantidad), registrar ventas totales y realizar operaciones básicas como agregar, buscar, actualizar stock, eliminar productos y calcular el valor total del inventario.

## 🧱 Atributos

| Atributo         | Tipo               | Descripción                                                                 | Valor inicial |
|------------------|--------------------|-----------------------------------------------------------------------------|---------------|
| `inventario`     | `list` de `dict`   | Lista de productos. Cada producto: `{'nombre': str, 'precio': float, 'cantidad': int}` | `[]` (vacío) |
| `ventas_totales` | `float`            | Acumulado de ventas realizadas (no se modifica en esta versión preliminar)  | `0.0`         |

## ⚙️ Métodos

### `agregar_producto(nombre, precio, cantidad)`
Agrega un nuevo producto o actualiza la cantidad si ya existe.

- **Parámetros:**
  - `nombre` (str): nombre del producto.
  - `precio` (float): precio unitario.
  - `cantidad` (int): cantidad a añadir (si existe) o stock inicial.

### `ver_inventario()`
Muestra en consola todos los productos con su nombre, precio y cantidad.

### `buscar_producto(nombre)`
Busca un producto por su nombre y muestra sus detalles si existe.

- **Parámetro:** `nombre` (str)

### `actualizar_stock(nombre, cantidad)`
Suma o resta cantidad al stock de un producto existente. Si la cantidad es negativa, reduce stock (sin permitir valores negativos en esta versión).

- **Parámetros:**
  - `nombre` (str)
  - `cantidad` (int): puede ser positivo o negativo.

### `eliminar_producto(nombre)`
Elimina completamente un producto del inventario.

- **Parámetro:** `nombre` (str)

### `calcular_valor_inventario()`
Calcula y muestra el valor total del inventario (suma de `precio * cantidad` para cada producto).

## 💻 Ejemplo de uso

```python
# Crear la tienda
tienda = TiendaOnline()

# Agregar productos
tienda.agregar_producto("Camisa", 20, 40)
tienda.agregar_producto("Pantalón", 30, 30)

# Ver inventario
tienda.ver_inventario()
# Salida esperada:
# Nombre: Camisa, Precio: €20, Cantidad: 40
# Nombre: Pantalón, Precio: €30, Cantidad: 30

# Buscar un producto
tienda.buscar_producto("Camisa")
# Salida: Nombre: Camisa, Precio: €20, Cantidad: 40

# Actualizar stock (vender 2 camisas)
tienda.actualizar_stock("Camisa", -2)

# Eliminar un producto
tienda.eliminar_producto("Pantalón")

# Calcular valor del inventario
tienda.calcular_valor_inventario()
# Ejemplo: si hay 38 camisas a $20 → $760
