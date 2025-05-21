# TUPLA

## ¿Qué es?

Una **tupla** en Python es una estructura de datos que permite agrupar múltiples valores en un solo objeto. Su funcionamiento es similar al de una lista, pero con una diferencia importante: las tuplas son **inmutables**, lo que significa que **no pueden ser modificadas** una vez creadas. Es decir, no se pueden cambiar, agregar ni eliminar elementos.

Para crear una tupla, los elementos se colocan entre paréntesis y se separan por comas. Por ejemplo:

```python
tup = (4, 5, 6)
```

Sin embargo, el uso de paréntesis no es obligatorio. También se puede definir una tupla simplemente separando los elementos con comas:

```python
tup = 4, 5, 6
```

## Crear tuplas a partir de otras secuencias

También es posible generar una tupla a partir de **cualquier secuencia** (como listas o cadenas) o **iterador**, utilizando la función incorporada `tuple()`.

A continuación, algunos ejemplos:

```python
tuple([4, 0, 2])
# Resultado: (4, 0, 2)

tup = tuple('string')
# Resultado: ('s', 't', 'r', 'i', 'n', 'g')

```

## Acceso a los elementos

Es posible acceder a los elementos de una tupla utilizando **corchetes** `[]`, al igual que ocurre con la mayoría de los tipos de secuencia en Python. 

Al igual que en lenguajes como C/C++ o Java, las posiciones dentro de una tupla están **indexadas desde cero**, lo que significa que el primer elemento tiene índice `0`.

Por ejemplo:

```python
tup = ('s', 't', 'r', 'i', 'n', 'g')
tup[0]
# Resultado: 's'


```

## Tuplas anidadas

Cuando se definen tuplas que contienen otras tuplas (es decir, **tuplas anidadas**) o se utilizan **expresiones más complejas**, es recomendable —y en algunos casos necesario— **usar paréntesis para agrupar correctamente los valores**.

Por ejemplo, al crear una tupla compuesta por otras dos tuplas:

```python
nested_tup = (4, 5, 6), (7, 8)
# Resultado: ((4, 5, 6), (7, 8))
```

En este caso, nested_tup es una tupla que contiene dos elementos, y cada uno de esos elementos es a su vez una tupla.

Puedes acceder a los elementos individuales como en cualquier otra tupla:

```python
nested_tup[0]
# Resultado: (4, 5, 6)

nested_tup[1]
# Resultado: (7,8)
```



## Inmutabilidad de las tuplas

Aunque los **elementos** dentro de una tupla pueden ser objetos **mutables** (como listas), la tupla en sí misma es **inmutable**. Esto significa que **no se puede cambiar qué objeto ocupa una posición** determinada una vez la tupla ha sido creada.

En este caso:

    'foo' es una cadena (inmutable),

    [1, 2] es una lista (mutable),

    True es un valor booleano (inmutable).


Por ejemplo:

```python
tup = tuple(['foo', [1, 2], True])

tup[2] = False
# TypeError: 'tuple' object does not support item assignment

```

Este error ocurre porque no se puede modificar directamente el contenido de una posición de la tupla.

Sin embargo, sí es posible modificar el contenido de un objeto mutable dentro de la tupla. Por ejemplo:

```python
tup[1].append(3)
print(tup)
# Resultado: ('foo', [1, 2, 3], True)

```

## Concatenación de tuplas

En Python, se pueden **unir varias tuplas** utilizando el operador `+`. Esto produce una **nueva tupla** que contiene todos los elementos de las tuplas originales, en orden. Cabe destacar que este proceso **no modifica** las tuplas originales, ya que son inmutables.

Por ejemplo:

```python
resultado = (4, None, 'foo') + (6, 0) + ('bar',)
print(resultado)
# Resultado: (4, None, 'foo', 6, 0, 'bar')
```
**Nota importante**: El último grupo ('bar',) incluye una coma para que Python lo reconozca como una tupla con un solo elemento. Sin la coma, sería solo una cadena entre paréntesis, no una tupla.

Este tipo de operación es útil para construir tuplas más complejas a partir de partes más pequeñas.


## Repetición de tuplas

Al igual que con las listas, en Python se puede **multiplicar una tupla por un número entero** para repetir su contenido. Esto genera una **nueva tupla** que contiene tantas copias consecutivas de la original como lo indica el número.

Por ejemplo:

```python
tup = ('foo', 'bar') * 4
print(tup)
# Resultado: ('foo', 'bar', 'foo', 'bar', 'foo', 'bar', 'foo', 'bar')
```

Esta operación no modifica la tupla original, sino que crea una nueva con los elementos repetidos. Es útil para generar datos de prueba o construir estructuras repetitivas rápidamente.

## Desempaquetado de tuplas

Python permite asignar múltiples variables a la vez usando una sintaxis similar a la de una tupla. Cuando se usa esta estructura, **Python intentará desempaquetar** (es decir, repartir) los valores de la secuencia que está a la derecha del signo igual.

Por ejemplo:

```python
tup = (4, 5, 6)
a, b, c = tup
print(b)
# Resultado: 5
```


En este caso, los valores de la tupla se asignan a las variables a, b y c respectivamente.
Desempaquetado de tuplas anidadas

Incluso se pueden desempaquetar estructuras anidadas, siempre que la forma de la expresión coincida con la forma de la tupla:

```python
nested_tup = (4, (5, 6))
a, (b, c) = nested_tup
print(b)
# Resultado: 5
```

## Intercambio de variables con tuplas

Gracias al **desempaquetado de tuplas**, en Python se puede **intercambiar el valor de dos variables de forma directa y elegante**, sin necesidad de usar una variable temporal, como sería necesario en muchos otros lenguajes.

### En otros lenguajes (como C, Java, etc.):

```bash
tmp = a
a = b
b = tmp
```



Pero en Python, gracias a la asignación múltiple (también conocida como tuple unpacking), puedes hacerlo de forma más compacta y clara:

```python

a, b = 1, 2
print("a:", a)  # a: 1
print("b:", b)  # b: 2

# Intercambio
b, a = a, b

print("a:", a)  # a: 2
print("b:", b)  # b: 1

```
