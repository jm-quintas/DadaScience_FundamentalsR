# Visión general e Historia de R.

## Que es R?.  
R es un dialecto del idioma S.  

## Que es S?.  
* S es un lenguaje **desarrollado por John Chambers** y otros en Bell Labs.  
* S se **inició en 1976** como un entorno de análisis estadístico interno, originalmente implementado como bibliotecas Fortran.  
* Las primeras versiones del lenguaje no contenían funciones para modelado estadístico.
* En **1988 el sistema fue reescrito en C y comenzó a parecerse al sistema que tenemos hoy** (esta era la Versión 3 del lenguaje).
  El libro Statistical Models in S de Chambers y Hastie (el libro blanco) documenta la funcionalidad del análisis estadístico.
*La **versión 4 del lenguaje S se lanzó en 1998 y es la versión que utilizamos hoy**. El libro Programación con datos de John
Chambers (el libro verde) documenta esta versión del lenguaje.

## Notas históricas.  
* En 1993, Bell Labs otorgó a StatSci (ahora Insightful Corp.) una licencia exclusiva para desarrollar y vender el lenguaje S.
* En 2004, Insightful compró el lenguaje S a Lucent por 2 millones de dólares y es el propietario actual.
* En 2006, Alcatel compró Lucent Technologies y ahora se llama Alcatel-Lucent.
* Insightful vende su implementación del lenguaje S bajo el nombre de producto S-PLUS y ha creado una serie de características sofisticadas (GUI, en su mayoría) además, de ahí el "PLUS".
* En 2008, TIBCO adquiere Insightful por 25 millones de dólares.
* Los fundamentos del lenguaje S en sí no han cambiado dramáticamente desde 1998.
* En 1998, S ganó el premio al sistema de software de la Association for Computing Machinery.

## Filosofía S.
En “Etapas de la evolución de S”, John Chambers escribe: “Queríamos que los usuarios pudieran comenzar en un entorno interactivo, donde no se consideraran conscientemente programadores. Luego, a medida que sus necesidades se hicieran más claras y su sofisticación aumentara, deberían poder deslizarse gradualmente hacia la programación, cuando los aspectos del lenguaje y del sistema se volverían más importantes”.  

## Volver a R.
* 1991: Creado en Nueva Zelanda por Ross Ihaka y Robert Gentleman. Su experiencia en el desarrollo de R está documentada en un artículo del JCGS de 1996.
* 1993: Primer anuncio de R al público.
* 1995: Martin Mächler convence a Ross y Robert de utilizar la Licencia Pública General GNU para crear software libre R.
* 1996: Se crea una lista de correo pública (R-help y R-devel).
* 1997: Se forma el R Core Group (que contiene algunas personas asociadas con S-PLUS). El grupo central controla el código fuente de R.
* 2000: Se lanza la versión R 1.0.0.
* 2013: La versión R 3.0.2 se lanza en diciembre de 2013.

## Características de R.
* La sintaxis es muy similar a la de S, lo que facilita el cambio a los usuarios de S-PLUS.
* La semántica es superficialmente similar a S, pero en realidad es bastante diferente (más sobre esto más adelante).
* Se ejecuta en casi cualquier plataforma informática/sistema operativo estándar (incluso en PlayStation 3).
* Lanzamientos frecuentes (anuales + lanzamientos de corrección de errores); desarrollo activo.
* Bastante sencillo, en lo que respecta al software; La funcionalidad se divide en paquetes modulares.
* Capacidades gráficas muy sofisticadas y mejores que la mayoría de los paquetes de estadísticas.
* Útil para el trabajo interactivo, pero contiene un potente lenguaje de programación para desarrollar nuevas herramientas (usuario -> programador).
* Comunidad de usuarios muy activa y vibrante; Listas de correo de R-help y R-devel y desbordamiento de pila.
* ¡Es gratis!

## Software libre.
Con el software gratuito, tienes garantizado:  

* La libertad de **ejecutar el programa, para cualquier propósito** (libertad 0).
* La libertad de **estudiar cómo funciona el programa y adaptarlo a tus necesidades** (libertad 1). El acceso al código fuente es una condición previa para esto.
* La libertad de **redistribuir copias para poder ayudar a tu prójimo** (libertad 2).
* La libertad de **mejorar el programa y hacer públicas sus mejoras**, de modo que toda la comunidad se beneficie (libertad 3). El acceso al código fuente es una condición previa para ello.

## Desventajas de R.
* Básicamente basado en tecnología de 40 años.
* Poco soporte integrado para gráficos dinámicos o 3-D (pero las cosas han mejorado mucho desde los “viejos tiempos”).
* La funcionalidad se basa en la demanda de los consumidores y las contribuciones de los usuarios. Si nadie tiene ganas de implementar tu método favorito, ¡entonces es tu trabajo!.
* Por lo general, los objetos deben almacenarse en la memoria física; pero también ha habido avances para lidiar con esto.
* No es ideal para todas las situaciones posibles (pero esto es un inconveniente de todos los paquetes de software).

## Diseño del Sistema R.
El sistema R se divide en 2 partes conceptuales:  
1. El sistema R “base” que descargas de CRAN.
2. Todo lo demás.

La funcionalidad de R se divide en varios paquetes.
1. El sistema R “base” contiene, entre otras cosas, el paquete base necesario para ejecutar R y contiene las funciones más fundamentales.
2. Los otros paquetes contenidos en el sistema "base" incluyen utils, stats, datasets, graphics, grDevices, grid, methods, tools, parallel, compiler, splines, tcltk, stats4.
3. También hay paquetes "Recomendados": boot, class, cluster, codetools, foreign, KernSmooth, lattice, mgcv, nlme, rpart, survival, MASS, spatial, nnet, Matrix.

Y hay muchos otros paquetes disponibles:  
* Hay alrededor de 4000 paquetes en CRAN que han sido desarrollados por usuarios y programadores de todo el mundo.
* También hay muchos paquetes asociados con el proyecto Bioconductor (http://bioconductor.org).
* Las personas suelen ofrecer paquetes en sus sitios web personales; No existe una forma confiable de realizar un seguimiento de cuántos paquetes hay disponibles de esta manera.

## Algunos recursos de R.
Disponible en CRAN (http://cran.r-project.org).
* Una introducción a R.
* Escribir extensiones R.
* Importación/exportación de datos R.
* Instalación y administración de R (principalmente para construir R a partir de fuentes).
* R Internals (no apto para cardíacos).

## Algunos libros útiles sobre S/R.
Textos estándar:  
* Chambers (2008). Software for Data Analysis, Springer. (your textbook)
* Chambers (1998). Programming with Data, Springer.
* Venables & Ripley (2002). Modern Applied Statistics with S, Springer.
* Venables & Ripley (2000). S Programming, Springer.
* Pinheiro & Bates (2000). Mixed-Effects Models in S and S-PLUS, Springer.
* Murrell (2005). R Graphics, Chapman & Hall/CRC Press.

Otras fuentes:  
* Springer tiene una serie de libros llamados Use R!.
* Una lista más larga de libros está en http://www.r-project.org/doc/bib/R-books.html.
