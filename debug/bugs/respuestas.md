En la primera compilacion sin frags no tiene información necesaria para 
ser interpretada por gdb
Una vez compilada con -g
El programa add_array_segfault.e
presenta errores a momentos de ejecución, ya que da como error 
Violación de segmento (`core' generado) 
Si corremos el programa con gdb con su comando run obtenemos 
0x000055555555470f in main (argc=1, argv=0x7fffffffda08)
    at add_array_segfault.c:19
19	    b[i] = i;
El problema esta en la linea 19, En b[i]. El cual se debe a que el 
arreglo no tiene definida su dimensión.    

En el programa ./add_array_nobugs.e
Da la respuesta que deberia tener errores y da como respuesta 6

En el programa ./add_array_dynamic.e
En mi maquina no da error, pero si existe, al hacer ir el for 
de add_array más alla de las dimenciones del array

En el programa ./add_attay_statics.c
Pasa lo mismo que dynamics.





