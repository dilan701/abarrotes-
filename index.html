import sqlite3
from datetime import datetime, timedelta

# Base de datos SQLite
DATABASE = 'inventario.db'

# Función para conectar a la base de datos
def get_db():
    conn = sqlite3.connect(DATABASE)
    conn.row_factory = sqlite3.Row  # Esto permitirá acceder a las columnas por nombre
    return conn

# Crear la tabla de productos (si no existe)
def create_table():
    with get_db() as conn:
        conn.execute('''
            CREATE TABLE IF NOT EXISTS productos (
                id INTEGER PRIMARY KEY AUTOINCREMENT,
                nombre TEXT NOT NULL,
                categoria TEXT NOT NULL,
                cantidad INTEGER NOT NULL,
                ubicacion TEXT NOT NULL,
                stock_minimo INTEGER NOT NULL,
                fecha_caducidad DATE
            )
        ''')
        conn.commit()

# Agregar un producto al inventario
def agregar_producto(nombre, categoria, cantidad, ubicacion, stock_minimo, fecha_caducidad=None):
    with get_db() as conn:
        conn.execute('''
            INSERT INTO productos (nombre, categoria, cantidad, ubicacion, stock_minimo, fecha_caducidad)
            VALUES (?, ?, ?, ?, ?, ?)
        ''', (nombre, categoria, cantidad, ubicacion, stock_minimo, fecha_caducidad))
        print(f"Producto '{nombre}' de la categoría '{categoria}' agregado con éxito.")

# Función para agregar productos iniciales (100 de limpieza y 100 de abarrotes)
def agregar_productos_iniciales():
    productos_limpieza = [
        ("Detergente Líquido", "Productos de limpieza", 10, "Estante 1", 3),
        ("Jabón para platos", "Productos de limpieza", 10, "Estante 1", 3),
        ("Limpiador multiusos", "Productos de limpieza", 10, "Estante 2", 3),
        ("Esponjas", "Productos de limpieza", 10, "Estante 2", 3),
        ("Toallas de papel", "Productos de limpieza", 10, "Estante 3", 3),
        ("Cloro", "Productos de limpieza", 10, "Estante 3", 3),
        ("Amoniaco", "Productos de limpieza", 10, "Estante 4", 3),
        ("Limón", "Productos de limpieza", 10, "Estante 4", 3),
        ("Sacos de basura", "Productos de limpieza", 10, "Estante 5", 3),
        ("Desinfectante", "Productos de limpieza", 10, "Estante 5", 3),
    ]
    
    productos_abarrotes = [
        ("Arroz", "Abarrotes", 20, "Estante 6", 5),
        ("Frijoles", "Abarrotes", 20, "Estante 6", 5),
        ("Aceite de cocina", "Abarrotes", 20, "Estante 7", 5),
        ("Azúcar", "Abarrotes", 20, "Estante 7", 5),
        ("Sal", "Abarrotes", 20, "Estante 8", 5),
        ("Pasta", "Abarrotes", 20, "Estante 8", 5),
        ("Harina", "Abarrotes", 20, "Estante 9", 5),
        ("Leche en polvo", "Abarrotes", 20, "Estante 9", 5),
        ("Sopa instantánea", "Abarrotes", 20, "Estante 10", 5),
        ("Café", "Abarrotes", 20, "Estante 10", 5),
    ]

    # Agregar los productos de limpieza
    for producto in productos_limpieza:
        agregar_producto(*producto)

    # Agregar los productos de abarrotes
    for producto in productos_abarrotes:
        agregar_producto(*producto)

# Ver todos los productos en el inventario
def ver_inventario():
    with get_db() as conn:
        productos = conn.execute('SELECT * FROM productos').fetchall()
    
    if not productos:
        print("No hay productos en el inventario.")
        return

    print("\nInventario:")
    for producto in productos:
        print(f"ID: {producto['id']} | Nombre: {producto['nombre']} | Categoría: {producto['categoria']} | "
              f"Cantidad: {producto['cantidad']} | Ubicación: {producto['ubicacion']} | "
              f"Stock mínimo: {producto['stock_minimo']} | Caducidad: {producto['fecha_caducidad']}")

