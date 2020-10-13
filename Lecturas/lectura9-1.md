# Lectura 9 - 1

El paper trata sobre la implementación de una técnica para recomendar basada en la selección del algoritmo que haya tenido un mejor desempeño en la iteración anterior. Es decir, se creó un algoritmo que tiene a su disposición otros algoritmos de recomendación y de los cuales elige el mejor dependiendo del rendimiento que se ha obtenido hasta el momento. De este modo siempre tenemos "la mejor recomendación posible".

En particular para este experimento el "bandido" tenía a elegir entre KNN, factorización matricial y Most-Popular. Los resultados arrojaron que los métodos bandidos (que eran dos versiones) tenían mejor rendimiento que otros algortimos. Sin embargo, en el mismo paper indican que esto puede variar dependiendo de como es la etapa de entrenamiento de los algoritmos en cuánto a cantidad de datos que se usan y cuales son las "armas" del bandido.

Si bien, los resultados son favorables en este experimento en partícular, da la sensación de que la consistencia del buen rendimiento de esta técnica no esta asegurada. Se apegan demasiado al hecho de usar la factorización matricial y su comportamiento. Esto se ve reflejado en los últimos gráficos que presentan donde queda en evidencia que no siempre tendremos un buen desempeño. ¿Qué hubiese pasado si se realizaba el mismo experimento pero con otras "armas"? ¿sería igual de buena esta técnica?

Por otro lado, se destaca el descubrimiento de que este algoritmo utilice los items más populares en un principio para recomendar y así aprender respecto a los datos y de esta forma brindar una mejor recomendación a medida que pasan las épocas. También se podría preguntar que pasa si se cambia la cantidad de recomendaciones por época y ver como esto afecta al rendimiento en general.
