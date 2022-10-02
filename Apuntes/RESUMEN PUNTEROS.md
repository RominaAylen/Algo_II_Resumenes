# APUNTES DE PUNTEROS A UNA FUNCION

##### ¿Qué es un puntero?

* Un puntero es una variable que almacena una dirección de memoria (sabe la ubicación de donde esta localizado algo en memoria).
* Hay dos tipo de punteros:
    - Punteros a datos.
    - Punteros a funciones.
* Estos actuan distintos:
    ###### NO SE PUEDE CASTEAR UN PUNTEROA DATO PARA QUE SEA UN PUNTERO A FUNCION, NI VICEVERSA.

##### ¿Qué es un puntero a función?

* Un puntero es una variable que almacena una dirección de memoria de una función.
* Se unsan para que el codigo sea los mas generalizado y modularizado posible.
* Para tener un puntero a función, debemos conocer qué tipo de dato devuelve y que paramentros recibe.

#### Sintaxis:

La sintaxis a funciones no un usa el operadir '&' para acceder a memoria
 
##### ¿Cómo declarar un puntero a función?

     char obtener_letra(int numero, bool chequeo); //función
    
    - Una forma:
        char (*puntero_obtener_letra)(int,bool);
        puntero_obtener_letra = obtener_letra; //asignación
    
    - Otra forma:
        char (*puntero_obtener_letra)(int,bool) = obtener_letra; //Inicialización

##### ¿Cómo recibir un puntero a función por parámetro?

    void mostrar_letra (int repeticiones, char(*puntero_obtener_letra)(int, bool);

##### ¿Cómo invocar una función si tengo el puntero de la misma?

    char mi_litra = puntero_obtener_letra (180, true);

##### Vector de punteros a función:

    int* suma (int* primer_numero, int* segundo_numero);
    int* resta (int* primer_numero, int* segundo_numero);

    int* (funciones[2])(int*, int*) = {suma, resta};

##### ¿Como invocar una función de un vector de punteros a función?

######- Primera forma:
    
    tipo_de_dato mi_variable_resultado = vector_de_funciones[posicion](variable1, variable2);
   
    + Ejemplo:

    int* suma_total = funciones [i](valor1, valor2);

###### - Segunda forma:

    tipo_de_dato (*funcion_actual)(tipo_de_variable1, tipo_de_variable2) = vector_de_funciones[posicion];
    tipo_de_dato nombre_variable = funcion_actual(variable1, variable2);

    + Ejemplo:

    int* (*funcion_actual)(int*, int*) =  funciones[i];
    int* suma_total = funcion_actual(valor1, valor2);

