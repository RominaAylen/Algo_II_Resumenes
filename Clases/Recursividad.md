# Recursividad
#### ¿Qué es?

* Wikipedia: es la forma por la cual se especifica un proceso basado en su propia definicion.
* RAE: Dicho de una unidad o una estructura que puede contener como constituyente otra del mismo tipo.
* Asi nomas: Decimos que algo es recursivo si se conteiene a si mismo en una versión mas pequeña.

#### Tipos de recursividad.

##### Recursividad Directa:
El problema recursivo depende del problema recursivo.
- Sea R un problema recursivo
- Sea N el tamaño del problrma y M < N.     
            
        R(N) = f(R(M))

##### Recursividad Indirecta:
El problema recursivo depende del problema de otro recursivo.
- Sea R, Q un problemas recursivos.
- Sea N el tamaño del problema y O < M < N.    
        
        R(N) = f(Q(M))
        Q(M) = f(R(O))

##### Recursividad de cola:

Tail recursive
Es cuando la llamada recursiva a si misma es la ultima operación dentro de dicha función.

##### Dualidad Recursivo-Iterativo
Si yo tengo un algoritmo recursivo, lo puedo escribir de forma iterativa. 
Si tengo un algritmo itrativo, lo puedo escribir como un algoritmo recursivo.
###### Con mayor o menor complejidad

#### Ejemplo:
##### Lista recursiva

        typedef struct _lista{
            int elemento;
            struct _lista *siguiente;
        }lista_t

        /// CON CALLOC
        lista_t *lista_insertar(lista_t * lista, int elemento) 
        {
            if(!lista){
                lista_t *nueva_lista = calloc(1, sizeof(lista_t));
                    if(!nueva_lista)
                        return NULL;
                
                nueva_lista->elemento = elemento;
                
                return nueva_lista;
            }
            lista->siguiente = lista_insertar(lista->siguiente, elemento)
                
            return lista;
        }
        /// CON MALLOC
        lista_t *lista_insertar(lista_t * lista, int elemento) 
        {
            if(lista == NULL){
                lista_t *nueva_lista = malloc(sizeof(lista_t));
                    if(!nueva_lista)
                        return NULL;
                
                nueva_lista->elemento = elemento;
                nueva_lista->siguiente = NULL;
                
                return nueva_lista;
            }
            lista->siguiente = lista_insertar(lista->siguiente, elemento)
                
            return lista;
        }




        lista_t *lista_insertar_en_posicion(lista_t * lista, int n, int elemento) {
            if(lista == NULL || n == 0){
                lista_t *nueva_lista = malloc(sizeof(lista_t));
                if(!nueva_lista)
                    return NULL;
                nueva_lista->elemento = elemento;
                nueva_lista->siguiente = NULL;
                return nueva_lista;
            }
            lista->siguiente = lista_insertar_en posicion(lista->siguiente, n-1, elemento);
            return lista;
        }
        /// RECURSIVA DE COLA
        lista_t *lista_obtener_posicion(lista_t * lista, int n) 
        {
            if(lista == NULL)
                return -1;
            if(n == 0){
                return lista->elemento;
            }
            return lista_obtener_posicion(lista->siguiente, n-1);
        }
        int main (){
            lista_t * lista = NULL;
            
            lista = lista_insertar(lista, 5);
            lista = lista_insertar(lista, 8);
            lista = lista_insertar(lista, 9);
            lista = lista_insertar(lista, 1);
            lista = lista_insertar(lista, 2);


            return lista_obtener_posicion(lista, 100);
        }
