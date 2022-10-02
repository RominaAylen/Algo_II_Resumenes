# TDA-  Tipo de Dato Abstracto

#### Concepto de Abstracción

* Es la separación de las caracteristicas de un elemento para poder enfocarse en esa parte.
* Consiste no solo de operaciones, sino tambien de valores de los datos subyacentes y de restricciones en las operaciones.

###### Entender el contexto para desarrollar el tp.

#### ¿Qué tipo de datos existe?
*  tipo de datos básicos (int, char, bool, etc.)
* Se pueden generar tipos de datos mas complejos que para definirse se necesita: 
     - El contenido (definicion de un dato básico).
     - Las operaciones que la definen(suma, resta, etc.).

#### El qué y el cómo

##### Qué hace?
CAJA NEGRA

* Se habla de funcionalidad

##### Cómo lo hace?
CAJA BLANCA

* Se habla de la forma en que algo esta implementado (o diseñado).
* Interesa saber la estructura interna l la forma en la cual se lleva a cabo algo.

#### ¿Por qué usamos TDAs?
##### - Manejan la abstración:
La abstraccón permite simplificar la realidad mediante el despojo de complejidad que no es propio del problema que estamos resolviendo.

##### - Encapsulamiento:
Es la propiedad por la cual un TDA debe exponer la menor cantidad posible de información del como esta implementado, haciendo que el usuario se base en las funciones que él mismo entiende.

##### - Localización del cambio:
Cuando existen errores dentro de un programa, es más facil detectarlo, ya que las TDAs fuerzan la modularización.


##### Ejemplo: Número complejo.

###### Se pide desarrollar un TDA que sea un número complejo.

Hay que tener una noción de rango:
##### Contenido:
Descripción: Son numeros que deberian contener parte entera y parte real.

##### implementación:
Funcionalidades: Debe poder crearlo, hacer operaciones, e imprimir por pantalla.

typedef struct complejo{
        double real;
        double imag;
} complejo;

/* c = a + b */
void add_c (complejo* c, complejo a, complejo b){
    c->real = a.real + b real;
    c->imag = a.imag + b imag;
}



