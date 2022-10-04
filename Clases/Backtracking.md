# Backtracking
#### ¿Que es?
* Es una forma de resolver problemas con recursividad.
* Es una técnica de resolución de problemas que explora recursivamente todas las soluciones posibles.
    -  Hay que saber cuales son las posibilidad de cada caso.
* Consiste en avanzar en una opcion de reesolución y cuando no logra poder resolverlo, vuelve para atras en la toma de decisión

#### Definición del problema del laberinto

* Laberintos: al ser una grilla cuadrada siempre hay opciones.
* Vuelve al punto de bifurcación mas cercano.

#### Escapando del laberinto

    #include <stdio.h>
    #include laberinto.h

    int explorar_laberinto(laberinto* lab){
        
        char bloque = mirar_posicion_actual(lab;)

        if(es_pared(bloque) || (es_marca(bloque)))
            return 0;

        if(es_salida(bloque))
            return 1;

        marcar_posicion_actual(lab);

        moverse(lab, -1, 0);
        if(explorar_laberinto(lab))
            return 1;

        moverse(lab, 2, 0);
        if(explorar_laberinto(lab))
            return 1;

        moverse(lab, -1, -1);
        if(explorar_laberinto(lab))
            return 1;
       
        moverse(lab, 0, 2);
        if(explorar_laberinto(lab))
            return 1;
        moverse(lab, -1, 0);
        
        return 0;
    }
    
    int main(int argc, char* argv[]){
        if(argc < 2){
            fprintf(stderr, "%s <archivo>\n", argv[0]);
        }
        laberinto* lab = crear_laberinto(argv[1]);

        if(lab){
            mostrar_laberinto(lab);
            explorar_laberinto(lab);
            mostrar_laberinto(lab);
        }

        destruir_laberinto(lab);
        return 1;
    }