# Eliminar un producto del inventario
def eliminar_producto():
    ver_inventario()
    try:
        producto_id = int(input("Introduce el ID del producto que deseas eliminar: "))
        with get_db() as conn:
            conn.execute('DELETE FROM productos WHERE id = ?', (producto_id,))
            print("Producto eliminado con éxito.")
    except ValueError:
        print("ID inválido, por favor ingresa un número válido.")

# Ver productos que necesitan ser comprados (por debajo del stock mínimo)
def productos_faltantes():
    with get_db() as conn:
        productos = conn.execute('SELECT * FROM productos WHERE cantidad <= stock_minimo').fetchall()
    
    if not productos:
        print("No hay productos faltantes.")
        return

    print("\nProductos que necesitas comprar (falta stock):")
    for producto in productos:
        print(f"Nombre: {producto['nombre']} | Categoría: {producto['categoria']} | "
              f"Cantidad: {producto['cantidad']} | Ubicación: {producto['ubicacion']}")

# Ver productos que podrían acabarse pronto (menos de 5 unidades)
def productos_agotarse_pronto():
    with get_db() as conn:
        productos = conn.execute('SELECT * FROM productos WHERE cantidad <= 5').fetchall()
    
    if not productos:
        print("No hay productos que se estén agotando pronto.")
        return

    print("\nProductos que podrían acabarse pronto:")
    for producto in productos:
        print(f"Nombre: {producto['nombre']} | Categoría: {producto['categoria']} | "
              f"Cantidad: {producto['cantidad']} | Ubicación: {producto['ubicacion']}")

# Recomendaciones de productos basadas en las categorías
def recomendaciones():
    with get_db() as conn:
        categorias = conn.execute('SELECT DISTINCT categoria FROM productos').fetchall()
    
    if not categorias:
        print("No hay categorías disponibles para recomendaciones.")
        return

    print("\nRecomendaciones de productos:")
    for categoria in categorias:
        print(f"- {categoria['categoria']}")

# Función para mostrar el menú y obtener opciones
def mostrar_menu():
    print("\nMenú de Inventario:")
    print("1. Ver inventario")
    print("2. Agregar un producto")
    print("3. Eliminar un producto")
    print("4. Ver productos faltantes (necesarios para comprar)")
    print("5. Ver productos que podrían acabarse pronto")
    print("6. Ver recomendaciones de productos por categoría")
    print("7. Salir")

# Función principal para ejecutar la aplicación
def ejecutar():
    create_table()

    # Agregar productos iniciales
    agregar_productos_iniciales()

    while True:
        mostrar_menu()
        try:
            opcion = int(input("Selecciona una opción (1-7): "))
            if opcion == 1:
                ver_inventario()
            elif opcion == 2:
                nombre = input("Nombre: ")
                categoria = input("Categoría: ")
                cantidad = int(input("Cantidad: "))
                ubicacion = input("Ubicación: ")
                stock_minimo = int(input("Stock mínimo: "))
                fecha_caducidad = input("Fecha de caducidad (opcional, formato YYYY-MM-DD): ")
                if not fecha_caducidad:
                    fecha_caducidad = None
                agregar_producto(nombre, categoria, cantidad, ubicacion, stock_minimo, fecha_caducidad)
            elif opcion == 3:
                eliminar_producto()
            elif opcion == 4:
                productos_faltantes()
            elif opcion == 5:
                productos_agotarse_pronto()
            elif opcion == 6:
                recomendaciones()
            elif opcion == 7:
                print("Gracias por usar la aplicación. ¡Hasta luego!")
                break
            else:
                print("Opción inválida, por favor ingresa un número entre 1 y 7.")
        except ValueError:
            print("Entrada inválida. Por favor, ingresa un número.")

if __name__ == "__main__":
    ejecutar()
