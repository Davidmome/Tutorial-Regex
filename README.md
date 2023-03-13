# Cómo funciona una expresión regular (o regex)?

Es una cadena de texto generico que se usa a modo de patron y que sirve para localizar pedazos de texto dentro de otro de mayor magnitud

## Resumen

Para definir una RegEx podemos usar distintos tipos de metacaracteres dentro de una expresion. En este caso estaremos analizando la siguiente expresion regular la cual puede ser utilizada para buscar un patron de correo electronico. `^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$`

## Índice

- [Anclajes](#anclajes)
- [Cuantificadores](#cuantificadores)
- [Constructos de agrupación](#constructos-de-agrupaciones)
- [Expresiones entre corchetes](#expresiones-entre-corchetes)
- [Clases de caracteres](#clases-de-caracteres)
- [Escapes con caracteres](#escapes-con-caracteres)

## Componentes de la expresión regular

### Anclajes

Hay 2 anclajes basicos los cuales son: ^ el cual indica el inicio de linea y $ que indica el final de linea como puedes ver nuestro ejemplo `^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$` inicia y termina con estos caracteres

### Cuantificadores

Los cuantificadores son metacaracteres que indican como se pueden repetir los caracteres o grupos

- `+` indica que puede coincidir 1 o mas veces
- `*` indica que puede coincidir 0 o mas veces
- `?` indica que el caracter es opcional puede coincidir 0 o una vez
- `{a,b}` indica que puede repetirse un minimo de a veces y un maximo de b

En nuestro ejemplo:

- `^([a-zA-Z0-9_\-\.]+)@` 1 o mas veces
- `([a-zA-Z0-9_\-\.]+)\.` 1 o mas veces
- `([a-zA-Z]{2,5})$` 2 o 5 veces

### Constructos de agrupación

Son agrupaciones que sirven para envolver un conjunto de caracteres. Se indican agrupando el conjunto con parentesis ()

En nuestro ejempo tenemos 3 subexpresiones:

- `^([a-zA-Z0-9_\-\.]+)@`
- `([a-zA-Z0-9_\-\.]+)\.`
- `([a-zA-Z]{2,5})$`

### Expresiones entre corchetes

Estas expresiones indican los caracteres o rango de caracteres que deben de coincidir en nuestro patron. Para hacer una negacion o convertir un grupo en negativo se debe utilizar el comodin ^ al inicio de la expresion dentro de los corchetes.
En nuestor ejemplo

- `([a-zA-Z0-9_\-\.])$` se indica un rango de a-z minuscula, A-Z mayuscula, 0-9, guion bajo, guion y un punto

### Clases de caracteres

Esto representa tipologias de caractares como por ejemplo

- `[abc]` para designar un caracter que puede ser cualquiera de los indicados
- `[0-9]` cualquier caracter de la secuencia indicada es decir del 0 al 9
- `[^abc]` que es la negacion de la clase es decir cualquier caracter que no sea a,b o c

en nuestro ejemplo

- `([a-zA-Z]{2,5})$` conjunto de secuencias letras mayusculas y minusculas

PERL incluyo mejoras que son

- \w Coincide con cualquier caracter de palabra igual a `[a-zA-Z0-9_]`
- \W Coincide con cualquier otra cosa que no sea una letra, dígito o subrayado
- \d Coincide con cualquier dígito decimal. Equivalente a `[0-9]`
- \D Coincide con cualquier cosa que no sea un dígito decimal

### Escapes con caracteres

Para poder expresar un caracter especial en regex se debe de utilizar \ antes del caracter especial en nuestro ejemplo

- `^([a-zA-Z0-9_\-\.]+)@` \ antes de - y \ antes del .

## Autor

github: https://github.com/Davidmome
