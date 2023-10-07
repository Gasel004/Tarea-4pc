C++
#1
#2
#include <iostream>

using namespace std;

int main() {
    int filas, columnas;

    cout << "Ingrese el número de filas de la matriz: ";
    cin >> filas;

    cout << "Ingrese el número de columnas de la matriz: ";
    cin >> columnas;

    int** matriz = new int*[filas];
    for (int i = 0; i < filas; ++i) {
        matriz[i] = new int[columnas];
    }

    for (int i = 0; i < filas; ++i) {
        for (int j = 0; j < columnas; ++j) {
            std::cout << "Ingrese el valor para la posición [" << i << "][" << j << "]: ";
            std::cin >> matriz[i][j];
        }
    }

    int numeroMayor = matriz[0][0];
    for (int i = 0; i < filas; ++i) {
        for (int j = 0; j < columnas; ++j) {
            if (matriz[i][j] > numeroMayor) {
                numeroMayor = matriz[i][j];
            }
        }
    }

    int suma = 0;
    for (int i = 0; i < filas; ++i) {
        for (int j = 0; j < columnas; ++j) {
            suma += matriz[i][j];
        }
    }
    double promedio = static_cast<double>(suma) / (filas * columnas);

    cout << "   ***Bienvenido***   "<< endl;
    cout << "Número mayor en la matriz: " << numeroMayor << endl;
    cout << "La matriz ingresada es:" << endl;
    for (int i = 0; i < filas; ++i) {
        for (int j = 0; j < columnas; ++j) {
            cout << matriz[i][j] << " ";
        }
        cout << endl;
    }
    cout << "El promedio de la matriz es: " << promedio << endl;

    for (int i = 0; i < filas; ++i) {
        delete[] matriz[i];
    }
    delete[] matriz;

    return 0;
}

//(-_-)
#3
#include <iostream>
#include <vector>

using namespace std;
vector<int> son_perfectos(int limite) {
   vector<int> numeros_perfectos;
    
    for (int numero = 1; numero < limite; ++numero) {
        int suma_divisores = 0;
        for (int divisor = 1; divisor < numero; ++divisor) {
            if (numero % divisor == 0) {
                suma_divisores += divisor;
            }
        }
        
        if (suma_divisores == numero) {
            numeros_perfectos.push_back(numero);
        }
    }
    
    return numeros_perfectos;
}

int main() {
    int limite = 1000;
    vector<int> numeros_perfectos = son_perfectos(limite);

    cout << "Números perfectos existentes en el rango del 1 al " << limite << " son:" << endl;
    for (int numero_perfecto : numeros_perfectos) {
        cout << numero_perfecto << endl;
    }

    return 0;
}
#4
#include <iostream>
#include <vector>
 
 using namespace std;

int main () {
    int tamaño;
    cout << "Ingrese el tamaño de su lista de numeros: ";
    cin >> tamaño;

    vector <int> arreglo(tamaño);

    for (int i = 0; i < tamaño; ++i) {
        cout << "Ingrese el valor numero " << i << ": ";
        cin >> arreglo[i];
    }

    double promedio = 0.0;
    for (int i = 0; i < tamaño; ++i) {
        promedio += arreglo[i];

    }
    promedio /= tamaño;

    cout <<"La lista creada es: " << endl;
    for (int i = 0; i < tamaño; ++i ) {
        cout << arreglo[i] << ", ";

    } 
    cout << "\nEl promedio de la lista de numero es: " << promedio << endl;
    cout <<"\Espero haberte ayudado ( ͡° ͜ʖ ͡°)" << endl;
    return 0;
}

*python*
#1
# Q.20 por estaciorse hasta 3 horas 
# Q0.50 Por cada hora extra que permanezca en el parqueo
# el tiempo maximo que pueden parquearse durante 24 horas es de Q.10 es decir (20 horas)
# Se supone que nadie se estaciona mas de 24 horas a la vez
# Crear un programa que registre e imprima el total de pagar de los 3 clientes de ayer
# Creando y usando la funcion calcularCargos determinar el precio que paga cada cliente 
# Siendo las horas ingresadas por el usuario
# y mostrar los totales en forma tabul

