# Resolver estos ejercicios en Pseudo codigo
Es decir resolverlo mas o menos con mis propias palabras antes de hacerlo con codigo
hay que intentar que las palabras que ponga parezcan codigo 
osea usar else if etc, voy a aponer un ejemplo de otro problema

Pick up phone book
2  Open to middle of phone book
3  Look at page
4  If person is on page
5      Call person
6  Else if person is earlier in book
7      Open to middle of left half of book
8      Go back to line 3
9  Else if person is later in book
10     Open to middle of right half of book
11     Go back to line 3
12 Else
13     Quit

## 1) Suma de múltiplos (FÁCIL)

Problema: dado un entero N, calcula la suma de todos los números entre 1 y N (incluidos) que sean múltiplos de 3 o 5.
Si N <= 0, la suma es 0.

Entrada: un entero N.
Salida: un entero con la suma.

Ejemplos:

N = 10 → múltiplos: 3,5,6,9,10 ⇒ 33

N = 1 → 0

N = 15 → suma = 3+5+6+9+10+12+15 = 60

Pistas/errores típicos:

No dupliques múltiplos de 15 (usa if (x % 3 == 0 || x % 5 == 0)).

Usa long long si quieres soportar N grande.

## 2) Estadísticas de una lista (MEDIO)

Problema: lee un entero M y luego M enteros. Calcula:

mínimo, máximo

media (double, con 2 decimales al imprimir)

mediana

moda (si hay empate, la menor)

Restricción: implementa tu propio ordenamiento simple (por ejemplo, selección o burbuja). No uses qsort en C para esta vez.

Entrada:

Línea 1: M (1 ≤ M ≤ 10^5 si lo haces eficiente; si usas burbuja, prueba con M pequeños).

Línea 2: M enteros separados por espacios.

Salida (en este orden):

min=...
max=...
media=...
mediana=...
moda=...


Ejemplos:

M=5, datos: 1 2 2 9 5

min=1, max=9, media=3.80, ordenado: 1 2 2 5 9 → mediana=2, moda=2

M=4, datos: 7 7 3 3

ordenado: 3 3 7 7 → mediana=(3+7)/2=5.00, moda=3 (empate 3 y 7 → menor es 3)

Pistas/errores típicos:

Cuidado con división entera al calcular la media.

Para mediana: si M es par, promedio de los dos centrales.

Para moda: recorre el array ordenado y cuenta rachas.

## 3) Validador de paréntesis y llaves (DIFÍCIL)

Problema: dado un texto, valida si los delimitadores (), [], {} están balanceados y bien anidados. Ignora cualquier otro carácter.

Salida:

Si todo OK: OK

Si hay error:

Si aparece un cierre que no corresponde:
ERROR en pos i: esperaba X, encontro Y

Si faltan cierres al final:
ERROR: faltan cierres, esperaba X

Donde i es el índice 0-based en la cadena. X debe ser el cierre correcto esperado (por ejemplo ]), Y el encontrado.

Sugerencia técnica: implementa una pila con un array de char.

Al leer (, [ o { → empuja.

Al leer ), ] o } → si la pila está vacía o el tope no coincide, error.

Al terminar, si la pila no está vacía, error (faltan cierres).

Ejemplos:

Entrada: {[()()]} → OK

Entrada: ([)]

En ) (pos 2): esperaba ] (porque el último abierto era [) →
ERROR en pos 2: esperaba ], encontro )

Entrada: ((abc)

Termina con ( pendiente → ERROR: faltan cierres, esperaba )

Pistas/errores típicos:

No olvides actualizar correctamente el índice i.

Cuidado al mapear apertura→cierre: (→), [→], {→}.
