# Vectores.
Se ha dicho con anterioridad que las clases atómicas de datos no se manejan de manera individual. En efecto, en todos los ejemplos anteriores, el lenguaje ha creado implícitamente vectores de longitud 1, y son esos los que se han asignado a las variables.

```R
x <- 2; print(x)
```
Sol:  
[1] 2  

Aquí, la impresión del valor de x tiene una forma muy particular: ***[1] 2***. El ***[1]*** que precede al valor, indica que se trata del primer elemento y único, en este caso, del vector que se muestra.  

## Función c() para crear vectores.
La primera manera de crear vectores es a partir de los elementos individuales que compondrán el vector.

```python
x <- c(4, 2, -8); print(x)
```
Sol:  
[1]  4  2 -8  

Distintas formas de asignar un vector a una variable:  

```python
# Asignación de un vector a una variable, utilizando los operadores <- y ->:
v1 <- c(4, 2, -8)
c(4, 2, -8) -> v2

# Usando la función assign para definir un vector:
assign("v3", c(4, 2, -8))

# Utilizar el operador = para generar la asignación:
v4 = c(4, 2, -8)

# Salidas:
print(v1); print(v2); print(v3); print(v4)
```
Sol:  
[1]  4  2 -8  
[1]  4  2 -8  
[1]  4  2 -8   
[1]  4  2 -8  

La ***función c()*** sirve para concatenar varios elementos del mismo tipo. En todos los ejemplos mostrados, la impresión del vector se hace en un renglón que comienza con el símbolo ***[1]***, indicando con ello que el primer elemento del renglón corresponde al primer elemento del vector.  

Un caso muy particular de asignación, es el de la ***función assign()***. A diferencia de los otros casos vistos en el ejemplo anterior, el nombre de la variable aparece entre comillas.

## Creación de vectores a partir de archivos de texto - la función scan().
Otra manera de crear un vector es a partir de un archivo de texto. Si tenemos un archivo ***Vec.txt*** que contiene la siguiente información:

```
12 15.5 3.1
-2.2 0 0.0007
```

Ahora a partir de esos datos creamos un vector. Para eso se usa la ***función scan()***:

```R
vec <- scan("Vec.txt")
print(vec)
```
Sol:  
[1] 12.0000 15.5000  3.1000 -2.2000  0.0000  0.0007  

La función inversa, en este caso, de la función scan(), es la ***función write***. Así, un vector cualquiera fácilmente se puede escribir en un archivo de texto.

```R
# Creamos una variable y le asignamos un vector:
vv <- c(5, 6.6, -7.7)
# Escribir la información almacenada en la variable vv en un archivo creado con el nombre "OtroArchivo.txt":
write(vv, "OtroArchivo.txt")
print(vv)
```
Sol:  
[1] 5.0  6.6 -7.7  

Ahora recuperamos el contenido del archivo.  

```R
v1 <- scan("OtroArchivo.txt")
print(v1)
```
Sol:  
[1]  5.0  6.6 -7.7  

## Creación de vectores a partir de secuencias y otros patrones.
El operador : permite generar un vector entero a partir de una secuencia creciente o decreciente de enteros.

```R
x <- 1:5
print(x)
```
Sol:  
[1] 1 2 3 4 5  

```R
y <- 5:1
print(y)
print(class(y))
```
Sol:  
[1] 5 4 3 2 1  
[1] "integer"  

El alcance del operador : no se limita solo a números enteros.  

```R
v <- pi:6
print(v); print(class(v))
```
Sol:  
[1] 3.141593 4.141593 5.141593  
[1] "numeric"  

En este caso, pi simboliza el valor de la constante matemática π aproximadamente igual a 3.1416, y la secuencia de números reales que se produce es con incrementos de 1 a ese valor hasta mientras que no se rebase el límite superior, 6, en este caso. Por otra parte, la función ***seq()*** permite generar una mayor variedad de secuencias numéricas.

```R
v <- seq(from = 5, to = 15, by = 2)
# Secuencia desde 5 hasta 15 de 2 en 2
print(v); print(class(v))
```
Sol:  
[1]  5  7  9 11 13 15  
[1] "numeric"  

En seguida se muestra sólo otra forma bastante común de utilizar esta función, que tiene que ver con la producción de un vector o una secuencia de una longitud determinada.

```R
v <- seq(from = 4, by = 2, length.out = 8)
print(v)
```
Sol:  
[1]  4  6  8 10 12 14 16 18  

