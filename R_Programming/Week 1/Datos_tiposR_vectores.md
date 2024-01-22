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
# Secuencia de 8 números iniciando desde 4 y de 2 en 2.
v <- seq(from = 4, by = 2, length.out = 8)
print(v)
```
Sol:  
[1]  4  6  8 10 12 14 16 18  

Algunas veces es necesario repetir una secuencia de números varias veces para generar un vector deseado. La ***función rep()*** sirve para ese propósito.

```R
v <- c(4, 8, -3)
v2 <- rep(v, times = 5)
print(v2)
```
Sol:  
[1]  4  8 -3  4  8 -3  4  8 -3  4  8 -3  4  8 -3    

Finalmente, aveces se requiere construir un vector a partir de dos o más vectores ya existentes. La forma simple de lograr esto es con la ***función c()*** como se muestra a continuación:

```R
u <- c(3, 4, 5)
p <- c(5, 4, 3)
w <- c(u, p)

print(w)
```
Sol:  
[1] 3 4 5 5 4 3  

# Acceso a los elementos individuales de un vector.
Dentro de un vector, sus elementos se pueden identificar mediante un índice entero, que en el caso de este lenguaje empieza con el 1.

```R
v <- c(2, 4, 6, 8, 10)
print(v[1]); print(v[3]); print(v[5])
```
Sol:  
[1] 2  
[1] 6  
[1] 10  

También, podemos realizar operaciones aritmética con los índices:

```R
v1 <- c(2, 4, 6, 8, 10)
# La suma del primer y segundo elementos de v
vs = v1[1] + v1[3]
# Salida:
print(vs)
```
Sol:  
[1] 8  

El acceso a los elementos individuales de un vector no solamente es para ***consulta o lectura***, sino también para su ***modificación o escritura***.

```R
v1 <- c(2, 4, 6, 8, 10)
# Modificamos el primer índice del vector, con la suma de 2 índices:
v1[1] <- v1[2] + v1[4]
print(v1)
```
Sol:  
[1] 12  4  6  8 10  

Esta misma operación puede hacer crecer un vector. Por ejemplo, el vector v tiene 5 elementos. Si se asigna un valor al elemento 8, el vector crecerá hasta esa longitud.

```R
v1 <- c(2, 4, 6, 8, 10)
v1[8] <- 20
print(v1)
```
Sol:  
[1] 12  4  6  8 10 NA NA 20    

Para aumentar el vector a esa longitud se tuvieron que introducir elementos ausentes o vacíos que se indican con el valor NA (del inglés: Not Available) en los espacios correspondientes.  

Otra característica interesante de este lenguaje, es que permite dar nombre y acceder por medio de ese nombre a los elementos individuales de un vector.  

```R
frutas <- c(15, 20, 25, 30)
print(frutas)
```
Sol:  
[1] 15 20 25 30  

Ahora asociamos esos valores con el nombre de la fruta correspondiente:

```R
frutas <- c(15, 20, 25, 30)
names(frutas) <- c("Manzanas", "Peras", "Fresas", "Mangos")
print(frutas)
```
Sol:  
Manzanas    Peras   Fresas   Mangos  
   15        20       25      30  

Otra manera más directa de nombrar los elementos de un vector, es en el momento mismo de la creación con la función c().

```R
frutas <- c(Manzanas = 15, Peras = 20, Fresas = 25, Mangos = 30)
print(frutas)
```
Sol:  
Manzanas    Peras   Fresas   Mangos   
    15       20       25       30  

Se puede acceder a los elementos individuales del vector mediante su nombre.

```R
frutas <- c(Manzanas = 15, Peras = 20, Fresas = 25, Mangos = 30)
print(frutas["Peras"])
```
Sol:  
Peras  
 20  

El acceso a través de índices se sigue permitiendo:

```R
frutas <- c(Manzanas = 15, Peras = 20, Fresas = 25, Mangos = 30)
print(frutas[1])
```
Sol:  
Manzanas  
  15  

## Operaciones sencillas con vectores.
Las operaciones aritméticas más comunes están definidas para vectores: la suma, la resta, la división y la exponenciación, todas ellas se definen elemento a elemento entre dos vectores.

```R
# Resulta en un vector de longitud 1.
v <- 2 + 3
print(v)
```
Sol:  
[1] 5  

```R
# Resulta en un vector de longitud 2.
v <- c(1, 2) - c(5, 1)
print(v)
```
Sol:  
[1] -4  1  

```R
# Resulta en un vector de longitud 3.
v <- c(2, 3, 4) * c(2, 1, 3)
print(v)
```
Sol:  
[1]  4  3 12  

```R
# Eleva a potencias 3,2,1.
v <- c(2, 3, 4)^(3:1)
print(v)
```
Sol:  
[1] 8 9 4  

En muchas ocasiones es necesario saber la longitud de una vector. La función ***length()*** aplicada a un vector regresa precisamente ese valor:

```R
u <- 2:10
b <- c(3, 4, 5)
w <- c(u, b)
print(w)
print(length(w))
```
Sol:  
[1]  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26  
[26] 27 28 29 30  3  4  5  

Sol:  
[1] 32  

Ilustremos el uso de las operaciones lógicas.

```R
u <- 2:10
b <- c(3, 4, 5)
w <- c(u, b)
print(w <= 10)
```
Sol:  
[1]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE FALSE FALSE FALSE  
[13] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE  
[25] FALSE FALSE FALSE FALSE FALSE  TRUE  TRUE  TRUE  

El resultado es un vector de lógicos, de la misma longitud que el original y paralelo a ese, en el que se indica, elemento a elemento cuál es el resultado de la prueba lógica: “menor o igual que diez”.  

### Operadores lógicos.
| Símbolo | Descripción |
| :-----: | :-----: |
| < | Menor que |
| > | Mayor que |
| == | Igual a |
| != | Distinto a |

**Pregunta importante**: ¿qué pasa cuando los vectores operandos no son de la misma longitud? En esos casos, el intérprete del lenguaje procede a completar la operación reciclando los elementos del operador de menor longitud.

```R
vect <- c(4, 5, 6, 7, 8, 9, 10) * c(1, 2)

