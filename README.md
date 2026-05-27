# 1. Matriz: Creación de la matriz con al menos 6 productos de diversas categorías
menu = [
    ["Churrasco de Res", "Platos Fuertes", 45000],
    ["Hamburguesa Clásica", "Platos Fuertes", 25000],
    ["Empanadas de Pipían", "Entradas", 12000],
    ["Ceviche de Mango", "Entradas", 18000],
    ["Brownie con Helado", "Postres", 15000],
    ["Limonada Cerezada", "Bebidas", 9000],
    ["Salmón a la Plancha", "Platos Fuertes", 38000]
]

# 2. Módulos: Función para calcular el precio final
def calcular_precio_final(precio_base, categoria_producto, categoria_objetivo, umbral):
    """
    Calcula el precio final aplicando un 15% de descuento si cumple las condiciones.
    De lo contrario, mantiene el precio base.
    """
    # Lógica de Negocio
    if categoria_producto == categoria_objetivo and precio_base > umbral:
        descuento = precio_base * 0.15
        return precio_base - descuento
    else:
        return precio_base

# Definimos las condiciones de la promoción actual
categoria_promocion = "Platos Fuertes"
umbral_minimo = 30000

# 3. Salida: Mostrar cada producto, su precio base y el precio final
print("=" * 70)
print(f"{'PRODUCTO':<25} | {'CATEGORÍA':<16} | {'PRECIO BASE':<12} | {'PRECIO FINAL'}")
print("=" * 70)

for producto in menu:
    nombre = producto[0]
    categoria = producto[1]
    precio_base = producto[2]
    
    # Llamado a la función para cada elemento de la matriz
    precio_final = calcular_precio_final(precio_base, categoria, categoria_promocion, umbral_minimo)
    
    # Formateo de salida para que se vea como una tabla ordenada
    print(f"{nombre:<25} | {categoria:<16} | ${precio_base:<11,.0f} | ${precio_final:,.0f}")

print("=" * 70)
# fundamentos-programacion-trabajo-final
