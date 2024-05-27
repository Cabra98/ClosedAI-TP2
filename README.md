# ClosedAI - TP2
### Sistemas de Computación FCEFyN UNC - 2024 
---

Los sistemas compuestos por hardware y software utilizan arquitecturas de capas para desarrollar aplicaciones complejas. En las capas superiores se trabaja con lenguajes de alto nivel, mas "amigables" con el programador. En la capa inferior, más baja, siempre está el hardware puro y duro. Inmediatamente encima está la capa de lenguaje de bajo nivel, podríamos decir más amigable con el hardware.  
Recordemos que los lenguajes de bajo nivel están entre uno de los primeros intentos de la humanidad de despegar de la programación directa en lenguaje de máquina. Así el "ensamblador" es un lenguaje propio de la arquitectura y un intento de construir un lenguaje más accesible con el programador.  
Los lenguajes de alto nivel, para controlar el hardware y su interacción con los sistemas físicos que lo rodean, necesitan acceder al hardware a través de los lenguajes de bajo nivel. Para ello utilizan convenciones de llamadas.  
Entender cómo funciona una convención de llamada nos acercará a un conocimiento de sumo interés para áreas de desarrollo de sistemas críticos, seguridad y también para profundizar sobre el conocimiento de la interacción entre software y hardware.

Para aprobar este practico se debe diseñar e implementar una interfaz que muestre el índice GINI. La capa superior recuperará la información del banco mundial https://api.worldbank.org/v2/en/country/all/indicator/SI.POV.GINI?format=json&date=2011:2020&per_page=32500&page=1&country=%22Argentina%22. Se recomienda el uso de API Rest y Python. Los datos de consulta realizados deben ser entregados a un programa en C (capa intermedia) que convocará rutinas en ensamblador para que hagan los cálculos de conversión de float a enteros y devuelva el índice de un país como Argentina u otro sumando uno (+1). Luego el programa en C o python mostrará los datos obtenidos.-

Se debe utilizar el stack para convocar, enviar parámetros y devolver resultados. O sea utilizar las convenciones de llamadas de lenguajes de alto nivel a bajo nivel.


### Estructura

---
El main de nuestro programa fue desarrollado en Python. Aqui utilizando una API REST obtendremos los datos necesarios de los GINI de diferentes paises.  
Utilizando una interfaz grafiza, el usuario podra seleccionar el pais del cual quiere conoces sus datos GINI.   
(INSERTAR IMAGEN DE LA INTERFAZ)   
Con este dato, filtraremos la informacion para solo quedarnos con la del pais que nos interesa.  
Luego haremos el llamado a una libreria codificada en lenguaje de C, la cual hara de "pasamanos" entre Python y Assembler. A dicha libreria se le pasa como parametro un numero flotante, el cual este enviara a una funcion de Assembler para que lo transforme en un numero entero y le sume 1. Este valor retornara a la funcion de C, y esta retornara el valor ya modificado a Python.   
Con estos datos, Python graficara la evolucion de los valores GINI del pais seleccionado segun los años que se tengan registro.


### Testeo
---
Para comprobar el buen funcionamiento del programa, se codificaron 3 testeos.  

Test 1: Con este test se comprueba el buen fucionamiento de la libreria encargada de transformar los numeros flotantes. Se les pasa ciertos 


ver evidencia de depuracion con gdb para encontrar







