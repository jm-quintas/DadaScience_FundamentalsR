# Matrices.
Una matriz ***es un vector con un atributo adicional: dim***. Para el caso de las matrices, este atributo es un vector entero de dos elementos, a saber: el ***número de renglones y el número de columnas*** que componen a la matriz.

## Construcción de matrices.
Una de las formas de construir una matriz es a partir de un vector.

```R
# Un vector con 2 número:
m <- 1:20
print(m)
```
Sol:  
[1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20  

Para convertirlo en una matriz se especifica el atributo ***dim***.

```R
# 4 renglones y 5 columnas.
dim(m) <- c(4, 5)
print(m)
```
Sol:  
| _____ | Col1 | Col2 | Col3 | Col4 | Col5 |
| :---: | :--: | :--: | :--: | :--: | :--: |
| Fila1 | 1 | 5 | 9 | 13 | 17 |
| Fila2 | 2 | 6 | 10 | 14 | 18 |
| Fila3 | 3 | 7 | 11 | 15 | 19 |
| Fila4 | 4 | 8 | 12 | 16 | 20 |

```R
print(class(m))
```
Sol:  
"matrix"  

El armado de la matriz ***se hace por columnas***. Por otra parte, las dimensiones de la matriz pueden cambiarse en cualquier momento, y ***el acceso a un elemento particular de la matriz se hace ahora mediante dos índices: el renglón y la columna***, aunque, el acceso a los elementos de la matriz como un vector, es decir, con un solo índice, sigue siendo posible.

```R
dim(m) <- c(5, 4)
print(m)
```
Sol:  
| _____ | Col1 | Col2 | Col3 | Col4 |
| :---: | :--: | :--: | :--: | :--: |
| Fila1 | 1 | 6 | 11 | 16 |
| Fila2 | 2 | 7 | 12 | 17 |
| Fila3 | 3 | 8 | 13 | 18 |
| Fila4 | 4 | 9 | 14 | 19 |
| Fila5 | 5 | 10 | 15 | 20 |

El elemento en el renglon 3 y columna 2 es:

```R
print(m[3, 2])
```
Sol:  
[1] 8  

Acceso al mismo elemento, como vector, con un solo índice.

```R
print(m[8])
```
Sol:  
[1] 8  

Una ventaja del lenguaje es que permite hacer referencia a una columna o a un renglón de la matriz, como si se tratara de un sólo objeto, o sea como un vector. Para ello, se omite alguno de los dos índices en la expresión de acceso a la matriz.  

```R
El reglón 3 de la matriz:
print(m[3, ])
```
Sol:  
[1]  3  8 13 18  

```R
La columna 2 de la matriz:
print(m[ , 2])
```
Sol:  
[1]  6  7  8  9 10  

```R
# La clase las columnas o renglones:
print(class(m[3, ]))
```
Sol:  
[1] "integer"  

Las matrices también se pueden crear de manera flexible por medio de la función primitiva ***matrix()***, que permite alterar la secuencia por default de armado de la matriz. Se puede ***armar la matriz por renglones en vez de columnas***:  

```R
 m <- matrix(11:30, nrow = 5, ncol = 4, byrow = TRUE)
print(m)
```
Sol:  
| _____ | Col1 | Col2 | Col3 | Col4 |
| :---: | :--: | :--: | :--: | :--: |
| Fila1 | 11 | 12 | 13 | 14 |
| Fila2 | 15 | 16 | 17 | 18 |
| Fila3 | 19 | 20 | 21 | 22 |
| Fila4 | 23 | 24 | 25 | 26 |
| Fila5 | 27 | 28 | 29 | 30 |

Adicionalmente, a los ***renglones y las columnas de una matriz se les pueden asignar nombres***, que pueden ser después consultados o usados como índices:

```R
rownames(m)<- c("uno", "dos", "tres", "cuatro", "cinco")
colnames(m)<- c("UNO", "DOS", "TRES", "CUATRO")

print(m)
```
Sol:  
| _____ | UNO | DOS | TRES | CUATRO |
| :---: | :--: | :--: | :--: | :--: |
| uno | 11 | 12 | 13 | 14 |
| dos | 15 | 16 | 17 | 18 |
| tres | 19 | 20 | 21 | 22 |
| cuatro | 23 | 24 | 25 | 26 |
| cinco | 27 | 28 | 29 | 30 |

```R
# Consultamos los nombres de las columnas:
print(colnames(m))
```
Sol:  
[1] "UNO"    "DOS"    "TRES"   "CUATRO"  

```R
# Consultar una columna:
print(m[ , "DOS"])
```
Sol:  
| uno | dos | tres | cuatro | cinco |
| :---: | :--: | :--: | :--: | :--: |
| 12 | 16 | 20 | 24 | 28 |

Las funciones ***rbind()*** y ***cbind()***, son otras que se pueden utilizar para construir matrices, dando, ya sea los renglones individuales o las columnas individuales, respectivamente.  

```R
m1 <- rbind(c(1.5, 3.2, -5.5), c(1, 1.1, 70))
print(m1)
```
Sol:  
| _____ | Col1 | Col2 | Col3 |
| :---: | :--: | :--: | :--: |
| Fila1 | 1.5 | 3.2 | -5.5 |
| Fila2 | 1.0 | 1.1 | 70.0 |

```R
print(class(m1[1, ]))
```
Sol:  
"numeric"  

```R
m2 <- cbind(c(1.5, 3.2, -5.5), c(0, 1.1, 70))
print(m2)
```
Sol:  
| _____ | Col1 | Col2 |
| :---: | :--: | :--: |
| Fila1 | 1.5 | 0.0 |
| Fila2 | 3.2 | 1.1 |
| Fila3 | -5.5 | 70.0 |

## Acceso a los elementos individuales de una matriz.
El lenguaje también provee de mecanismos para acceder a los elementos individuales de una matriz. Para ello se emplea el operador [].

```R
print(m[2,1])
```
Sol:  
[1] 15  

## Operaciones sencillas con matrices.
las operaciones aritméticas válidas para vectores, son validas para las matrices, siempre y cuando, las matrices operando tengan las mismas dimensiones y se aplican elemento a elemento. 

```R
m <- matrix(1:6, nrow = 2, ncol = 3)
mm <- rbind(1:3, 3:1)
print(m)
print(mm)
```
Sol:  
| _____ | Col1 | Col2 | Col3 |
| :---: | :--: | :--: | :--: |
| Fila1 | 1 | 3 | 5 |
| Fila2 | 2 | 4 | 6 |

| _____ | Col1 | Col2 | Col3 |
| :---: | :--: | :--: | :--: |
| Fila1 | 1 | 2 | 3 |
| Fila2 | 3 | 2 | 1 |

Aplicando la operación arítmetica de la suma:  

```R
print(m + mm)
```
Sol:  
| _____ | Col1 | Col2 | Col3 |
| :---: | :--: | :--: | :--: |
| Fila1 | 2 | 5 | 8 |
| Fila2 | 5 | 6 | 7 |

Aplicando la operación arítmetica de la multiplicación:  

```R
print(m * mm)
```
Sol:  
| _____ | Col1 | Col2 | Col3 |
| :---: | :--: | :--: | :--: |
| Fila1 | 1 | 6 | 15 |
| Fila2 | 6 | 8 | 6 |

Aplicando la traspuesta a una matriz:

```R
print(t(m))
```
Sol:  
| _____ | Col1 | Col2 |
| :---: | :--: | :--: |
| Fila1 | 1 | 2 |
| Fila2 | 3 | 4 |
| Fila3 | 5 | 6 |

