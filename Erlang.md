# Erlang

## Conceptos básicos 
Para acceder el Shell desde la terminal escribimos "erl".
### Funciones

| Función | Descripción |
| ----------- | ----------- |
| help() | Imprime las funciones disponibles del Shell.  |
| h() | Imprime la historia de los comandos capturados.  |
| v(N) | Retorna el valor calculado en la línea N.  |
| cd(dir) | Cambia el directorio actual (el directorio debe estar entre comillas). |
| Is(dir) | Imprime el listado del directorio actual. |
| pwd() | mprime el directorio de trabajo actual. |
| q(), init:stop() | Salida del Shell. |
| i() | Imprime la información acerca del sistema en ejecución. |
| memory() | Imprime información de la memoria utilizada. |

### Operadores
**Aritméticos**
| Operador | Nombre | Ejemplo |
| ----------- | ----------- | ----------- |
| + | Suma | 5 + 3 = 8 |
| - | Resta | 5 - 2 = 3 |
| * | Multiplicación | 4 * 5 = 20 |
| / | División | 10 / 2 = 5.0 |
| rem | Remanente | 10 rem 2  = 0 |
| div | División entera | 10 div 2 = 5 |

**Racionales**
| Operador | Nombre | Ejemplo | Resultado |
| ----------- | ----------- | ----------- | ----------- |
| ==, =:= | Igual | 3 == 3.0  3 =:= 3.0 | true false |
| /= | Distinto | 3 /= 4 | true |
| < | Menor | 3 < 5 | true |
| =< | Menor o igual | 2 =< 3 | true |
| > | Mayor | 3 > 2 | true |
| >= | Mayor o igual | 3 >= 3 | true |
  
**Lógicos**
 
| p | q | p and q | p or q | p xor q |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| true | true | true | true | false |
| true | false | false | true | true |
| false | true | false | true | true |
| false | false | false | false | false |

| p | not p |
| ----------- | ----------- |
| true | false |
| false | true |

*Operadores a nivel de bits*
| p | q | p band q | p bor q | p bxor q |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| 1 | 1 | 2#1 band 2#1  1 | 2#1 bor 2#1  1 | 2#1 bxor 2#1  0 |
| 1 | 0 | 2#1 band 2#0  0 | 2#1 bor 2#0  1 | 2#1 bxor 2#0  1 |
| 0 | 1 | 2#0 band 2#1  0 | 2#0 bor 2#1  1 | 2#0 bxor 2#1  1 |
| 0 | 0 | 2#0 band 2#0  0 | 2#0 bor 2#0  0 | 2#0 bxor 2#0  0 |

### Tipos de datos

* **Entero**
```
1>5.
5
2>1_000_000 * 3.
3000000
3>$A * $a.
6305
4>is_integer(5).
true
```

* **Flotante**
```
1>3.14.
3.14
2>1_000_000.325.
1000000.325
3>iis_float(3.1416).
true
```

* **Notación científica**
```
1> 9.81256352e-4.
9.81256352e-4
2> 9.81256352e4.
98125.6352
```

* **Números base N(2 => N <= 36)**
```
1> 2#101010101. 
341 
2> 3#123123123. 
 1: syntax error before: 3123123 
3> 3#121212. 
455 
4> 8#1234567. 
342391 
5> 16#FFFFFF. 
16777215 
6> 36#ZFWQX. 
59528841 
7> 37#ZFWQX. 
 1: illegal base '37' 
```
 
 ### Atoms
- Literalmente el nombre es el contenido. 
- Inician con una letra minúscula.
- Puede llevar el caracter _ o @.
- Puede estar encerrada entre comillas simples (’) si inicia con una letra mayúscula o tienen otros caracteres alfanuméricos distintos a los mencionados.
```
1> ok.
ok
2> phone_number.
phone_number
3> 'Lunes'.
'Lunes'
4> is_atom('Lunes').
true
```

### Booleano
```
1> true.
true
2> is_atom(true).
true
3> is_atom(false).
true
```

