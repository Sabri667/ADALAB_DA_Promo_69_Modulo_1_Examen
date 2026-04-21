# 🛒 TiendaOnLine - Sistema de Gestión de Inventario y Ventas

Una clase Python robusta y profesional para gestionar una tienda online con control de inventario, registro de clientes, procesamiento de compras y cálculo de ventas. Ideal para proyectos de portafolio, demostraciones de programación orientada a objetos (POO) y aplicaciones de backend simples.

---

## ✨ Características principales

- **Gestión de inventario**  
  Agregar, actualizar, eliminar y buscar productos.  
  Control de stock con validaciones de tipos y rangos.

- **Carga masiva de productos**  
  Agregar listados completos mediante listas de diccionarios.

- **Clientes**  
  Registro con validación de correo electrónico mediante expresiones regulares (regex).  
  Historial de compras por cliente.

- **Carrito de compras interactivo**  
  Experiencia paso a paso: selección de productos, cantidades, resumen y confirmación.  
  Limpieza automática de productos que desaparecen del inventario durante la sesión.

- **Procesamiento de pagos**  
  Cálculo de cambio con soporte para formatos monetarios locales (ej: `1.234,56` o `1,234.56`).

- **Métodos auxiliares privados**  
  Código refactorizado y reutilizable (`_buscar_producto`, `_limpiar_carrito`, `_procesar_compra`).

- **Reportes**  
  Ver inventario, listado de clientes con número de compras, valor total del inventario, ventas acumuladas y compras de un cliente específico.

---

## 📦 Dependencias

- Python 3.7+
- Librería `tabulate` (para mostrar clientes en formato tabla).  
  Instalación: `pip install tabulate`

El resto del código utiliza solo la biblioteca estándar (`re`).

---

## 🚀 Instalación y uso

1. Clona o descarga el archivo que contiene la clase `TiendaOnLine`.
2. Asegúrate de tener Python instalado.
3. Opcional: instala `tabulate` para una mejor visualización de clientes.
4. Importa la clase en tu script o interactúa directamente.

```python
from tienda_online import TiendaOnLine

# Crear una tienda
mi_tienda = TiendaOnLine("Mi Farmacia")

# Agregar productos individualmente
mi_tienda.agregar_producto("Vitamina C", 12.50, 150)

# O mediante lote
lote = [
    {"nombre": "Gel antibacterial", "precio": 8.99, "cantidad": 300},
    {"nombre": "Termómetro digital", "precio": 15.90, "cantidad": 80}
]
mi_tienda.agregar_listado_productos(lote)

# Registrar cliente
mi_tienda.agregar_cliente("Luisa Trujillo", "luisa@example.com")

# Realizar una compra interactiva
mi_tienda.realizar_compra("Luisa Trujillo")

# Ver reportes
mi_tienda.ver_inventario()
mi_tienda.calcular_ventas_totales()
mi_tienda.ver_compras_cliente("Luisa Trujillo")