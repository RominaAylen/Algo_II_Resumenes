#TDA Iterador

#### Iterador:
* Es la capacidad de poder recorrer secuencialmente los datos almacenados en un TDA, sin tener que ser conciente la estructura del mismo.

* Se pueden realizar las siguientes operaciones:
    
    - Primero();
    - Siguiente();
    - HayMas();
    - ElementoActual();

#### Tipos de iteradores:

##### Internos:
* Permite recorrer todos lo elementos del TDA sin tener que controlar el ciclo en el cual se recorre el mismo. 
* Para ello un iterador interno es una funcion que recibe  tres parámetros:
    -    La lista.
    -    Un puntero a funcion, que recibe un dato como el contenido en el nodo, otro puntero extra por si la funcion lo requiere.
    -    Un puntero a void extra que funciona como memoria común. a todos los nodos visitados.

    void lista_iterar(lista_t *lista, bool visitar(void *dato, void *extra), void * extra);

 ##### Externos:
 * Es un TDA que provee un set de primitivas para recorrer una estructura(otro TDA). 
 * Se puede realizar con las siguientes operaciones:
    - Crear();
            
             struct iterador 
             {
                nodo_t *corriente;
                lista_t *lista;
             }

             iterador_t *iterador_crear(lista_t *lista)
             {
                if(!lista)
                
                return NULL;
                    
                    interador_t *resultado = malloc(sizeof(struct iterador));
                    
                    resultado->corriente = lista->inicio;
                    resultado->lista = lista;   // El iterador sabe de dinde vino
                
                return resultado;
             }
        
    - Primero();
    - Siguiente();
    - HaySiguiente();
    - ElementoActual();
* Puede ser implementado como un objeto opaco que mantiene un puntero a la lista.
    - El iterador mantiene el estado de iteración. Para que este avance hacia adelante, solo hay que pedirselo.
    -  El iterador debe conocer como esta representada la lista.
* La interfaz del iterador se refiere solo a las operaciones y quizas a a las restricciones de estas (Pre y post condiciones). 
* El iterador se define como un puntero al primer elemento de la lista y un puntero a un nodo actual.
* El iterador soportara las siguientes operaciones:
    - Chequea si el iterador esta posicionado al final de la lista.
    
            bool iterador_hay_siguiente(iterador_t *iterador)
            {
                return iterador->corriente->siguiente != NULL;
            }

    - Mover el iterador hacia adelante una posición.

            void iterador_siguiente(iterador_t *iterador)
            {
                if(iterador->corriente)
                    return iterador->corriente = iterador->corriente->siguiente;
            }

    - Obtener el elemento corriente.


            elemento_t iterador_elemento(iterador_t *elemento)
             {
                if(iterador->corriente)
                    return iterador->corriente->elemento;
             }


    - Eliminar el elemento corriente.
    - Resetear el iterador (Posicionarlo en la primera posición otra vez).
    
            void iterador_primero(iterador_t *iterador)
            {
                iterador->corriente = iterador->corriente->lista->inicio; 
            }
    - Liberar el espacio en el HEAP.
            
            void iterador_destruir(iterador_t *iterador)
            {
                free(iterador);
            }
###### El elemento corriente es el elemento al cual apunta el iterador en ese preciso instante.
* Para la implementación es necesario definir la estructura. Provocando intencionalmente que el usuario sepa la menor cantidad de detalles de la implementación.
                
    
        typedef struct interador_t;       //Va en el .h
        _________________________________________________
         
         struct iterador 
             {
                nodo_t *corriente;       // Va en el .c
                lista_t *lista;
             };

*L

