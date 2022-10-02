# TDA Listas y sus Derivados

* Mediante la abstracción, la cual a traves de combinaciones de ciertas herramientas primitivas, se pueden crear nuevos tipos de datos. Las herramientas son:
    - Tipos primitivos: int, char, bool, etc.
    - Funciones: permiten generar y encapsular nuevas acciones o funcionalidades sobre los datos.
    - Bibliotecas: Agrupan acciones y datos, para generar nuevos tipos de datos.
    - Caja negra.
* Las TDA se implementan utilizando memoria dinámica.

#### TDA Nodo enlazado
* La idea que abstrae un nodo enlazado es la propiedad de que una entidad pueda conocer quien le sucede o antecede.

        typedef struct nodo
        {
            dato_t elemento
            nodo_t *siguiente
            nodo_t *anterior
        }nodo_t;

#### TDA Pila
* Es una colección ordenada de elementos en la que se pueden isertar o eliminar elementos a travez de su extremo 'TOPE'
* Existe un pequeño conjunto de operaciones que siempre debería estar pero que no siempre son estandar:
    - Crear (create) -> Se realizan operaciones que tienen que ver con el tamaño de la pila, inicializaciones, etc.
    - Poner (push) -> Pone un elemento en la pila por el tope, convirtiendo a este ultimo en tope.
    - Sacar (pop) -> Retira el tope de la pila y mueve el tope de esta hacia el elemento anterior al extraído, si el elemto extraído es el ultimo, la pila quedará vacía.
    - Tope (top) -> Permite observar el valor del tope de la pila.
    - Esta vacia (is  empty) -> Devuelve TRUE: Si no hay elementos. FALSE: si hay elementos.
    - Destruir (destroy) ->  Libera y limpia todos los recursos que se utilizan oara la creacion de una pila, la misma posee elemntos en su interior, debe vaciarse en el proceso de destrucción.

#### TDA Cola

* Es una estructura que posee dos extremos por los que se realizan operaciones.

* Sirve para modelar procesos.

* El conjunto mínimo de operaciones es: 

    - Crear (create) -> Se realizan operaciones que tienen que ver con el tamaño de la cola, inicializaciones, etc.
    - Encolar (enqueue) ->  Los elemnetos se encolan por el final de la cola
    - Desencolar (dequeue) -> Los elemnetos se extraen del frente de la cola. (FIFO)
    - Primero (first) -> Permite observar el primer elemento del del frente de la cola.
    - Esta vacia (is empty) -> Permite determinar si una cola tiene o no tiene elementos. Devuelve:
        - TRUE: Si no hay elementos. 
        - FALSE: si hay elementos.
    - Destruir (destroy) -> Libera y limpia la todos los recursos que se utilizan para la creación de una cola.

#### Lista simple enlazada

* Esta basada en nodos enlazados.
    - El nodo para conocer su siguiente puede crear una lista de nodos
    - Cuando el nodo es el utimo devuelve NULL.
    -Su recorrido es unidereccionalmente.

* Las operaciones básicas de una lista enlazada son:

    * Crear:
        - Se debe inicializar la estructura lista_t, seeteando todos sus campos válidos.
        - Al implementarse con memoria dinámica, se debe reservar la cantidad de memoria dinamica en el heap.
    * Insertar: 
        - Inserta un elemento al final de la lista.
        - Devuelve 0 si pudo insertar.
        - Devuelve -1 si NO pudo insertar.

    * Insertar en posicion:
        - Inserta un elemento en la posición indicada.
        - Donde 0 es insertar como primer elemento.
        - Donde 1 es insertar luego del primer elemento.
        - En caso de no existir la posición indicada, lo inserta al final.
        - Devuelve 0 Si pudo insertar.
        - Devuelve -1 Si pudo NO insertar.
                
                insertar_en_posicion(0,z);

    * Borrar -> Quita de la lista el elemento que se encuentra en la ultima posición.
        - Devuelve 0 Si pudo eliminar.
        - Devuelve -1 Si pudo NO eliminar.
    * Borrar de posicion:   
        - Quita de la lista el elemento que se encuentra en la posición indicada.
        - Donde 0 es el primer elemento.
        - En caso de no existir la posición indicada, se intentará borrar el elemento final.

                borrar_de_posicion(0);

    * Elemento en posicion:
        - Devuelve el elemento de la posición indicada.
        - Donde 0 es el primer elemento.
        - Si no existe dicha posición devuelve NULL.
        elemento_de posicion(i);
    * Ultimo -> Devuelve el ultimo elemento de la lista
        - Si la lista esta vacia devuelve NULL.

                ultimo();

    * Vacia 
        - Devuelve TRUE si la lista esta vacía
        - Devuelve FALSE si la lista esta NO esta vacía.
    * Elementos -> Devuelve la cantidad de elemntos almacenados en la lista.
    * Destruir -> Libera la memoria reservada por la lista.