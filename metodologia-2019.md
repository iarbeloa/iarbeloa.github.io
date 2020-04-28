# De dónde salen estos números

En esta sección explico la metodología que sigo para estimar las posibilidades de ser presidente para cada candidato.

## Dos predicciones

El Congreso de los Diputados elige al presidente del gobierno. Para estimar las opciones de cada candidato a presidente, primero tenemos que estimar la composición del Congreso. Por lo tanto, realizo dos predicciones: La composición del Congreso y la elección del presidente.

Ambas predicciones son probabilísticas: El objetivo no es predecir con certeza quién ganará o qué mayoría habrá en el Congreso, sino cuantificar la incertidumbre. Quiero explicar la frecuencia con la que cada escenario puede darse en función de la información disponible. Las encuestas son un instrumento útil pero imperfecto: Primero, porque tienen un margen de error. Segundo, porque aunque fuesen altamente precisas en el momento actual, las cosas pueden cambiar de aquí al día de las elecciones. Tercero, porque el porcentaje de voto a nivel nacional no se traduce directamente en escaños, sino que pasa por el filtro de un sistema electoral con 52 circunscripciones. Y cuarto, porque aunque conociésemos la composición de la cámara, aún tendría que producirse una investidura para tener presidente.

Una respuesta a esas imperfecciones sería decir que no sabemos nada, que las encuestas no sirven y que la incertidumbre es total. Sin embargo eso es falso: Si un partido le saca 5 puntos al segundo en las encuestas a dos meses de las elecciones, es probable que gane las elecciones. Y si en vez de 5 son 8, entonces es aún más probable. Algo sí que sabemos.

Cuantificar la incertidumbre consiste en traducir la información imperfecta de las encuestas en la probabilidad de ocurrir que tiene cada escenario. Sabemos que es probable que el partido que saca 5 puntos al segundo gane, pero ¿cuánto de probable? ¿Es algo que ocurre 2 de cada 3 veces, o 19 de cada 20? Iré actualizando el modelo a diario durante las próximas semanas, lo que nos permitirá interpretar mejor los cambios que se vayan dando en las encuestas.

### Primer modelo: La composición del Congreso

El primer modelo toma como ingrediente las encuestas de intención de voto y genera una predicción sobre la composición del Congreso de los Diputados. El modelo esta elaborado a partir de los errores históricos de las encuestas en España, de la distribución del voto a cada partido en las diferentes provincias y de los cambios históricos en esa distribución.

[La metodología del primer modelo puede consultarse aquí.](https://www.inakiarbeloa.com/metodologia-del-primer-modelo-la-composicion-del-congreso/)

### Segundo modelo: La elección del presidente

El segundo modelo toma como ingrediente el resultado del primer modelo y genera una predicción sobre qué partido alcanzara la presidencia del gobierno. Este modelo está basado en un análisis exhaustivo de los distintos escenarios post-electorales posibles.

[La metodología del segundo modelo puede consultarse aquí.](https://www.inakiarbeloa.com/metodologia-del-segundo-modelo-la-eleccion-del-presidente-2/)