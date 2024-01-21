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

