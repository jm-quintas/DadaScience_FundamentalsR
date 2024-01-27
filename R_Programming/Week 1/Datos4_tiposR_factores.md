# Factores.

Las ***cadenas de caracteres se utilizan para nombrar cosas u objetos*** del mundo. Igual que en el caso de los números, en R la ***clase character*** no se refiere a una cadena de caracteres aislada sino a un vector que contiene cero o más cadenas de caracteres.  

```R
persona <- c("Hugo", "Paco", "Luis", "Jose", "Kavin", "Melissa", "Nicole", "Laurent", "Jasmin", "Jason", "Mickey")
meses_nacimiento <- c("Enero", "Febrero", "Marzo", "Abril", "Mayo", "Julio", "Agosto", "Septiembre", "Octubre", "Noviembre", "Diciembre")

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


