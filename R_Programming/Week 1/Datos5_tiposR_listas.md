## Listas en R.
Una lista, de la ***clase list***, es una clase de datos que puede ***contener cero o más elementos***, cada uno de los cuales puede ser de una clase distinta.

```R
# Crear una lista con los miembros de una familia:
familia <- list("Maria", "Juan", 10, c("Hugo", "Petra"), c(8, 6))
print(familia)
```
Sol:  
[[1]]  
[1] "Maria"  
  
[[2]]  
[1] "Juan"  
  
[[3]]  
[1] 10  
  
[[4]]  
[1] "Hugo"  "Petra"  
  
[[5]]  
[1] 8 6  

Nótese que la lista contiene cinco elementos; los tres primeros son a su vez de un sólo elemento: el nombre de la mamá, el nombre del papá, y los años de casados. Los siguientes dos, son dos vectores de dos elementos cada uno: los hijos y sus respectivas edades. Al igual que en el caso de los vectores, los elementos de las listas pueden ser nombrados, lo que añade mayor claridad a su significado dentro de la lista.  

```R
familia <- list(madre="Maria", padre="Juan", casados=10, hijos=c("Hugo", "Petra"), edades=c(8, 6))
print(familia)
```
Sol:  
$madre  
[1] "Maria"  
  
$padre  
[1] "Juan"  
  
$casados  
[1] 10  
  
$hijos  
[1] "Hugo"  "Petra"  
  
$edades  
[1] 8 6  

### Acceso a los elementos individuales de una lista.
Al igual que en el caso de los vectores, las listas no serían de mucha utilidad sin la posibilidad de tener acceso a sus elementos individuales. El lenguaje, provee de este acceso mediante ***tres operadores, a saber: [ ], [[ ]], y $*** (por el momento utilizaremos los dos ultimos operadores). Cuando los elementos de la lista tienen nombre, se puede acceder a ellos con cualquiera de los dos operadores.  

```R
print(familia$madre)
```
Sol:  
[1] "Maria"  

```R
print(familia[["madre"]])
```
Sol:  
[1] "Maria"  

```R
# Acceso de escritura
print(familia[["padre"]] <- "Juan Pedro")
```
Sol:  
[1] "Juan Pedro"  

Otra manera de obtenerlo:

```R
familia[["padre"]] <- "Juan Pedro"
print(familia$padre)
```
Sol:  
[1] "Juan Pedro"  

Nótese que al emplear el ***operador $***, no se han usado las comillas para mencionar el nombre del elemento, pero, este operador también admite nombres con comillas. Por otra parte, el ***operador [[ ]]***, sólo admite los nombres de elementos con comillas, o de cualquier expresión que al evaluarse dé como resultado una cadena de caracteres.  

```R
familia$"madre" <- "Maria Candelaria"
mm <- "madre"
print(familia[[mm]])
```
Sol:  
[1] "Maria Candelaria"  

```R
 print(familia[[paste("ma", "dre", sep="")]])
```
Sol:  
[1] "Maria Candelaria"  

En el último caso, el operador ha recibido como argumento la función ***paste()***, que sirve para concatenar cadenas de caracteres. Esta función supone de inicio que las cadenas irán separadas por un espacio en blanco. Por ello es que, en el ejemplo se indica que el separador es vacío mediante sep="".  
