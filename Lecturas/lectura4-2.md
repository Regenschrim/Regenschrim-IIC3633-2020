# Lectura 4 - 2

El paper leído habla sobre una nueva forma de hacer clustering de textos basado en la frecuencia de las palabras dentro del texto y se compara respecto a otro métodos que trabajan con valores propios que requieren más cálculos para poder identificar los *clusters* dentro de un determinado texto (en concreto se menciona mucho el método de K-means).

Para evaluar los algoritmos usados, se tomaron dos datasets de documentos ya clasificados y se les aplicaron los diversos algoritmos. Para su comparación de resultados, se midió la *accuracy* y la *normalized mutual information*, en los cuales la versión del NMF que usa los pesos siempre obtenía mejores resultados en partícular (para distintos *k*) y en promedio.

La gracia que tiene el algoritmo presentado es que los vectores obtenidos para cada documento no es necesarios que sean ortogonales, ya que los *clusters* están respecto a cada eje de cada dimensión. Como en el ejemplo mostrado en el paper, los puntos se agrupan alrededor de los 3 ejes. Esto también genera un problema al trabajar con muchos *clusters* ya que la visualización no es posible debido a la cantidad de dimensiones que van a poseer los vectores.

Por otro lado, tiene sentido que la matriz solo tenga valores positivos, ya que como se menciona en el paper, un texto puede tratar sobre distintos temas y al final es una suma de distintas proporciones de los temas.

Como problema del algoritmo está el hecho de que se debe ejecutar varias veces para poder obtener un resultado que pueda servir, en el paper en particular se ejecutaron 10 intentos y esto se debe a que la NMF no asegura obtener el óptimo global cuando se ejecuta. Esto puede traer problemas en casos en que resultados nos den muy parecidos, ya que casi por "azar" tendríamos que buscar un valor que nos ayude a corroborar nuestra hipótesis. Si bien en este caso la diferencia es bastante como para decir que el algoritmo es mejor, en un caso con resultados más estrechos podríamos tener que ejecutar muchas veces el algoritmo sin obtener los resultados esperados.
