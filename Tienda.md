# tienda-Pycharm.io
# programa amb menú que permet tenir una llista d'elements i afegir, eliminar i modificar elements

# variable llista amb tota la informació del meu programa
llista = []

# Funció mostrar_menu mostra les opcions a l'usuari
# li pregunta quina opció vol escollir i retorna el número escollit
tienda = print("♢♢♧♥♤☘Tienda MOLINA♢♢♧♥♤☘")
def mostrar_menu():
    print("♢♢♧♥♤☘♢♢♧♥♤☘ MENU ♢♢♧♥♤☘♢♢♧♥♤☘")
    print("1.- Agregar producto.")
    print("2.- Eliminar producto.")
    print("3.- Agregar precio.")
    print("4.- Modificar nombre del producto.")
    print("5.- Modificar precio del producto.")
    print("6.- Elementos de la lista.")
    print("7.- Modificar cantidad de productos.")
    print("8.- cantidad total de productos.")
    print("9.- Salir.")
    print("♢♢♧♥♤☘♢♢♧♥♤☘♢♢♧♥♤☘♢♢♧♥♤☘")
    opcio = int(input("Selecciona una opcion: "))
    return opcio

opcio = 0


def afegir_element():
    element = input("Introduce el nombre del producto: ")
    for i in llista:
        if i [0] == element:
            print("El producto ya esta.")
            return
    llista.append([element, 0.0, 0])


def eliminar_element():
    element = input("Introduce el nombre del producto a eliminar: ")
    for i in llista:
        if i [0] == element:
            llista.remove(i)
            return


def modificar_element():
    element_primero = input("Introduce el nombre del producto a modificar: ")
    element_nou = input("Introduce el nuevo nombre del producto: ")
    for i in llista:
        if i [0] == element_primero:
            i [0] = element_nou
            return


def agregar_precio():
    nom_producto = input("introduce el nombre del producto: ")
    precio = float(input("introduce el precio del producto: "))
    for i in llista:
        if i [0] == nom_producto:
            i [1] = precio
            return


def modif_precio():
    nom_producte = input("introduce el nombre del producto: ")
    precio_now = float(input("introduce el nuevo precio del producto: "))
    for i in llista:
        if i [0] == nom_producte:
            i [1] = precio_now
            return


def modif_cantidad():
    cant_producto = input("nombre del producto para agregar cantidad: ")
    now_cantidad = int(input("introduce la cantidad: "))
    for i in llista:
        if i [0] == cant_producto:
            i [2] = now_cantidad
            return


def mostra_elements():
    if not llista:
        print("La tienda está vacía")
        return

    for nombre, precio, cantidad in llista:
        print(f"{nombre} - Precio: ${precio} - Cantidad: {cantidad}")


def canti_modifi():
    cantidad = input("introduce el producto: ")
    now_canti = int(input("introduce la nueva cantidad: "))
    for i in llista:
        if i [0] ==cantidad:
            i [2] = now_canti


def total_produc():
    for i in llista:
        produ = i [0]
        valor = i [1]
        cantidad = i [2]
        tod =  valor * cantidad
        print(f"el valor total es: {tod} - {produ}")


while True:

    try:
        opcio = mostrar_menu()
    except:
        opcio = 0

    match opcio:
        case 1:
            afegir_element()
        case 2:
            eliminar_element()
        case 3:
            agregar_precio()
        case 4:
            modificar_element()
        case 5:
            modif_precio()
        case 6:
            mostra_elements()
        case 7:
            canti_modifi()
        case 8:
            total_produc()
        case 9:
            print("gracias por usar este programa.")
            break
        case _:
            print("La opció seleccionada és incorrecta.")
