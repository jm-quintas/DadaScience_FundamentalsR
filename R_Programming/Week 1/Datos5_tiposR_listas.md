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


