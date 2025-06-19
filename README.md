**Table of content:**

1. [Ejercicio 1: Busqueda en profundidad](#ejercicio1)
2. [Ejercicio 2: ejercicio 1 limitando la profundidad a 6](#limite6)
3. [Ejercicio 3: Busceda por coste uniforme](#uniforme)
4. [jercicio 4: Busqueda con algoritmo A A*](#asterisco)






# Ejercicio 1: Busqueda en profundidad <a name="ejercicio1"></a>

![esquema ejercicio 1.jpg](https://github.com/PabloRodriguezLomba/Ejercicios_MIA/blob/main/capturas/esquema%20ejercicio%201.jpg)

en este esquema podemos ver el mundo o entorno del problema y como acabara cuando se expanda y complete el algoritmo de profundidad.

resultados:

Paso 1 C= {i} F= {A,B} \
Paso 2 C= {i,B} F= {A,C,D} Test(B) \
Paso 3 C= {i,B,D} F= {A,C} Test(D) \
Paso 4 C= {i,B,D,C} F= {A,E} Test(C) \
Paso 5 C= {i,B,D,C,E} F= {A,F,G} Test(E) \
Paso 6 C= {i,B,D,C,E,G} F= {A,F,H} Test(G) \
Paso 7 C= {i,B,D,C,E,G,H} F= {A,F,I} Test(H) \
Paso 8 C= {i,B,D,C,E,G,H,I} F= {A,F,J} Test(I) \
Paso 9 C= {i,B,D,C,E,G,H,I,J} F= {A,F,K,L} Test(J) \
Paso 10 C= {i,B,D,C,E,G,H,I,J,L} F= {A,F,K,M} Test(M) \
Paso 11 C= {i,B,D,C,E,G,H,I,J,L,M} F= {A,F,K,N,e} Test(e) \
solucion: \
  C={i,B,D,C,E,G,H,I,J,L,M,e} F = {A,F,K,N} 

Este es el arbol resultante:

![arbol](https://github.com/PabloRodriguezLomba/Ejercicios_MIA/blob/main/capturas/arbol_ejercicio_1.jpg)


# Esto es el ejercicio limitando la profundidad a 6 <a name="limite6"></a>

![esquema_alternativo](https://github.com/PabloRodriguezLomba/Ejercicios_MIA/blob/main/capturas/Esquema_alternativo_ejercicio1.jpg)

resultados:

Paso 7 C= {i,B,D,C,E,G,H,F} F= {A} \
Paso 7 C= {i,B,D,C,E,G,H,F,A} F= {I,J} Test(A) \
Paso 7 C= {i,B,D,C,E,G,H,F,A,J} F= {I,K} Test(J) \
Paso 7 C= {i,B,D,C,E,G,H,F,A,J,K} F= {I,L} Test(K) \
Paso 7 C= {i,B,D,C,E,G,H,F,A,J,K,L} F= {I,M,N} Test(L) \
Paso 7 C= {i,B,D,C,E,G,H,F,A,J,K,L,N} F= {I,M,Ñ,e} Test(N) \
Paso 7 C= {i,B,D,C,E,G,H,F,A,J,K,L,N,e} F= {I,M,Ñ} Test(e) \

solucion:

Paso 7 C= {i,B,D,C,E,G,H,F,A,J,K,L,N,e} F= {I,M,Ñ}

y este es el arbol que se genera

![arbol_alternativo](https://github.com/PabloRodriguezLomba/Ejercicios_MIA/blob/main/capturas/Arbol_ejercicio_1_alternativo.jpg)


 # Ejercicio 3 : Busceda por coste uniforme <a name="uniforme"></a>


 resultados:

 Paso 1: E= {Ourense<sub><sup><sup>0</sup></sup></sub>} F= {Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>),Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>)} 
 
 Paso 2: E= {Ourense<sub><sup><sup>0</sup></sup></sub>,Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>)} F= {Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>),Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>),Benavente<sub><sup><sup>300</sup></sup></sub>(<sub>Ponferrada</sub>)} Test(Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>)) 
 
 Paso 3: \
   &emsp;E= {Ourense<sub><sup><sup>0</sup></sup></sub>,Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>),Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>)} <br /> 
   &emsp;F= {Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>),Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>),Valladolid<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),Palencia<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>)} \
   &emsp;Test(Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>))

 Paso 4: \
   &emsp;E= {Ourense<sub><sup><sup>0</sup></sup></sub>,Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>),Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>),Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>)} <br /> 
   &emsp;F= {Valladolid<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),Palencia<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),Osorno<sub><sup><sup>409</sup></sup></sub>(<sub>Leon</sub>)} \
   &emsp;Test(Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>))

 Paso 5: \
   &emsp;E= {Ourense<sub><sup><sup>0</sup></sup></sub>,Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>),Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>),Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>),Valladolid<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>)} <br /> 
   &emsp;F= {Palencia<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),Osorno<sub><sup><sup>409</sup></sup></sub>(<sub>Leon</sub>),Aranda<sub><sup><sup>443</sup></sup></sub>(<sub>Valladolid</sub>)} \
   &emsp;Test(Valladolid<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>))
   
 Paso 6: \
   &emsp;E= {Ourense<sub><sup><sup>0</sup></sup></sub>,Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>),Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>),Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>),Valladolid<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),Palencia<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>)} <br /> 
   &emsp;F= {Osorno<sub><sup><sup>409</sup></sup></sub>(<sub>Leon</sub>),Aranda<sub><sup><sup>443</sup></sup></sub>(<sub>Valladolid</sub>),Osorno<sub><sup><sup>397</sup></sup></sub>(<sub>Palencia</sub>),Burgos<sub><sup><sup>440</sup></sup></sub>(<sub>Palencia</sub>)} \
   &emsp;Test(Palencia<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>))      

 Paso 7: \
   &emsp;E= {Ourense<sub><sup><sup>0</sup></sup></sub>,Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>),Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>),Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>),Valladolid<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),Palencia<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>), <br /> 
   &emsp;&emsp;Osorno<sub><sup><sup>397</sup></sup></sub>(<sub>Palencia</sub>)} <br /> 
   &emsp;F= {Aranda<sub><sup><sup>443</sup></sup></sub>(<sub>Valladolid</sub>),Burgos<sub><sup><sup>440</sup></sup></sub>(<sub>Palencia</sub>),Burgos<sub><sup><sup>456</sup></sup></sub>(<sub>Osorno</sub>)} \
   &emsp;Test(Osorno<sub><sup><sup>397</sup></sup></sub>(<sub>Palencia</sub>))

 Paso 8: \
   &emsp;E= {Ourense<sub><sup><sup>0</sup></sup></sub>,Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>),Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>),Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>),Valladolid<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),Palencia<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>), <br /> 
   &emsp;&emsp;Osorno<sub><sup><sup>397</sup></sup></sub>(<sub>Palencia</sub>),Burgos<sub><sup><sup>440</sup></sup></sub>(<sub>Palencia</sub>)} <br /> 
   &emsp;F= {Aranda<sub><sup><sup>443</sup></sup></sub>(<sub>Valladolid</sub>),Aranda<sub><sup><sup>529</sup></sup></sub>(<sub>Burgos</sub>),Soria<sub><sup><sup>583</sup></sup></sub>(<sub>Burgos</sub>),Logroño<sub><sup><sup>590</sup></sup></sub>(<sub>Burgos</sub>)} \
   &emsp;Test(Burgos<sub><sup><sup>440</sup></sup></sub>(<sub>Palencia</sub>))

 Paso 9: \
   &emsp;E= {Ourense<sub><sup><sup>0</sup></sup></sub>,Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>),Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>),Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>),Valladolid<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),Palencia<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),  <br /> 
   &emsp;&emsp;Osorno<sub><sup><sup>397</sup></sup></sub>(<sub>Palencia</sub>),Burgos<sub><sup><sup>440</sup></sup></sub>(<sub>Palencia</sub>),Aranda<sub><sup><sup>443</sup></sup></sub>(<sub>Valladolid</sub>)} <br /> 
   &emsp;F= {Soria<sub><sup><sup>583</sup></sup></sub>(<sub>Burgos</sub>),Logroño<sub><sup><sup>590</sup></sup></sub>(<sub>Burgos</sub>),Osma<sub><sup><sup>501</sup></sup></sub>(<sub>Aranda</sub>)} \
   &emsp;Test(Aranda<sub><sup><sup>443</sup></sup></sub>(<sub>Valladolid</sub>))

 Paso 10: \
   &emsp;E= {Ourense<sub><sup><sup>0</sup></sup></sub>,Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>),Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>),Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>),Valladolid<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),  <br /> 
   &emsp;&emsp;Palencia<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),Osorno<sub><sup><sup>397</sup></sup></sub>(<sub>Palencia</sub>),Burgos<sub><sup><sup>440</sup></sup></sub>(<sub>Palencia</sub>),Aranda<sub><sup><sup>443</sup></sup></sub>(<sub>Valladolid</sub>),Osma<sub><sup><sup>501</sup></sup></sub>(<sub>Aranda</sub>)} <br /> 
   &emsp;F= {Soria<sub><sup><sup>583</sup></sup></sub>(<sub>Burgos</sub>),Logroño<sub><sup><sup>590</sup></sup></sub>(<sub>Burgos</sub>),Calatayud<sub><sup><sup>641</sup></sup></sub>(<sub>Osma</sub>),Soria<sub><sup><sup>559</sup></sup></sub>(<sub>Osma</sub>)} \
   &emsp;Test(Osma<sub><sup><sup>501</sup></sup></sub>(<sub>Aranda</sub>)) 

 Paso 11: \
   &emsp;E= {Ourense<sub><sup><sup>0</sup></sup></sub>,Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>),Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>),Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>),Valladolid<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),Palencia<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>), <br /> 
   &emsp;&emsp;Osorno<sub><sup><sup>397</sup></sup></sub>(<sub>Palencia</sub>),Burgos<sub><sup><sup>440</sup></sup></sub>(<sub>Palencia</sub>),Aranda<sub><sup><sup>443</sup></sup></sub>(<sub>Valladolid</sub>),Osma<sub><sup><sup>501</sup></sup></sub>(<sub>Aranda</sub>),Soria<sub><sup><sup>559</sup></sup></sub>(<sub>Osma</sub>),Logroño<sub><sup><sup>590</sup></sup></sub>(<sub>Burgos</sub>)} <br /> 
   &emsp;F= {Calatayud<sub><sup><sup>641</sup></sup></sub>(<sub>Osma</sub>),Calatayud<sub><sup><sup>650</sup></sup></sub>(<sub>Soria</sub>)} \
   &emsp;Test(Logroño<sub><sup><sup>590</sup></sup></sub>(<sub>Burgos</sub>)) 

 Solucion: \
   &emsp;E={Ourense<sub><sup><sup>0</sup></sup></sub>,Ponferrada<sub><sup><sup>175</sup></sup></sub>(<sub>Ourense</sub>),Benavente<sub><sup><sup>236</sup></sup></sub>(<sub>Ourense</sub>),Leon<sub><sup><sup>288</sup></sup></sub>(<sub>Ponferrada</sub>),Valladolid<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>),Palencia<sub><sup><sup>348</sup></sup></sub>(<sub>Benavente</sub>), <br /> 
   &emsp;&emsp;Osorno<sub><sup><sup>397</sup></sup></sub>(<sub>Palencia</sub>),Burgos<sub><sup><sup>440</sup></sup></sub>(<sub>Palencia</sub>),Aranda<sub><sup><sup>443</sup></sup></sub>(<sub>Valladolid</sub>),Osma<sub><sup><sup>501</sup></sup></sub>(<sub>Aranda</sub>),Soria<sub><sup><sup>559</sup></sup></sub>(<sub>Osma</sub>),Logroño<sub><sup><sup>590</sup></sup></sub>(<sub>Burgos</sub>),Calatayud<sub><sup><sup>641</sup></sup></sub>(<sub>Osma</sub>)} <br /> 
   &emsp;F= {} \
   &emsp;Test(Calatayud<sub><sup><sup>641</sup></sup></sub>(<sub>Osma</sub>))



