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
 
*And*
| p | q | p and q |
| ----------- | ----------- | ----------- |
| true | true | true |
| true | false | false |
| false | true | false |
| false | false | false |

*Or*
| p | q | p or q |
| ----------- | ----------- | ----------- |
| true | true | true |
| true | false | true |
| false | true | true |
| false | false | false |

*Not*
| p | not p |
| ----------- | ----------- |
| true | false |
| false | true |

*Xor*
| p | q | p xor q |
| ----------- | ----------- | ----------- |
| true | true | false |
| true | false | true |
| false | true | true |
| false | false | false |

*Operadores a nivel de bits*
| p | q | p band q | p bor q | p bxor q |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| 1 | 1 | 2#1 band 2#1  1 | 2#1 bor 2#1  1 | 2#1 bxor 2#1  0 |
| 1 | 0 | 2#1 band 2#0  0 | 2#1 bor 2#0  1 | 2#1 bxor 2#0  1 |
| 0 | 1 | 2#0 band 2#1  0 | 2#0 bor 2#1  1 | 2#0 bxor 2#1  1 |
| 0 | 0 | 2#0 band 2#0  0 | 2#0 bor 2#0  0 | 2#0 bxor 2#0  0 |

### Tipos de datos

* **Entero**

1>5.\
5\
2>1_000_000 * 3.\
3000000\
3>$A * $a.\
6305\
4>is_integer(5).\
true

* **Flotante**

1>3.14.\
3.14\
2>1_000_000.325.\
1000000.325\
3>iis_float(3.1416).\
true

* **Notación científica**

1> 9.81256352e-4.\
9.81256352e-4\
2> 9.81256352e4.\
98125.6352\

* **Números base N(2 => N <= 36)**

1> 2#101010101. \
341 \
2> 3#123123123. \
 1: syntax error before: 3123123 \
3> 3#121212. \
455 \
4> 8#1234567. \
342391 \
5> 16#FFFFFF. \
16777215 \
6> 36#ZFWQX. \
59528841 \
7> 37#ZFWQX. \
 1: illegal base '37' 
 
 ### Atoms
- Literalmente el nombre es el contenido. 
- Inician con una letra minúscula.
- Puede llevar el caracter _ o @.
- Puede estar encerrada entre comillas simples (’) si inicia con una letra mayúscula o tienen otros caracteres alfanuméricos distintos a los mencionados.

1> ok.\
ok\
2> phone_number.\
phone_number\
3> 'Lunes'.\
'Lunes'\
4> 'numero de telefono'.\
'numero de telefono'\
5> is_atom('Lunes').\
true\
6> is_atom('numero de telefono').\
true 

### Booleano

1> true.\
true\
2> is_atom(true).\
true\
3> is_atom(false).\
true\

### Strings 
• Son un tipo específico de lista\
• Es una lista homogénea (caracteres)\
• La palabra Hola por ejemplo puede representarse como:
* “Hola”
* [72,111,108,97]

1> is_list("Hola"). \
true \
2> [72,111,108,97]. \
"Hola" \
3> "Hola"=[72,111,108,97]. \
"Hola" \
**Concatenación**\
  1> Msg = "Hola " ++ "Mundo". \
"Hola Mundo" \
2> "Hola " ++ Msg2 = "Hola Mundo". \
"Hola Mundo" \
3> Msg2. \
"Mundo" \
4> Msg. \
"Hola Mundo"
