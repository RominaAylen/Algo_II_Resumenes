# Introducción al TDA Pila
##### ¿Qué es una pila?

* Estructura de datos en el cual se van a poder agrupar elementos.

* Su funcion es poder agrupar elementos, cualquier tipo de dato.(no sirve para buscar elemntos).

* Es recomendable que esos elementos sean del mismo tipo, a lo largo de toda la pila.

* LIFO (Last In, First Out).El ultimo elemento en entrar, va a ser el ultimo elemento en salir.

* Solo tengo acceso al tope de la pila, y el usuario no va a poder ver el resto de los elementos.

###### Ejemplo: Ctrl + z.

#### Operaciones del TDA Pila
* Crear (Create)
* Apilar (Push) -> Meter en el tope.
* Tope(Top) -> Muestra sin desapilar el ultimo elemento.
* Destruir (Destroy)
* Desapilar (Pop) -> Sacar del tope, pero no lo elimina.
* Vacia (isEmpty) -> Booleano, Avisa si esta vacía.

#### ¿Cómo se implementan las pila?

##### Implementación con vector estático
    #define CAPACIDAD 5

    typedef pila{
        int a;
        int b;
    }pilas_t;

    int vector[CAPACIDAD];
    int tope = 0;
- ¿Puedo apilar? SI, tope != CAPACIDAD
- ¿Está vacía? SI, tope == 0
- ¿Puedo desapilar) NO, tope == 0

---------------------------------

    int vector[CAPACIDAD] = {55,6};
    int tope = 2;
- ¿Puedo apilar? SI, tope != CAPACIDAD
- ¿Está vacía? NO, tope != 0
- ¿Puedo desapilar) SI, tope != 0

---------------------------------

    int vector[CAPACIDAD] = {55,6, 29,37,14};
    int tope = 5;
- ¿Puedo apilar? NO, tope == capacidad
- ¿Está vacía? NO, tope != 0
- ¿Puedo desapilar) SI, tope != 0

##### Complejidad algoritmica

* Crear (Create) -> O(1).
* Apilar (Push) -> O(1).
* Destruir (Destroy) -> O(1)/O(n).
* Desapilar (Pop) -> O(1).

#### Implementación con vector dinámico
Se inicializa el vector en  en minimo segun la funcionalidad del mismo.

    #define CAPACIDAD 5

    typedef pila{
        int tope;
        void* vector[CAPACIDAD] = {55,6, 29,37,14};
    }pilas_t;

- ¿Puedo apilar? SI, puedo pedir mas memoria 
- ¿Está vacía? SI, tope == 0
- ¿Puedo desapilar) NO, tope == 0

###### Redimensión: 

¿Cuanto se agranda? Cuando la pila crece:

- Cuando  se supera el %75 de la capacidad.
- Cuando se llena.
- Etc.

¿Cuanto se achica? Cuando se desapila:
- Cuando llega al %50 de la capacidad.
- Cuando desapilo
- Cuando llega al %25 de la capacidad.
- Etc.

##### Complejidad algoritmica

* Crear (Create) -> O(1).
* Apilar (Push) -> O(n).
* Destruir (Destroy) -> O(1)/O(n).
* Desapilar (Pop) -> O(n).

#### Implementación con nodos enlazados
* Individualización de un elemento.
* El TDA  guarda el elemento y un puntero al siguiente nodo.
* A veces, tambien guarda un puntero al anterior elemnto.
* La memoria no debe ser contigua.
* Da flexibilidad.
¿Cuándo reservo / libero memoria?
* Reservo para cada nodo cuando quiero apilar.
* Libero para cada nodo cuando quiero desapilar.
* En la primera posición, el anterior esta inicializado en NULL

* PASOS CREAR:  Se crea el nodo -> El puntero del nodo apunta a tope de la pila -> el tope de la pila se apunta a la nueva posición.
* PASOS DESAPILA: Nodo auxilia que apunta al nodo a borrar -> Se mueve el tope al elemento anterior -> borras el nodo auxiliar(liberas).

##### Complejidad algoritmica

* Crear (Create) -> O(1).
* Apilar (Push) -> O(1).
* Destruir (Destroy) -> O(n).
* Desapilar (Pop) -> O(1).

# Introducción al TDA Lista
* Agrupa elementos, cada uno tiene un sucesor (menos el ultimo) y un antecesor (menos el primero).
* No tiene politica de acceso.
* Puedo usar la pila y la cola como un interfaz de la lista.
#### Operaciones del TDA Lista  
* Crear (Create).
* Insertar en una posición(insertAt).
* Vacia (isEmpty).
* Destruir (Destroy).
* Eliminar (DeleteAt).
* Ver elemento (Find).

#### ¿Cómo se implementan las listas?

* Vector estático.
* Vector dinámico.
* Lista de nodos.

#### Tipos de Listas:
##### Simple enlazada:
* Implementación con nodos.
* Cada uno con referencia al nodo siguiente
* Lista mantiene referencia al primer nodo.
* Procedimientos:
    - Al insertar:
        1. Apuntamos con el nuevo nodo al  siguiente.
        2. El nodo anterior, apunta al nuevo nodo.
     - Al borrar:
        1. Usamos un puntero auxiliar llamado nodo_a_borrar, y apuntamos al nodo a borrar.
        2. El nodo anterior de nodo_a_borrar apuntará al nodo siguiente de nodo_a_borrar.
        3. Borramos nodo_a_borrar.

###### Redimensión:
¿Cuándo reservo / libero memoria?

* Reservo memoria para cada nodo
* Libero memoria para cada nodo.

Ventaja:
* Memoria no debe ser contigua.

##### Doblemente enlazada:
* Referencia al sucesor y predecesor.
* Procedimientos:
    - Al insertar:
        1. Apuntamos con el nuevo nodo al anterior y al siguiente.
        2. El nodo siguiente, apunta al nuevo nodo.
        3. El nodo anterior  apunta al nuevo nodo.
    - Al borrar:
        1. Usamos un puntero auxiliar llamado nodo_a_borrar, y apuntamos al nodo a borrar.
        2. El nodo anterior de nodo_a_borrar apuntará al nodo siguiente de nodo_a_borrar.
        3. El nodo siguiente de nodo_a_borrar apuntará al nodo anterior de nodo_a_borrar.
        4. Borramos nodo_a_borrar.

##### Circular:
* El ultimo puntero apunta a principo. 
* Hay que tener en cuenta una condicion de corte.

* Iniciando la Lista :
    -  La lista inicia vacia.
    -  Cuando se agrega el primer nodo,este apunta al ultimo elemento.
    -  Primer elemento == último.