# Ejercicio 4: Busqueda con algoritmo A A* <a name="asterisco"></a>


![esquema](https://github.com/PabloRodriguezLomba/Ejercicios_MIA/blob/main/capturas/esquema_ejercicio_A.jpg)

 f = h + g 

<sub>g h</sub>N<sup>f</sup>   

g = al gasto necesario para moverse en el entorno , un movimiento vertical es igual a 1 y un moviemiento horizontal es igual a 2
h = la distancia mas corta entre el nodo y el objetivo , esta sin importar los obstaculos o limitaciones <br />
f = a la suma de h + g, el total

resultados:

Paso 1: E= {<sub>0 4</sub>i<sup>4</sup>}&emsp;F = {<sub>1 3</sub>A<sup>4</sup>(i), <sub>1 5</sub>B<sup>6</sup>(i)}

Paso 1: E= {<sub>0 4</sub>i<sup>4</sup>,<sub>1 3</sub>A<sup>4</sup>(i)}&emsp;F = {<sub>1 5</sub>B<sup>6</sup>(i) , <sub>3 2</sub>C<sup>5</sup>(A) , <sub>3 4</sub>D<sup>7</sup>(A)}&emsp;Test(<sub>1 3</sub>A<sup>4</sup>(i))

Paso 1: E= {<sub>0 4</sub>i<sup>4</sup>, <sub>1 3</sub>A<sup>4</sup>, <sub>3 2</sub>C<sup>5</sup>(A)}&emsp;F = {<sub>1 5</sub>B<sup>6</sup>(i) , <sub>3 4</sub>D<sup>7</sup>(A) ,}&emsp;Test(<sub>1 3</sub>A<sup>4</sup>(i))

Paso 1: E= {<sub>0 4</sub>i<sup>4</sup>, <sub>1 3</sub>A<sup>4</sup>, <sub>3 2</sub>C<sup>5</sup>(A), <sub>1 5</sub>B<sup>6</sup>(i)}&emsp;F = {<sub>3 4</sub>D<sup>7</sup>(A) , <sub>3 4</sub>E<sup>7</sup>(B), <sub>3 6</sub>F<sup>9</sup>(B)}&emsp;Test(<sub>1 5</sub>B<sup>6</sup>(i))

Paso 1: E= {<sub>0 4</sub>i<sup>4</sup>, <sub>1 3</sub>A<sup>4</sup>, <sub>3 2</sub>C<sup>5</sup>(A), <sub>1 5</sub>B<sup>6</sup>(i), <sub>3 4</sub>D<sup>7</sup>(A) }&emsp;F = {<sub>3 4</sub>E<sup>7</sup>(B), <sub>3 6</sub>F<sup>9</sup>(B), <sub>4 3</sub>G<sup>7</sup>(D) }&emsp;Test(<sub>3 4</sub>D<sup>7</sup>(A))

Paso 1: E= {<sub>0 4</sub>i<sup>4</sup>, <sub>1 3</sub>A<sup>4</sup>, <sub>3 2</sub>C<sup>5</sup>(A), <sub>1 5</sub>B<sup>6</sup>(i), <sub>3 4</sub>D<sup>7</sup>(A) , <sub>3 4</sub>E<sup>7</sup>(B)}&emsp;F = {<sub>3 6</sub>F<sup>9</sup>(B), <sub>4 3</sub>G<sup>7</sup>(D), <sub>5 5</sub>H<sup>10</sup>(E) }&emsp;Test(<sub>3 4</sub>E<sup>7</sup>(B))

Paso 1: E= {<sub>0 4</sub>i<sup>4</sup>, <sub>1 3</sub>A<sup>4</sup>, <sub>3 2</sub>C<sup>5</sup>(A), <sub>1 5</sub>B<sup>6</sup>(i), <sub>3 4</sub>D<sup>7</sup>(A) , <sub>3 4</sub>E<sup>7</sup>(B), <sub>4 3</sub>G<sup>7</sup>(D)}&emsp;F = {<sub>3 6</sub>F<sup>9</sup>(B), <sub>5 5</sub>H<sup>10</sup>(E), <sub>5 2</sub>I<sup>7</sup>(G) }&emsp;Test(<sub>4 3</sub>G<sup>7</sup>(D))

Paso 1: E= {<sub>0 4</sub>i<sup>4</sup>, <sub>1 3</sub>A<sup>4</sup>, <sub>3 2</sub>C<sup>5</sup>(A), <sub>1 5</sub>B<sup>6</sup>(i), <sub>3 4</sub>D<sup>7</sup>(A) , <sub>3 4</sub>E<sup>7</sup>(B), <sub>4 3</sub>G<sup>7</sup>(D), <sub>5 2</sub>I<sup>7</sup>(G) }&emsp;F = {<sub>3 6</sub>F<sup>9</sup>(B), <sub>5 5</sub>H<sup>10</sup>(E), <sub>6 3</sub>J<sup>9</sup>(I), <sub>7 1</sub>K<sup>8</sup>(I)}&emsp;Test(<sub>5 2</sub>I<sup>7</sup>(G))

Paso 1: E= {<sub>0 4</sub>i<sup>4</sup>, <sub>1 3</sub>A<sup>4</sup>, <sub>3 2</sub>C<sup>5</sup>(A), <sub>1 5</sub>B<sup>6</sup>(i), <sub>3 4</sub>D<sup>7</sup>(A) , <sub>3 4</sub>E<sup>7</sup>(B), <sub>4 3</sub>G<sup>7</sup>(D), <sub>5 2</sub>I<sup>7</sup>(G), <sub>7 1</sub>K<sup>8</sup>(I) }&emsp;F = {~~<sub>3 6</sub>F<sup>9</sup>(B)~~, <sub>5 5</sub>H<sup>10</sup>(E), ~~<sub>6 3</sub>J<sup>9</sup>(I)~~, <sub>8 2</sub>L<sup>10</sup>(K), <sub>9 0</sub>e<sup>9</sup>(K) }&emsp;Test(<sub>7 1</sub>K<sup>8</sup>(I))

Solucion:


Paso 1: E= {<sub>0 4</sub>i<sup>4</sup>, <sub>1 3</sub>A<sup>4</sup>, <sub>3 2</sub>C<sup>5</sup>(A), <sub>1 5</sub>B<sup>6</sup>(i), <sub>3 4</sub>D<sup>7</sup>(A) , <sub>3 4</sub>E<sup>7</sup>(B), <sub>4 3</sub>G<sup>7</sup>(D), <sub>5 2</sub>I<sup>7</sup>(G), <sub>7 1</sub>K<sup>8</sup>(I), <sub>9 0</sub>e<sup>9</sup>(K)  }&emsp;F = {<sub>5 5</sub>H<sup>10</sup>(E), <sub>8 2</sub>L<sup>10</sup>(K)}&emsp;Test(<sub>9 0</sub>e<sup>9</sup>(K) )

Este es el arbol resultante:

![arbol](https://github.com/PabloRodriguezLomba/Ejercicios_MIA/blob/main/capturas/Arbol%20de%20ejercicio%201%20mediante%20A.jpg)