### Strings 
• Son un tipo específico de lista\
• Es una lista homogénea (caracteres)\
• La palabra Hola por ejemplo puede representarse como:
* “Hola”
* [72,111,108,97]
```
1> is_list("Hola"). 
true 
2> [72,111,108,97]. 
"Hola" 
3> "Hola"=[72,111,108,97]. 
"Hola" 
```
**Concatenación**
```
1> Msg = "Hola " ++ "Mundo". 
"Hola Mundo" 
2> "Hola " ++ Msg2 = "Hola Mundo". 
"Hola Mundo" 
3> Msg2. 
"Mundo" 
4> Msg. 
"Hola Mundo"
```

### Variables
* Iniciain con letra mayúscula.
* Son inmutables, por lo que es necesario primero borrar la variable para darle otro valor.
```
1> Pi = 3.14159.
3.14159
2> Pi = 3.1416.
** exception error: no match of right hand side value 3.1416
3> f(Pi).
ok
4> Pi = 3.1416.
3.1416
```

## Datos complejos

### Listas
> Estructura de datos con información heterogénea

**Agregar elementos**
```
1> [1,2,3,4,5,6] ++ [7,8,9,10].
[1,2,3,4,5,6,7,8,9,10]
2> [1,2,"Luis",3.1416,true] ++ [false, "Maria", 9.81].
[1,2,"Luis",3.1416,true,false,"Maria",9.81]
```

**Eliminar elementos**
```
1> [1,2,3,4,5,6] -- [1,5].
[2,3,4,6]
2> [1,2,"Luis",3.1416,true] -- ["Luis"].
[1,2,3.1416,true]
3> [1,2,3,4,5,6,7,8,9,10] -- [2,4,6,8,10]. 
[1,3,5,7,9] 
```

**Listas como cadenas**
```
1> Msg = "Hola".
"Hola"
2> Msg2 = [Msg|" Mundo"].
["Hola",32,77,117,110,100,111]
3> io:format("~s ~n",[Msg]).
Hola
ok
4> Msg2.
["Hola",32,77,117,110,100,111]
5> io:format("~s ~n",[Msg2]).
Hola Mundo 
ok
[1,3,5,7,9]
```

**Acceder a los elementos**
	
```
1> [H|T] = [1,2,3,4,5].
[1,2,3,4,5]
2> H.
1
3> T.
[2,3,4,5]
4> [H1,H2|T2]=[1,2,3,4,5].
[1,2,3,4,5]
5> H1.
1
6> H2.
2
7> T2.
[3,4,5]
```

**Listas binarias**
> Permite almacenar cadenas de caracteres (byte)
```
1> <<"Hola">>. 
<<"Hola">> 
2> <<"H","o","l","a">>. 
<<"Hola">> 
3> <<72,111,$l,$a>>. 
<<"Hola">>
4> <<H:1/binary,T/binary>> = <<"Hola">>. 
<<"Hola">> 
5> H. 
<<"H">> 
6> T. 
<<"ola">>
7> A = <<"Hola">>. 
<<"Hola">> 
8> B = <<" Mundo">>. 
<<" Mundo">> 
9> C = <<A/binary,B/binary>>. 
<<"Hola Mundo">>
10> byte_size(A). 
4
11> byte_size(B). 
6 
12> byte_size(C). 
10
```

### Tuplas
> Se utiliza en casos donde es más fácil acceder al elemento por un identificador conocido que por un índice, el cual podría no conocerse.
```
1>{{"López","González","Luis"},{1995,10,15},"México"}. 
{{"López","González","Luis"}, {1995,10,15}, [77,130,120,105,99,111]}
2> {Uno, Dos} = {1,2}. 
{1,2} 
3> Uno. 
1 
4> Dos. 
2 
5> {Tres, _} = {3,4}. 
{3,4}
```
| Función | Ejemplo | Descripción |
| ----------- | ----------- | ----------- |
| erlang:setelement/3  | erlang:setelement(2,{'A','b','C'},'B').   {'A','B','C'}  | Cambia un elemento de la tupla |
| erlang:append_element/2 |erlang:append_element({1,2,3},4).   {1,2,3,4} | Agrega un elemento al final de la tupla | 
| erlang:element/2  | erlang:element(2,{'a','b','c'}).   b | Obtiene un elemento mediante su índice |
| erlang:delete_element/2 | erlang:delete_element(3,{1,2,3,4}).   {1,2,4} | Elimina un elemento mediante el índice |

