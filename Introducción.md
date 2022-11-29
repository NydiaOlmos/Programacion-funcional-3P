# Paradicmas de Programación
> Comparación de los paradigmas estructurada, orientado a objetos y funcional.

Mediante la utilización de los 3 paradigmas de programación vistos en la sesión, haga una calculadora con las siguientes opciones: 
* [1] Suma: (num1+num2) 
* [2] Resta: (num1-num2) 
* [3] Multiplicación: (num1 x num2) 
* [4] División: (num1/num2) 
* [5] Cuadrado: cuadrado(num) 
* [6] Inverso (1/x): inverso(num)
* [7] Cubo: cubo (num)
* [8] Salida

## Programación estructurada 
> Lenguaje C

```
#include <stdio.h>

int suma(int n1, int n2);
int resta(int n1, int n2);
int multi(int n1, int n2);
int divi(int n1, int n2);
int cuadrado(int n1);
int inverso(int n1);
int cubo(int n1);
void menu();
int pedir_valor(char *mensaje);

int main(){
    int opc, n1, n2;
    do{
        do{
            menu();
            scanf("%d", &opc);
            if(opc < 1 || opc > 5){
                printf("Porfavor introduzca una opciÃ³n vÃ¡lida [1...5]\n");
            }
        }while(opc < 1 || opc > 5);
        switch(opc){
            case 1:
                n1 = pedir_valor("Dame el primer nÃºmero para sumar: ");
                n2 = pedir_valor("Dame el segundo nÃºmero para sumar: ");
                printf("Resultado: %d \n\n", suma(n1,n2));
                break;
            case 2:
                n1 = pedir_valor("Dame el primer nÃºmero para restar: ");
                n2 = pedir_valor("Dame el segundo nÃºmero para restar: ");
                printf("Resultado: %d \n\n", resta(n1,n2));
                break;
            case 3:
                n1 = pedir_valor("Dame el primer nÃºmero para multiplicar: ");
                n2 = pedir_valor("Dame el segundo nÃºmero para multiplicar: ");
                printf("Resultado: %d \n\n", multi(n1,n2));
                break;
            case 4:
                n1 = pedir_valor("Dame el primer nÃºmero para dividir: ");
                n2 = pedir_valor("Dame el segundo nÃºmero para dividir: ");
                printf("Resultado: %d \n\n", divi(n1,n2));
                break;
            case 5:
                n1 = pedir_valor("Dame el primer nÃºmero para elevar al cuadrado: ");
                printf("Resultado: %d \n\n", cuadrado(n1));
                break;
            case 6:
                n1 = pedir_valor("Dame el primer nÃºmero para invertir: ");
                printf("Resultado: %d \n\n", inverso(n1));
                break;
            case 7:
                n1 = pedir_valor("Dame el primer nÃºmero para elevar al cubo: ");
                printf("Resultado: %d \n\n", cubo(n1));
                break;
            case 8:
                printf("Gracias por utilizar la calculadora.\n");
                break;
            default:
                break;
        }
    }while (opc != 5);
    printf("Gracias por utilizar la calculadora.\n");
}

int suma(int n1, int n2){
    return n1 + n2;
}
int resta(int n1, int n2){
    return n1 - n2;
}
int multi(int n1, int n2){
    return n1 * n2;
}
int divi(int n1, int n2){
    return n1 / (float)n2;
}
int cuadrado(int n1){
	return n1 * n1;
}
int inverso(int n1){
    return 1 / (float)n1;
}
int cubo(int n1){
	return n1 * n1 * n1;
}
void menu(){
    printf("MenÃº de opciones\n");
    printf("[1] Suma\n");
    printf("[2] Resta\n");
    printf("[3] MultiplicaciÃ³n\n");
    printf("[4] DivisiÃ³n\n");
    printf("[5] Cuadrado\n\n");
    printf("[6] Inverso\n");
    printf("[7] Cubo\n");
    printf("[8] Salir\n");
    printf("Seleccione su opciÃ³n[1-4]: ");
}
int pedir_valor(char *mensaje){
    printf("%s", mensaje);
    int num;
    scanf("%d", &num);
    return num;
}
```

