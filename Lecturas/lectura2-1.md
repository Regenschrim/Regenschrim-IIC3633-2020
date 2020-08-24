# Lectura 2 - 1

En el paper se explica como fue desarrollado un sistema recomendador de programas de televisión utilizando *feedback implícito*. Se muestran varias características sobre este *feedback*:

- No feedback negativo.
- El *feedback implícito* es inherentemente ruidoso.
- El valor *feedback explícito* indica preferencia, el *feedback implícito* indica confianza.
- Hay que tener métricas apropiadas para este tipo de feedback.
- Es bueno asignar valores a todas las interacciones, ya que un cero igual supone información.

Para este estudio se utilizan varias métricas:
- **r<sub>ui</sub>:** indica la ocurrencia de eventos.
- **p<sub>ui</sub>:** indica preferencia por un elemento si su **r** es mayor a cero.
- **c<sub>ui</sub>:** función que mide el nivel de confianza de un dato **r**.

Se trabaja con vectores latentes para los usuarios e ítems, y en la fórmula que se busca optimizar se tiene en consideración la confianza de los datos (*c<sub>ui</sub>*) y un término regulador para evitar el *overfitting*.

La técnica detrá de estos es hacer una optimizaciónn de mínimos cuadrados cruzada, donde se alterna entre calcular los *user-factors* y los *item-factors*.

El problema que presenta este modelo según sus autores es que no hay explicación detrás de la recomendación. Sin embargo, al utilizar algebra en el cálculo de la predicción, se puede expresar esta en base a dos vectores latentes de ítems, lo que se traduce en la similaridad de dichos ítems.

En los resultados se puede observar que el algoritmo funciona bastante bien en comparación a una recomendación de los más vistos y un k-NN. Lo que se busca es que las mejores recomendaciones estén en un percentil bajo, ya que así se encuentran al principio de la lista de recomendaciones. Además, este modelo funciona mejor si se tiene en consideración información sobre programas ya vistos: es más fácil predecir si se volverá a ver un programa. En un última instancia una recomendación de algo que ya se vió puede ser un recordatorio para volver a verlo.

En general considero interesante el approach del trabajo. Me llamó bastante la atención la métrica que disminuye a medida que se pasa el tiempo, ya que es un caso super real el colocar el televisor para ver algo en particular y dejarlo encendido en el mismo canal.

Comparto el hecho de que el estudio de los hábitos para mirar televisión de un usuairo pueden ayudar mucho con la recomendación, ya que esto puede acotar las recomendaciones: si un usuario tiende a ver televisión solo en la noche y en la tarde por ejemplo, no tendría mucho sentido recomendarle un programa sea emitido en la mañana porque probablemente no lo vería. El problema es que este método también podría tener un *cold start* debido a que para conocer los hábitos de un usuario hay que tener información sobre este y si el usuario es nuevo, no hay información.

Creo que es super viable hacer un estudio sobre hábitos en los usuarios para ciertos tipos de recomendaciones, pero no sé en que medida afectaría esto a la complejidad de la data, los tiempos de ejecución y la definición del modelo.