### Lista de propiedades 
> Lista de tuplas
> Se usa la librería proplists
```
1>Registro = [{ap_paterno,"López"},{ap_materno,"González"},{nombre,"Luis"}]. 
[{ap_paterno,"López"}, {ap_materno,"González"}, {nombre,"Luis"}] 
2> proplists:get_value(nombre,Registro). 
"Luis"
```

### Mapas
* Son una estructura de datos.
* Cada elemento se almacena con un índice o clave con su respectivo valor.
* El índice puede ser de cualquier tipo.
* El contenido o valor también puede ser de cualquier tipo.
```
1> Map = #{nombre => "Alejandro"}. 
#{nombre => "Alejandro"}
```

|  | Agregar y cambiar datos | Cambios sobre un índice ya existente | Extraer valores | Eliminar una clave | Buscar una clave | ¿Es un mapa? | Cantidad de claves | Obtener claves |
| ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- |
| Función | Map2 = Map#{apellido =>"Perez"}. | Map3 = Map2#{nombre :="Alexander"}. |  #{nombre := Nombre} = Map3. Nombre. | aps:remove(nombre, Map3) | maps:get(nombre,Map3). | is_map(Map3). | map_size(Map3). | maps:keys(Map3). |
| Retorna | #{apellido => "Perez",nombre => "Alejandro"} | #{apellido => "Perez",nombre => "Alexander"} | #{apellido => "Perez",nombre => "Alexander"}  "Alexander" | #{apellido => "Perez"} | "Alexander" | true | 2 | [apellido,nombre] |

## Conversión de datos
* list_to_integer
```
1> list_to_integer("101"). 
101 
2> list_to_integer("101", 2). 
5 
3> list_to_integer("101", 8). 
65 
4> list_to_integer("101", 16). 
257 
5> list_to_integer("101", 36). 
1297 
6> list_to_integer("101", 37). 
** exception error: bad argument 
     in function  list_to_integer/2 
        called as list_to_integer("101",37)
```
* atom_to_list/1, atom_to_binary/2
* binary_to_atom/2, binary_to_float/1, binary_to_integer/1-2, binary_to_list/1-3
* list_to_atom/1, list_to_binary/1, list_to_float/1, list_to_integer/1-2, list_to_pid/1 
* integer_to_binary/1-2, integer_to_list/1-2, float_to_binary/1-2, float_to_list/1-2 
* list_to_tuple/1, tuple_to_list/1 

## Impresión en pantalla
> io.format
```
1> io:format("Hola Mundo"). 
Hola Mundook 
2> io:format("Hola Mundo\n"). 
Hola Mundo 
ok 
3> io:format("Hola Mundo~n"). 
Hola Mundo 
ok 
```

**C**

* Representa un caracter que será reemplazado por el valor pasado en la l
ista como segundo parámetro 
* antes de la letra puede llevar un par de números separados por un punto
(.) 
* El primer número indica el tamaño del campo 
* Puede llevar un signo positivo o negativo que indica la justificación i
zquierda o derecha 
* El segundo número indica las veces que se va a repetir el valor
```
1> io:format("[~c]~n",[$a]). 
[a] 
ok 
2> io:format("[~5c]~n",[$a]). 
[aaaaa] 
ok 
3> io:format("[~5.2c]~n",[$a]). 
[   aa] 
ok 
4> io:format("[~-5.2c]~n",[$a]). 
[aa   ] 
ok
```

**E**
> Notación científica 
```
1> io:format("[~7.2e]", [10.1]). 
[ 1.0e+1]oK
```
f
> Formato de punto fijo 
```
2> io:format("[~7.2f]", [10.1]). 
[  10.10]ok
```
