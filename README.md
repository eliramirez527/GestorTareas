# GestorTareas
```python
from datetime import datetime

tareas = []

# Función para agregar una nueva tarea
def agregar_tarea():
    descripcion = input("Ingrese la descripción de la tarea: ")
    fecha_limite = input("Ingrese la fecha límite (formato YYYY-MM-DD): ")
    tarea = {
        "descripcion": descripcion,
        "fecha_limite": datetime.strptime(fecha_limite, "%Y-%m-%d"),
        "estado": "pendiente",
    }
    tareas.append(tarea)

# Función para listar todas las tareas
def listar_tareas():
    for idx, tarea in enumerate(tareas):
        print(f"ID: {idx}")
        print(f"Descripción: {tarea['descripcion']}")
        print(f"Fecha límite: {tarea['fecha_limite'].strftime('%Y-%m-%d')}")
        print(f"Estado: {tarea['estado']}")
        print("---")

# Función para completar una tarea
def completar_tarea():
    id_tarea = int(input("Ingrese el ID de la tarea a completar: "))
    if 0 <= id_tarea < len(tareas):
        tareas[id_tarea]["estado"] = "completada"
    else:
        print("ID de tarea no válido.")

# Función para eliminar una tarea
def eliminar_tarea():
    id_tarea = int(input("Ingrese el ID de la tarea a eliminar: "))
    if 0 <= id_tarea < len(tareas):
        del tareas[id_tarea]
    else:
        print("ID de tarea no válido.")

# Menú principal
while True:
    print("*Sistema de gestión de tareas*")
    print("1. Agregar tarea")
    print("2. Listar tareas")
    print("3. Completar tarea")
    print("4. Eliminar tarea")
    print("5. Salir")

    opcion = input("Seleccione una opción: ")

    if opcion == '1':
        agregar_tarea()
    elif opcion == '2':
        listar_tareas()
    elif opcion == '3':
        completar_tarea()
    elif opcion == '4':
        eliminar_tarea()
    elif opcion == '5':
        break
    else:
        print("Opción no válida.")

print("¡Hasta luego!.")
```
