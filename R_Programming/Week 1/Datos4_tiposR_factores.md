# Factores.

Las ***cadenas de caracteres se utilizan para nombrar cosas u objetos*** del mundo. Igual que en el caso de los números, en R la ***clase character*** no se refiere a una cadena de caracteres aislada sino a un vector que contiene cero o más cadenas de caracteres.  

```R
persona <- c("Hugo", "Paco", "Luis", "Petra", "Maria", "Fulano", "Sutano", "Perengano", "Metano", "Etano", "Propano")

mes_nacimiento <- c("Dic", "Feb", "Oct", "Mar", "Feb", "Nov", "Abr", "Dic", "Feb", "Oct", "Dic")

print(persona); print(mes_nacimiento)
```
Sol:  
[1] "Hugo"      "Paco"      "Luis"      "Petra"     "Maria"     "Fulano"  
[7] "Sutano"    "Perengano" "Metano"    "Etano"     "Propano"  
 
[1] "Dic" "Feb" "Oct" "Mar" "Feb" "Nov" "Abr" "Dic" "Feb" "Oct" "Dic"  

Si se quiere imprimir el nombre de la persona 7 con su mes de nacimiento se puede hacer con:  

```R
print(persona[7]); print(mes_nacimiento[7])
```
Sol:  
[1] "Sutano"  
[1] "Abr"  

También, podemos imprimir de la siguiente manera:  

```R
print(c(persona[7], mes_nacimiento[7]))
```
Sol:  
[1] "Sutano" "Abr"  

La función ***paste()*** permite ***concatenar cadenas de caracteres*** y por medio de ella se puede dar incluso una mejor apariencia a la salida:  

```R
print(paste(persona[7], "nacio en el mes de", meses_nacimiento[7]))
```
Sol:  
[1] "Sutano nacio en el mes de Abr"  

### Los factores y sus estructuras.
Los dos vectores anteriores pueden considerarse como una estructura de información, a la que se puede someter a algún tipo de procesamiento estadístico. Consideremos el problema de determinar la frecuencia de aparición de ciertos meses en el vector ***meses_nacimiento***. En este caso, el lenguaje provee de una clase que facilita este tipo de análisis, a saber: ***la clase factor***. Procedemos primero a transformar el vector meses_nacimiento a un ***factor***, mediante la función de conversión ***as.factor()***, como sigue:  

```R
Fmes_nacimiento <- as.factor(mes_nacimiento)
print(Fmes_nacimiento)
```
Sol:  
[1] Dic Feb Oct Mar Feb Nov Abr Dic Feb Oct Dic  
Levels: Abr Dic Feb Mar Nov Oct  

10 Levels: Abril Agosto Diciembre Enero Febrero Julio Marzo ... Septiembre  

El factor exhibe una estructura adicional denominada ***Levels***, en la que se han registrado e identificado los elementos del vector sin repetición; esto es, los nombres únicos de los meses, en este caso. La estructura interna de esta clase
se puede descubrir:  

```R
print(unclass(Fmes_nacimiento))
```
Sol:  
[1] 2 3 6 4 3 5 1 2 3 6 2  
attr(,"levels")  
[1] "Abr" "Dic" "Feb" "Mar" "Nov" "Oct"  

Como se puede ver, el núcleo de la clase son dos vectores. El primero, es un vector de índices enteros, que sustituye al vector de caracteres original, y el segundo es un vector de caracteres, que contiene los niveles (Levels) o categorías, a los que hace referencia el primer vector.

La función ***table()*** toma típicamente como argumento un factor y regresa como resultado justamente la frecuencia de aparición de los niveles en el vector de índices:  

```R
table(fmeses_nacimiento)
```
Sol:  
fmeses_nacimiento  
| _____ | Col1 | Col2 | Col3 | Col4 | Col5 | Col6 | Col7 | Col8 | Col9 | 
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| fila1| Agosto | Diciembre | Enero | Febrero | Julio | Marzo | Noviembre | Octubre | Septiembre |
| fila2 | 1 | 1 | 1 | 2 | 1 | 1 | 1 | 1 | 1 | 1 |    
      
La creación de factores en los que se establezca un orden determinado en los niveles, se puede hacer con la función ***factor()***:  

```R
meses <- c("Enero", "Febrero", "Marzo", "Abril", "Mayo","Junio", "Julio", "Agosto", "Septiembre", "Octubre", "Noviembre", "Diciembre")
ffmeses_nacimiento <- factor(meses_nacimiento, levels = meses)
print(ffmeses_nacimiento)
```
Sol:  
[1] Enero      Febrero    Marzo      Abril      Febrero    Julio       
[7] Agosto     Septiembre Octubre    Noviembre  Diciembre   
12 Levels: Enero Febrero Marzo Abril Mayo Junio Julio Agosto ... Diciembre  

Ahora la tabla de frecuencia es:  

```R
table(ffmeses_nacimiento)
```
Sol:  
ffmeses_nacimiento
| _____ | Col1 | Col2 | Col3 | Col4 | Col5 | Col6 | Col7 | Col8 | Col9 | Col10 | Col11 | Col12 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| fila1| Enero | Febrero | Marzo | Abril | Mayo | Junio | Julio | Agosto | Septiembre | Octubre | Noviembre | Diciembre |
| fila2 | 1 | 2 | 1 | 1 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | 1 |   
