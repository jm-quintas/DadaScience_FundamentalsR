# Datos y sus tipos.

Todas las cosas que manipula R se llaman objetos. En general, éstos se construyen a partir de objetos más simples. De esta manera, se llega a los objetos más simples que son de cinco clases a las que se denomina atómicas y que son las siguientes:

* character (cadenas de caracteres).
* numeric (números reales).
* integer (números enteros).
* complex (números complejos).
* logical (lógicos o booleanos, que sólo toman los valores True o False).

En el lenguaje, sin embargo, cada uno de estas clases de datos no se encuentran ni se manejan de manera aislada, sino encapsulados dentro de la clase de objeto más básica del lenguaje: el vector. **Un vector puede contener cero o más objetos, pero todos de la misma clase**. En contraste, la clase denominada **list, permite componer objetos también como una secuencia de otros objetos, pero, a diferencia del vector, cada uno de sus componentes puede ser de una clase distinta**.

## Los datos numéricos.
El principal uso de R es la manipulación de datos numéricos. El lenguaje agrupa estos datos en tres categorías, a saber: **numeric, integer y complex**, pero cuando se introduce algo que puede interpretar como un número, su inclinación es tratarlo como un dato de tipo numeric, es decir, un número de tipo real, a no ser que explícitamente se indique otra cosa.

```R
# Se asigna el valor 2 a x.
x <- 1
# Se imprime el valor de x.
print(x)
```
Sol: 1  

```R
# Se asigna el valor 2 a x.
x <- 1
# Se imprime la clase de dato.
print(class(x))
```
Sol: "numeric"  

```R
# Asignamos la operacion de dividir a y.
y <- 6/2 
print(y)
```
Sol: 3

```R
# Asignamos la operacion de dividir a y.
y <- 6/2 
print(class(y))
```
Sol: "numeric"  

Para asignar explícitamente un entero, **integer**, a una variable, se agrega la letra L al final del número, como sigue:  

```R
z <- 23L; print(z)
```
Sol: 23

```R
z <- 23L; print(class(z))
```
Sol: "integer"  

Para lograr que una expresión, como la operación de división 6/2, arroje como resultado un entero, se tiene que hacer una **conversión; ello se logra mediante la función as.integer**, como sigue:

```R
x <- as.integer(6/2); print(x)
```
Sol: 3  

```R
x <- as.integer(6/2); print(class(x))
```
Sol: "integer"  

Las funciones de conversión más comunes en R son las siguientes:  

| Función | Descripción |
| :----: | :----: |
| as.character() | convierte un objeto a un objeto de tipo carácter |
| as.numeric() | Convierte un objeto a un objeto de tipo numérico |
| as.logical() | convierte un objeto a un objeto de tipo lógico |
| as.integer() | convierte un objeto a un objeto de tipo entero |
| as.complex() | convierte un objeto a un objeto de tipo complejo |
| as.Date() | convierte un objeto a un objeto de tipo fecha |
| as.POSIXct() | convierte un objeto a un objeto de tipo fecha/hora |

Por otra parte, los números complejos, **complex en el lenguaje**, tienen una sintaxis muy particular; misma que se tiene que emplear para indicar explícitamente que un número introducido corresponde a ese tipo:  

```R
x <- 21 + 2i
y <- 2i + 21
z <- -1 + 0i

tt <- sqrt(z)

print(x); print(y); print(z); print(tt); print(class(tt))
```
Sol:  
21+2i  
21+2i  
-1+0i  
0+1i  
"complex"  

También, existe un valor numérico especial, Inf, que representa el infinito y que puede resultar en algunas expresiones.

```R
i <- 1/0
print(i)
```
Sol: Inf  

```R
n <- 1/Inf
print(n)
```
Sol: 0  

Finalmente, algunas operaciones pueden resultar en algo que no es un número, esto se representa por el valor NaN.

```R
x <- 0/0
print(x)
```
Sol: NaN  

