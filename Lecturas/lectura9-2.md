# Lectura 9 - 2

En este paper se centra en la implementación de un recomendador bandido con varias armas al igual que en el paper anterior. Se recomiendan playlist dentro de un plataforma móvil. El esquema recomendador se basa en realizar una recomendación de las playlist basado en la probabilidad de que el usuario haga stream de estas y en obtener un vector de recompensas dependiendo de si el usuario hizo realmente stream de la playlist en cuestión. Finalmente, la armas o "policies" se actualizan de acuerdo a esto.

Dentro de los resultados se encontró que los algoritmos que favorecían la recomendación semi-personalizada funcionaban mejor. Estos algoritmos funcionaban en base a clusters de usuarios según sus gustos musicales. Además, el approach de cascada también generaba mejor resultados que un apporach que no era cascada.

Por otro lado, no hay muchos datos respecto a la experimentación online debido a la confidencialidad de los datos. Sin embargo, se ve una tendencia de que los mejores métodos son los semi personalizados-cascada. Esto quizás se deba al hecho de que los usuarios colocados dentro de un mismo cluster tengan ciertos gustos parecidos y otros distintos, de esta forma tenemos una idea de que cosas podrían gustarles simplemente basandose en los usuarios que están dentro del mismo cluster.

Para este experimento se utilizaron vectores para representar a los usuarios, una suerte de user-based, pero me queda una duda de si quizás un approach en base a las playlist (artistas dentro de estas, canciones, etc) hubiese podido obtener mejores o peores resultados.