#creamos nuestra función principal
def main():
#Establecemos los precios que conocemos en nuestras variables
    costo_base = 2.00
    extra_por_hora = 0.50 
    maximo_por_dia = 10.00
    horas_totales_por_dia = 24

#Inicializamos nuestra variable en donde estaran el numero de clientes 
    total_recibos = 0

#Almacenamos los datos de los clientes
    clientes = []

#Creamos un ciclo for para preguntar al usuario las horas de estacionamiento del cliente correspondiente.
    for cliente in range (1,4):

        horas_estacionamiento= float(input(f"Ingrese las horas de estacionamiento del cliente No.{cliente}:"))

#Si el total de horas es igual o menor a 3 se le cobrara el costo base correspondiente
        if horas_estacionamiento <= 3:
            cargo = costo_base
        
#Si se pasa el estandar se le sumara lo correspondiente 0.50 por hora extra
        else: 
            cargo = costo_base + (horas_estacionamiento - 3 ) * extra_por_hora

#Si sobre pasa el maximo por dia se le cobrara lo maximo correspondiente, pero segun el enunciado eso no pasara.       
        if cargo > maximo_por_dia:
            cargo = maximo_por_dia
        
        clientes.append((cliente, horas_estacionamiento, cargo))  # Almacena los datos del cliente en la lista
        total_recibos += cargo
    
    # Imprimimos los resultados en un formato tabular
    print("\nResumen de cargos por estacionamiento:")
    print("Cliente\tHoras\tCargo")
    for cliente, horas, cargo in clientes:
        print(f"{cliente}\t{horas}\t${cargo:.2f}")
    
#Imprimimos nuestro total de recibos igualmente de forma de tabla.
    print(f"\nTotal de los recibos de ayer: ${total_recibos:.2f}")

if __name__ == "__main__":
    main()

#Casi 1 hora buscando 2 errores y eran ":" y "una letra" :(

#2
#escriba una aplicación que le pregunte al usuario cuántas filas y cuántas columnas de una
#matriz quiere ingresar, luego que reciba todos los valores, seguido debe imprimir el número mayor de
#la matriz y los datos de la matriz ingresada y el promedio de la matriz
#Creaamos nuestro ciclo for para que el usuario ingrese los numeros de su matriz 1 por 1
def hacer_matriz(w, e):
    matriz = []
    for i in range(w):
        fila = []
        for j in range(e):
            numero = int(input(f"Ingrese el número en la posición ({i+1}, {j+1}): "))
            fila.append(numero)
        matriz.append(fila)
    return matriz

#Creamos el proceso por el cual encontraremos el mayor de los numeros ingresados por el usario, esto con un for
#Iniciando el ciclo 0 y luego el ciclo ira recibiendo numero por numero de la matriz para ver cual es el mayor
def hallar_mayor(matriz):
    mayor = matriz[0][0]
    for fila in matriz:
        for numero in fila:
            if numero > mayor:
                mayor = numero
#Retornamos el mayor que seria el numero mayor de todos los ingresados.
    return mayor


#Hacemos casi el mismo proceso con la diferencia que con este ciclo calcularemos el promedio de los numeros ingresado
#EL promedio se obtiene sumando todos n numeros por m cantidad de numeros ingresados por el usuario.
def es_promedio(matriz):
    total = 0
    cantidad_numeros = 0
    for fila in matriz:
        for numero in fila:
            total += numero
            cantidad_numeros += 1
    promedio = total / cantidad_numeros if cantidad_numeros > 0 else 0
#Retornamos el promedio:
    return promedio


