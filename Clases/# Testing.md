# Testing (nO entra al parcial)

Las pruebas las vamos a tener que hacer nosotros.

### ¿Por qué hacer pruebas?

Es necesario saber que el programa funciona correctamente

#### Definiciones
##### - FALLA (failure):
 Defecto NO DETECTADO que puede producir errores inesperados en nuestro programa.
######  Ej: Inicializaciones no hechas, condicines mal puestas, poscondiciones incorrectas, etc.

##### - ERROR:
Estado incorrecto de nuestro programa causado por una falla.
###### Ej: Bucle infinito.

##### - FALLO(failed):
Comportamiento incorrecto de nuestro programa causado por un error.

### Tipos de Análisis

#### Análisis Estático

###### Consiste en pasar un programa por el codigo que lo analiza.

Se le dice estatico porque el codigo esta 'muerto', ya que el programa esta sin ser corrido.

Arma un grafo de dependencia que analiza como se comporta e  interactua cada componente con otras partes del sistema.
Este análisis devuelve el grafo de ejecucion, lo que da lugar a poder eliminar redundancias, ciclos, etc

#### Análisis Dinámico

###### Consiste en pasar un programa por el codigo que lo analiza mientras este ejecuta.

Trabaja con pruebas unitarias y de integración:

    - caja negra: Puedo dar una entrada y esperar una salida, pero no se que pasa dentro. 
    Su implementación no importa.
    - caja blanca: Puedo dar una entrada y esperar una salida y se que pasa dentro. Conozco el interior del codigo. 
    Se pone a prueba su implementación.

##### - Prueba unitaria:
* Prueba automatizada que se enfoca en comprobar el correcto funcionamiento de UNA unidad de nuestro sistema. 
* Facilita el debbuegueo de funciones individuales.
    ###### Una funcion, una clase, etc.

* Consiste de tres partes:
    - Inicialización:
    Creación e inicialización de elementos para obtener los datos que necesito para mi prueba.
        ###### String, Variables, etc.

    - Afirmación (assert):
     Una o mas afirmaciones que me permitan verificar si el comportamiento es el esperado.
        ###### Funcionamiento de las funciones y una correcta devolucion, etc.
    - Destrucción:
    Destrucción de los elementos inicializados y me aseguro de no olestar al resto de las pruebas con mi estado.

##### - Prueba de integración:
* Prueba automatizada que intenta comprobar el correcto funcionamiento de VARIOS componentes de nuestro sistema trabajando en conjunto y sus interacciones.
* Facilita el debbuegueo entre modulos.
* indica cómo se comporta la aplicación en conjunto.



