#Ejercicio 1
letra = input("Introduce una letra: ")
letra = letra.lower()
print("Letra en minúscula:", letra)

#Ejercicio 2
letra = input("Introduce una letra: ")

if letra.isalpha():
    letra = letra.lower()
    print("Letra en minúscula:", letra)
else:
    print("Entrada no válida, no es una letra.")

#Ejercicio 3
intentos_invalidos = 0
while True:
    letra = input("Introduce una letra: ")
    if letra.isalpha():
        letra = letra.lower()
        print("Letra en minúscula:", letra)
        break
    else:
        intentos_invalidos += 1
        print("Entrada no válida, no es una letra. Intentos inválidos:", intentos_invalidos)

#Ejercicio 4
def validar_letra():
    intentos_invalidos = 0
    while True:
        letra = input("Introduce una letra: ")
        if letra.isalpha():
            letra = letra.lower()
            return letra, intentos_invalidos
        else:
            intentos_invalidos += 1
            print("Entrada no válida, no es una letra. Intentos inválidos:", intentos_invalidos)

letra_valida, intentos = validar_letra()
print("Letra válida en minúscula:", letra_valida)
print("Número de intentos inválidos:", intentos)

#Ejercicio 5
def menu():
    print("Menú de Opciones:")
    print("1. Opción 1")
    print("2. Opción 2")
    print("3. Salir")
    opcion = input("Selecciona una opción: ")
    return opcion

#Ejercicio 6
while True:
    opcion = menu()
    if opcion == '1':
        print("Has seleccionado Opción 1")
    elif opcion == '2':
        print("Has seleccionado Opción 2")
    elif opcion == '3':
        print("Saliendo del programa...")
        break
    else:
        print("Opción no válida. Inténtalo de nuevo.")

#Ejercicio 7
def validar_letra_sin_espacios():
    intentos_invalidos = 0
    while True:
        letra = input("Introduce una letra: ")
        if letra.isalpha() and not letra.isspace():
            letra = letra.lower()
            return letra, intentos_invalidos
        else:
            intentos_invalidos += 1
            print("Entrada no válida, no debe contener espacios ni ser un número. Intentos inválidos:", intentos_invalidos)

letra_valida, intentos = validar_letra_sin_espacios()
print("Letra válida en minúscula:", letra_valida)
print("Número de intentos inválidos:", intentos)

#Ejercicio 8
def validar_letras_separadas():
    intentos_invalidos = 0
    while True:
        entrada = input("Introduce varias letras separadas por comas: ")
        letras = entrada.split(',')
        if all(letra.isalpha() for letra in letras) and len(letras) == len(set(letras)):
            letras = [letra.lower() for letra in letras]
            return letras, intentos_invalidos
        else:
            intentos_invalidos += 1
            print("Entrada no válida, asegúrate de que todas sean letras y no estén repetidas. Intentos inválidos:", intentos_invalidos)

letras_validas, intentos = validar_letras_separadas()
print("Letras válidas en minúscula:", letras_validas)
print("Número de intentos inválidos:", intentos)

#ejercicio 9
def validar_letra_con_intentos(max_intentos=5):
    intentos_invalidos = 0
    while intentos_invalidos < max_intentos:
        letra = input("Introduce una letra: ")
        if letra.isalpha():
            letra = letra.lower()
            return letra, intentos_invalidos
        else:
            intentos_invalidos += 1
            print("Entrada no válida, no es una letra. Intentos inválidos:", intentos_invalidos)
    return None, intentos_invalidos

letra_valida, intentos = validar_letra_con_intentos()
if letra_valida:
    print("Letra válida en minúscula:", letra_valida)
else:
    print("Número máximo de intentos alcanzado. No se proporcionó una letra válida.")
print("Número de intentos inválidos:", intentos)

#Ejercicio 10
def validar_letra_con_mensajes():
    intentos_invalidos = 0
    while True:
        letra = input("Introduce una letra: ")
        if len(letra) != 1:
            print("Error: Debes ingresar solo una letra.")
        elif not letra.isalpha():
            print("Error: La entrada debe ser una letra del alfabeto.")
        elif letra.isspace():
            print("Error: La entrada no debe contener espacios.")
        else:
            letra = letra.lower()
            return letra, intentos_invalidos
        intentos_invalidos += 1
        print("Intentos inválidos:", intentos_invalidos)

letra_valida, intentos = validar_letra_con_mensajes()
print("Letra válida en minúscula:", letra_valida)
print("Número de intentos inválidos:", intentos)
