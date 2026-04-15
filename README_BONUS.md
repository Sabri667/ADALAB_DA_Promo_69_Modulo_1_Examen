# 🛍️ TiendaOnLine – Sistema de Gestión de Ventas e Inventario

> Una clase Python robusta para gestionar inventario, clientes, compras interactivas y registro de ventas. Ideal para integrar en sistemas de punto de venta, e-commerce o como base para proyectos de aprendizaje.

## ✨ Características principales

- **Gestión completa de inventario**: agregar, actualizar stock, eliminar, buscar y calcular valor total.
- **Clientes**: registro, historial de compras y visualización con tabla formateada (usando `tabulate`).
- **Compra interactiva**: el usuario navega por el inventario, arma un carrito, confirma y procesa el pago.
- **Registro programático de compras**: permite registrar una compra desde un carrito externo (útil para integraciones o pruebas).
- **Procesamiento de pagos**: convierte montos con formato regional (ej. `1.234,56` o `1,234.56`) y calcula cambio.
- **Código limpio y extensible**: métodos privados para evitar duplicación y facilitar el mantenimiento.

## 📦 Estructura de la clase

```python
class TiendaOnLine:
    def __init__(self, nombre):                     # nombre de la tienda
    def agregar_producto(self, nombre, precio, cantidad)
    def agregar_listado_productos(self, listado_productos)
    def ver_inventario(self)
    def buscar_producto(self, nombre)
    def actualizar_stock(self, nombre, cantidad)
    def eliminar_producto(self, nombre)
    def calcular_valor_inventario(self)

    # Clientes
    def agregar_cliente(self, nombre, correo)
    def ver_clientes(self)                          # usa tabulate para tabla bonita
    def ver_compras_cliente(self, nombre_cliente)

    # Compras
    def realizar_compra(self, nombre_cliente)       # modo interactivo (consola)
    def registrar_compra(self, nombre_cliente, carrito)  # compra directa con carrito externo
    def _procesar_compra(self, nombre_cliente, carrito)  # método privado común

    # Pagos
    @staticmethod
    def parse_moneda(cadena)                        # convierte strings con comas/puntos a float
    def procesar_pago(self)                         # calcula cambio