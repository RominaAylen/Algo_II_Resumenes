# Recursividad

* Son algoritmos que de llaman a si mismo para resolver un determinado problema.

### Recursividad Directa

En el lenguaje de C es posible contruir funciones recursivas de la misma forma que en las matematicas:

* Debe cumplir con las siguentes reglas para ser considerada recursiva:
    - Debe poseer condición de corte.
    - debe tener una llamada a si misma dentro de la función.

#### Ambito de una Función
* Cuando un programa pasa de estar almacenadod en el disco se ejecutado, el mismo es cargado en memoria y estructurado es cuatro partes:
    - .code
    - .data
    - .heap
    - .stack

* El ambito de una función es la porción de memoria que se crea cuando esta es llamada y se destruye cuanando la función termina su ejecución.

##### Se utiliza el STRACK o PILA DE EJECUCIÓN:
- Es una parte del programa donde se mantiene la información sobre cual función es la que se esta siendo ejecutada, sus variables y parametros.
- Cumple sis funciones de forma automatica  y es independiente del programador.
- El STRCK de ejecución de un programa es una estructura de datos de la cual únicamente se puede obtener informacion de su tope.
#### Recursividad Indirecta
* Son algoritmos donde una función provoca una llamada a sí misma de forma indirecta, a través de otras funciones.
*AL igual que las directas, deben tener un punto de corte.

#### Recursividad de cola   
* Es una tecnica para optimizar la recursividad, eliminando las 
constantes llamadas recursivas.
* Tail recusion se de cuando la llamada recursiva es la ultima instrucción de la función:
    - En la parte que realiza la llamada a la función, no debe existir ninguna otra instrución.
* Ventajas:
    - Evita la sobrecarga de cada llamada a la función.
    - Evita en gasto de memoria de pila.
    - Evita el stck overflow.
    - La cantidad de información que debe ser almacenada durante el calculo es independiente del numero de llamadas recursivas.
* Una función recursiva normal se puede convertir atail recursive usando en la función original un párametro adicional, usado para ir guardando un resultado de tal manera que la llamada recursiva ya no tiene una operación pendiente.
    