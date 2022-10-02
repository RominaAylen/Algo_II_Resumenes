# Tipo de dato abstracto


* La abtracción es un proceso por el cual se despoja a un problema o cosa, la complejidad que no es relevante para la solución de un problema determinado.
* Para el leguaje de C, las herramientas que hacen extencible al lenguaje con nuevas abstraciones son:
    - Funciones y procedimientos.
    - Archivos de encabezado.
    - Tipos de datos primitivos del lenguaje que definen dos cosas importantes:

        - El conjunto de valores que una variable de ese tipo puede tomar.
        - Las operaciones que se pueden realizar.

#### ¿Qué es un tipo de dato abstracto?

* Define una clase de objetos abstractos los cuales estan vcompletamente caracterizados por la operaciones que pueden realizarse sobre estos.
* Se definen a partir de sus estructura de dato y las operaciones de las mismas.
* La visión de aquel que lo utiliza es exclusivamente de caja negra.
* Deben tender a parecerse  un tipo de dato primitivo del lenguaje.
* La mayoria de las operaciones que se utilizan en un programa de un determinado TDA pertenecen al set de operaciones caracteristicas del mismo.

* A partir del momento que se comienza a manejar estructuras de datos complejas, es importante dividir dos conceptos:
    - Funcinalidad:
    Desde la visión del implementador del TDA, este debera basarse en la forma en la que se diseña e implementa en base a la funcionalidad que el mismo debe cumplir.
    - Diseño de implementación:
    Desde la visión del del usuario del TDA, al cual le importa que haga lo que dice que hace.
###### Ambas partes estan obligadas a cumplir un contrato que esta aceptado en el archivo de cabecera(.h).
* Es vital la utilización de las Pre y Post condiciones, declaradas en un .h.

#### Ventajas de las TDA:
* Manejan la abtraccción: Permiten crear niveles de abstracción basándose en contruir TDAs nuevos usando tipos de datos primitivos y otros TDAs.
* Encapsulamiento: Es la propiedad por la cual un TDA debe exponer la menor catidad posible de información de cómo esta implemntad, por lo debe hacer que el usuario se base en las funcionrd que el mismo entiende.
* Localización del cambio: Cuando existe une rror dentro de un proograma, es mucho mas fácil detectarlo gracias a que las TDAs fuerzan la modularización.


