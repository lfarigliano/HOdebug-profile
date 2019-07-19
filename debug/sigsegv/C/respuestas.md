cuando compilo de entrada, se generan los archivos small.e y big.e, 
cuando se corre small.e no pasa nada, y cuando se corre big.e aparece 
Violación de segmento (`core' generado), y small.e no da ningun 
resultado.

al tipear ulimit -s unlimited
./small.e sigue sin pasar nada
./big.e se queda colgado el programa sin dar nada

  ulimit -s unlimite, tipear estos comandos en terminar me permite 
  cambiar el limite de memoria que los usuarios tienen asignados
  para ejetuar sus programas, dandole el valor que no tienen ninguna 
  restricción


  ulimit -a
  Me descripo los lugares de memoria, cambiando los valores por la 
  palabra unlimited


Cambiar el ulimit, no es una solución de  debugging, ya que no 
soluciona el problema, solamente permite correr el problema en 
esas condiciones.

una alternativa para solucionar el problema fue escribir el 
array temp de forma dinamica, lo que permitio utilizar array 
más grandes.(se deja de utilizar el stack, utilizando heap)

temp = (float *) malloc(SIZE * SIZE * sizeof(float));
