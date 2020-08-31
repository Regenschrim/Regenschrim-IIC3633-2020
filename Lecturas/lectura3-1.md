# Lectura 3 - 1

En el paper se propone una nueva forma de realizar recomendaciones, la cual no se basa en minimizar el error de predicción. Además, se trabaja con un test set bien estructurado para evitar biases provenientes de ciertos ítems. La idea detrás de esto es recomendarle al usuario ítems a los que les puso un rating de 5 en base al resto de sus ratings, de esta forma sabemos si se están haciendo buenas recomendaciones.

El test set cuenta con todos los ítems a los que el usuario le dio un rating de 5:

- Para cada elemento del test, se toman 1000 ítems aleatorios que no hayan sido calificados y se asume que la mayoría no será del interés del usuario.

- Se predicen los ratings para los 1001 elementos.

- Se ordenan de acuerdo al rating. El mejor resultado es cuando el ítem con rating 5 supera a los otros 1000, es decir, cuando su posición (*p*) es igual a 1.

- Se genera un top-N de recomendaciones. Si *p <= N*, tenemos un *hit*, si no, tenemos un *miss*. La probabilidad de obtener un *hit* aumentan a medida que el valor de *N* aumenta.

Se toman dos medidas para hacer el análisis y ordenamiento de las recomendaciones: **recall** y **precision**. Estas medidas se hacen para cada test y hay un test por cada elemento con rating 5. **recall** mide los *hits* respecto a la cantidad de tests. Mientras que **precision** equivale al **recall** dividido por *N*: el porcentaje de *hits* de los test respecto a la cantidad de elementos a recomendar (*N*). Cabe mencionar que este cálculo subestima los valores reales de estas métricas.

A grandes rasgos se describe un modelo sencillo que proviene de factorizar matrices, utilizar factores latentes y dejar expresado a un usuario en función de los ítems que ha calificado (además de también considerar los ítems no calificados). Para los tests se hicieron tests con y sin los ítems más populares.

En general el PureSVD tiene mejores resultados que los otros algortimos. Se hace un distinción entre los tests con los ítems más populares y los que no los tienen: los con ítems populares necesitan menos factores latentes que los que no los tienen para obtener un valor óptimo. esto se cree que ocurre debido a que más factores latentes permiten descubrir las características específicas de los elementos que no son populares.

Si bien, es un modelo sencillo de implementar dicen que quedan cosas por revisar y posiblemente mejorar en un futuro. En lo personal me quedó como duda de donde obtenían el bias que utilizaban al calcular *r<sub>ui</sub>* y como interpretar los gráficos, ya que no me hace sentido que a medida que aumenta el **recall** (es decir, más *hits*) disminuya la **precision** (asumiendo que el valor de *N* se mantiene, si no es así, tiene sentido).

Es un buen approach al problema de recomendaciones ya que efectivamente no buscamos predecir el rating que le dará el usuario, sino indicarle elementos que tienen una alta probabilidad de ser de su preferencia y esto se consigue identificando al usuario respecto a sus gustos. Mi pregunta a punta a cómo condensan todos los resultados de los tests, ¿hacen una recomendación por cada test?, ¿toman los primeros *m* elementos de cada test y los agrupan y reordenan? Quizás el uso de *clusters* respecto a género o alguna otra característica podría generar una mejor recomendación y contraste entre ítems con cualidades similares.