## Programación Orientada a Objetos
> Lenguaje Python
```
from ast import While
from tkinter import Menu


class Objeto_Calculadora:
    def _int_(self, n1, n2):
        self.num1 = n1
        self.num2 = n2

    def Suma(self):
        return self.num1 + self.num2

    def Resta(self):
        return self.num1 - self.num2

    def Multi(self):
        return self.num1 * self.num2

    def Divi(self):
        return self.num1 / self.num2

    def Cuadrado(self):
        return self.num1 * self.num1 

    def Inverso(self):
        return 1 / self.num1

    def Cubo(self):
        return self.num1 * self.num1 * self.num1

    def _del_(self):
        self.num1 = None
        self.num2 = None

def menu():
    print("Menú de opciones")
    print("[1] Suma")
    print("[2] Resta")
    print("[3] Multiplicación")
    print("[4] División")
    print("[5] Cuadrado")
    print("[6] Inverso")
    print("[7] Cubo")
    print("[8] Salir")

def pedir_valores(mensaje):
    num = int(input(mensaje))
    return num

if __name__ == "__main__":
    Mi_Calculadora = Objeto_Calculadora()
    opc = 1
    while opc != 5:
        while opc >= 1 and opc <= 5:
            menu()
            opc = int(input("Seleccione su opcion [1-8]: "))
            if (opc== 1):
                Mi_Calculadora.num1 = pedir_valores("Dame el primer numero para sumar: ")
                Mi_Calculadora.num2 = pedir_valores("Dame el segundo numero para sumar: ")
                print(f"Resultado {Mi_Calculadora.Suma()}\n\n")
            elif (opc== 2):
                Mi_Calculadora.num1 = pedir_valores("Dame el primer numero para restar: ")
                Mi_Calculadora.num2 = pedir_valores("Dame el segundo numero para restar: ")
                print(f"Resultado {Mi_Calculadora.Resta()}\n\n")
            elif (opc== 3):
                Mi_Calculadora.num1 = pedir_valores("Dame el primer numero para multiplicar: ")
                Mi_Calculadora.num2 = pedir_valores("Dame el segundo numero para multiplicar: ")
                print(f"Resultado {Mi_Calculadora.Multi()}\n\n")
            elif (opc== 4):
                Mi_Calculadora.num1 = pedir_valores("Dame el primer numero para dividir: ")
                Mi_Calculadora.num2 = pedir_valores("Dame el segundo numero para dividir: ")
                print(f"Resultado {Mi_Calculadora.Divi()}\n\n")
            elif (opc== 5):
                Mi_Calculadora.num1 = pedir_valores("Dame un numero para elevar al cuadrado: ")
                print(f"Resultado {Mi_Calculadora.Cuadrado()}\n\n")
            elif (opc== 6):
                Mi_Calculadora.num1 = pedir_valores("Dame un numero para invertir: ")
                print(f"Resultado {Mi_Calculadora.Inverso()}\n\n")
            elif (opc== 7):
                Mi_Calculadora.num1 = pedir_valores("Dame un numero para elevar al cubo: ")
                print(f"Resultado {Mi_Calculadora.Cubo()}\n\n")
            elif (opc == 8):
                break
            else:
                pass
        else:
            print("Por favor ingresa un valor valido.")
            opc = 1
    
    print("\nGracias por usar la calculadora \n")
```

## Programación Funcional
> Lenguaje Erlang
```
-module (calculadoraerlang). %El nombre de modulo y archivo debe coincidir 
-export([suma/2, resta/2, multi/2, divi/2]). %Api capa de comunicacion de una interfaz con otra

suma(N1, N2) -> N1 + N2.

resta(N1, N2) ->
    N1 - N2.

multi(N1, N2) ->
    N1 * N2.

divi(N1, N2) ->
    N1 / N2.
cuad(N1) ->
    N1 * N1.
inverso(N1) ->
    1 / N1.
cub(N1) ->
    N1 * N1 * N1.
```
> Lenguaje Elixir 
```
defmodule Calculadora2 do
    def suma(n1, n2), do: n1+n2
    def resta(n1, n2), do: n1-n2
    def multi(n1, n2), do: n1*n2
    def divi(n1, n2), do: n1/n2
    def cuad(n1), do: n1 * n1
    def inverso(n1), do: 1/n1
    def cub(n1), do: n1 * n1 * n1
end
```