# Warning message:
# In c(4, 5, 6, 7, 8, 9, 10) * c(1, 2) :
  # longitud de objeto mayor no es múltiplo de la longitud de uno menor

print(vect)
```
Sol:  
[1]  4 10  6 14  8 18 10  

Es lo mismo que:

```R
vect2 <- c(4, 5, 6, 7, 8, 9, 10) * c(1, 2, 1, 2, 1, 2, 1)
print(vect2)
```
Sol:  
[1]  4 10  6 14  8 18 10  

En el primer caso el sistema ha arrojado un mensaje de advertencia, **Warning**, indicando la diferencia en las longitudes de los operandos. La eliminación de estos mensajes se hace por medio de la función ***options()***, como sigue:

```R
options(warn = -1)
vect <- c(4, 5, 6, 7, 8, 9, 10) * c(1, 2)
print(vect)
```
Sol:  
[1]  4 10  6 14  8 18 10  

Es esta funcionalidad la que permite hacer de manera muy simple algunas operaciones vectoriales,

```R
vector <- c(2, -3, 4)
# Dos veces el cuadrado de v:
vector2 <- 2 * (vector^2)
print(vector2)
```
Sol:  
[1]  8 18 32  

Algunas funciones pueden recibir como argumento un vector y producir a su salida un vector de la misma longitud que el de entrada. Tal es el caso de las funciones trigonométricas como ***sin()***, ***cos()***, y la raíz cuadrada: ***sqrt()***.

```R
v <- c(9, 8, 25)
print(sqrt(v))
```
Sol:  
[1] 3.000000 2.828427 5.000000  

```R
# El sin de 30, 45 y 60 grados.
# Primero se hace la conversión a radianes:
angulos <- c(30, 45, 60) * (pi/180)
print(angulos)
```
Sol:  
[1] 0.5235988 0.7853982 1.0471976  

```R
# Calculamos el seno:
senos <- sin(angulos)
print(senos)
```
Sol:  
[1] 0.5000000 0.7071068 0.8660254  


Proyecto 1 (Libro: El arte de programar en R):
De un edificio, a una ***altura de 15 m***, se ha lanzado con un ***ángulo de 50 grados***, un proyectil a una ***velocidad de 7 m/s***. ¿Cuáles serán las ***alturas (coordenadas y)*** del proyectil a cada ***0.5 m de distancia horizontal*** desde donde se lanzó y ***hasta los 11 m***?  

Las ecuaciones que gobiernan este fenómeno son las siguientes:  

```
                                          x = v0xt + x0
                                          y = (−1/2)gt^2 + v0yt + y0
```

