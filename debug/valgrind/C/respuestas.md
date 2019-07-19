para el programa       test_oob4.c     
compilado por 
gcc -g -O0 test_oob4.c -o test_oob4.e
corrido por 
valgrind --leak-check=full --track-origins=yes ./test_oob4.e
y analizando la memoria linkiada
==6301== LEAK SUMMARY:
==6301==    definitely lost: 280,000,000 bytes in 7 blocks
==6301==    indirectly lost: 0 bytes in 0 blocks
==6301==      possibly lost: 120,000,000 bytes in 3 blocks
==6301==    still reachable: 0 bytes in 0 blocks
==6301==         suppressed: 0 bytes in 0 blocks

da como resultado, que el programa pierde muchas memoria al creear 
las matices y no desalocaliarlas
                                           

para el caso del archivo source1.c 
El archivo valgrind no termino de correr despues de una hora de ser 
ejecutado. El problema es que nunca termina por un loop infinito.

for(;;) mat_Tmat_mul( A, C ); 

Lo que deberia haber pasado, es una acumulación de memoria por 
ese loop.


