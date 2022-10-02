## Complejidad computacional (se toma en el parcial y final)
###### Clase

Cuantos recursos va a consumir mi algoritmo.

# Como se copara un algoritmo? 

Recusos :
- Tiempo:   Qué tan rapido se ejecuta el algoritmo.
            Es necesario que los codigos se corran en la misma maquina
    
- Conteo de "Instrucciones": 
    - Cada sentencia simple es una instruccion (declarar una variable, etc).
    - Cada instruccion requiere de una unidad de tiempo para finalizar (horas, min).
    - Las funciones se caracterizan por la cantidad de instrucciones.
    - Esta estimacion solo sirve para comparar.
    - Permite identificar el "tamaño de problema" el cual depende de la cantidad de instrucciones.
    - permite comarar oto tipo de recurso ademas del tiempo(memoria, etc).
    - Por si solo, este modelo no es muy util.

 Se cuentan instruciones porque contar el tiempo no nos sirve

 # Notación Big O.

    - Sirve para expresar el tiempo de ejecucion como una expresión matematica.
    Vamos a poder expresar lo que tarda un algoritmo en ejecutarse, en funcion del tamaño del problema (por eso es importante definir el tamaño del problema).
    - Esta notacion permite escribir una expresion matematica que describa mi algoritmo, permitiendo una mejor comparacion con otros.

La notacion big O, busca una funcion matematica que siempre se mantenga por encima de la funcion de mi algoritmo
    - Alcanza con que la acote (por encima a T(n)) desde cierto punto(n0 en adelante).


## Analisis asintotico para algoritmos recursivos