#Pedimos al usuario ingresar la cantidad de filas y columas, de acuerdo a su gusto o necesidad;
filas = int(input("Ingrese la cantidad de filas para su matriz: "))
columnas = int(input("Ingrese la cantidad de columnas para su matriz: "))

#Representamos nuestra matriz con las distancias de ingresadas por el usuario.
matriz = hacer_matriz(filas, columnas)

#Imprimimos la matriz que se creo mediante los datos del usuario.
print("La matriz creada es:")
for fila in matriz:
    print(fila)

#Impimios el promedio que se calculo en un ciclo anterior.
promedio = es_promedio(matriz)
print(f"El promedio de los números ingresados es: {promedio}")

#Imprimimos el mayor con el proceso anteriormenten realizado.
mayor = hallar_mayor(matriz)
print(f"El mayo de los numeros ingresados por el usuario es: {mayor}")

print("Espero aberte ayudado :)")


#Me tomo mas de lo planeado hacerlo (*_*)

#3
def es_perfecto(rango):
    numeros_perfectos = []
    
    for numero in rango:
        suma_divisores = sum(divisor for divisor in range(1, numero) if numero % divisor == 0)
        
        if suma_divisores == numero:
            numeros_perfectos.append(numero)
    
    return numeros_perfectos


rango = range(1, 1000)
numeros_perfectos = es_perfecto(rango)

print("Números perfectos en el rango del 1 al 1000:")
for numero_perfecto in numeros_perfectos:
    print(numero_perfecto)


#De seguir probando con numeros mas grandes me hubiera explota la PC, ಠ⁠_⁠ಠ

#4
#escriba una aplicación que determine la mediana y el promedio de una lista (arreglo) de
#números, donde el usuario indique la cantidad de e ingrese dichos números. Es decir el debe decir cuáto
#será la longitud del arreglo e ingresará cada número.

#creamos nuestra funcion es_promedio con la que calcularemos el promedio sumando los numeros ingresados,
#y dividiendo por la cantidad total de los numeros que ingreso el usuario.
def es_promedio(lista):
#Verificamos la distancia de la lista que será ingresada por el usuario.
    if len(lista) == 0:
        return 0    
#Se suman todos los numeros.
    suma = sum(lista)
#Se devuelve el total de la suma y se divide por el numero de datos total registrado en "lista"
    return suma / len(lista)


#Tuve que copiar como encontrar la mediana :(
def calcular_mediana(lista):
    lista_ordenada = sorted(lista)
    e = len(lista_ordenada)

    if e % 2 == 1:

        mediana = lista_ordenada [e // 2]
    else:
        mediana = (lista_ordenada [e // 2 - 1] + lista_ordenada[e // 2]) /2.0
      
    return mediana

#Creamos nuestra función princiál que sera la encargada de la creación y almacenamiento de nuestra lista.
def main():
    print("   ***Bienvenido***   ")
    e = int(input("Ingrese la cantidad de números que desea ingresar: "))
#Creamos una lista vacia en donde almacenaremos los numeros que el usuario ingresara.    
    numeros = []

#Creamos un for para que repita el ciclo de pedir los numeros al usuario según la distancia que el indico al inicio.
    for i in range(e):
        numero = float(input(f"Ingrese el número {i + 1} : "))
        numeros.append(numero)

#Guardamos el promedio en "promedio" y mediana en "mediana"
    promedio = es_promedio(numeros)
    mediana = calcular_mediana(numeros)
#Imprimos nuestra lista guardada anteriormente en "numeros".
    print(f"La lista creada es: {numeros}")

#Imprimimos la mediana
    print(f"La mediana es: {mediana}")
#imprimimos el promedio.
    print(f"El promedio de los números ingresados es: {promedio}")

    print ("Espero haberte ayudado")
    print ("(+_+)")

#Este bloque no entiendo como funciona :(, pero sí lo borro no funcion el programa jajaja
if __name__ == "__main__":
    main()
