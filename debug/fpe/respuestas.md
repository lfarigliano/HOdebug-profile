Si corremos sin la opción DTRAPFPE me da un error en el programa 
square_root.c clavando la compilación 

para compilar square_root.c seguimos los siguientes pasos
gcc -c square_root.c -o square_root.o
gcc -c fpe_x87_sse.c -o fpe_x87_sse.o (en la carpeta fpe_x87_sse)
 finalmente linkeo 
gcc -DTRAPFPE -Ifpe_x87_sse/ square_root.o fpe_x87_sse/fpe_x87_sse.o -o square_root.e -lm
 
-DTRAPFPE -Ifpe_x87_sse/ (Para buscar .h en la carpeta)

  con todo este y ejecutandolo el resultado de sqrt(4/2) me da 1.414214

  Si se ejecuta ./comparison.e sin DTRAPFPE da como resultado 1.000 (pero no existe la divición pro cero)

  Si se ejecuta ./division.e sin DTRAPFPE da como resultado inf

  Si se ejecuta ./comparison.e con DTRAPFPE da como resultado 1.000 (pero no existe la divición pro cero)

  Si se ejecuta ./division.e con DTRAPFPEcon como resultado inf
