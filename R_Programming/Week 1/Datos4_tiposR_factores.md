# Factores.

Las ***cadenas de caracteres se utilizan para nombrar cosas u objetos*** del mundo. Igual que en el caso de los números, en R la ***clase character*** no se refiere a una cadena de caracteres aislada sino a un vector que contiene cero o más cadenas de caracteres.  

```R
persona <- c("Hugo", "Paco", "Luis", "Jose", "Kavin", "Melissa", "Nicole", "Laurent", "Jasmin", "Jason", "Mickey")
meses_nacimiento <- c("Enero", "Febrero", "Marzo", "Abril", "Febrero", "Julio", "Agosto", "Septiembre", "Octubre", "Noviembre", "Diciembre")

print(persona); print(meses_nacimiento)
```
Sol:  
[1] "Hugo"    "Paco"    "Luis"    "Jose"    "Kavin"   "Melissa" "Nicole"  
[8] "Laurent" "Jasmin"  "Jason"   "Mickey"  

[1] "Enero"      "Febrero"    "Marzo"      "Abril"      "Mayo"        
[6] "Julio"      "Agosto"     "Septiembre" "Octubre"    "Noviembre"   
[11] "Diciembre"  

Si se quiere imprimir el nombre de la persona 7 con su mes de nacimiento se puede hacer con:  

```R
print(persona[7]); print(meses_nacimiento[7])
```
Sol:  
[1] "Nicole"  
[1] "Agosto"  

También, podemos imprimir de la siguiente manera:  

```R
print(c(persona[7], meses_nacimiento[7]))
```
Sol:  
[1] "Nicole" "Agosto"  

La función ***paste()*** permite concatenar cadenas de caracteres y por medio de ella se puede dar incluso una mejor apariencia a la salida:  

```R
print(paste(persona[7], "nacio en el mes de", meses_nacimiento[7]))
```
Sol:  
"Nicole nacio en el mes de Agosto"  

### Los factores y sus estructuras.
Los dos vectores anteriores pueden considerarse como una estructura de información, a la que se puede someter a algún tipo de procesamiento estadístico. Consideremos el problema de determinar la frecuencia de aparición de ciertos meses en el vector ***meses_nacimiento***. En este caso, el lenguaje provee de una clase que facilita este tipo de análisis, a saber: ***la clase factor***. Procedemos primero a transformar el vector meses_nacimiento a un ***factor***, mediante la función de conversión ***as.factor()***, como sigue:  

```R
fmeses_nacimiento <- as.factor(meses_nacimiento)
print(fmeses_nacimiento)
```
Sol:  
[1] Enero      Febrero    Marzo      Abril      Febrero    Julio      
[7] Agosto     Septiembre Octubre    Noviembre  Diciembre   

10 Levels: Abril Agosto Diciembre Enero Febrero Julio Marzo ... Septiembre  

El factor exhibe una estructura adicional denominada ***Levels***, en la que se han registrado e identificado los elementos del vector sin repetición; esto es, los nombres únicos de los meses, en este caso. La estructura interna de esta clase
se puede descubrir:  

```R
print(unclass(fmeses_nacimiento))
```
Sol:  
[1]  4  5  7  1  5  6  2 10  9  8  3  
attr(,"levels")  
[1] "Abril"      "Agosto"     "Diciembre"  "Enero"      "Febrero"     
[6] "Julio"      "Marzo"      "Noviembre"  "Octubre"    "Septiembre"  

Como se puede ver, el núcleo de la clase son dos vectores. El primero, es un vector de índices enteros, que sustituye al vector de caracteres original, y el segundo es un vector de caracteres, que contiene los niveles (Levels) o categorías, a los que hace referencia el primer vector.

La función ***table()*** toma típicamente como argumento un factor y regresa como resultado justamente la frecuencia de aparición de los niveles en el vector de índices:  

```R
table(fmeses_nacimiento)
```
Sol:  
fmeses_nacimiento  
     Abril     Agosto  Diciembre      Enero    Febrero      Julio      Marzo   
         1          1          1          1          2          1          1   
     Noviembre    Octubre Septiembre   
         1          1          1  
