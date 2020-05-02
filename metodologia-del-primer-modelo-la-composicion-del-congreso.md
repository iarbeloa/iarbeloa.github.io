---
redirect_from: "/metodologia-del-primer-modelo-la-composicion-del-congreso/"
---
# Metodología del primer modelo: La composición del Congreso

## Paso 1: Agregar encuestas

El primer paso es recopilar todas las encuestas publicadas y calcular la media. En general, la media de las encuestas [se acerca más al resultado final](https://fivethirtyeight.com/features/the-polls-are-all-right/) que encuestas individuales. Para evitar sesgos, incluiré todas las encuestas que cumplan una serie de criterios decididos de antemano:
* La encuesta ha sido elaborada para un medio de comunicación conocido, por/para una institución publica, o por una institución educativa.
* La encuesta utiliza *cocina*. Es decir, incluye un modelo de estimación de voto.
* Está basada en entrevistas (telefónicas, personales o por Internet), con una muestra no auto-seleccionada.
* La ficha técnica incluye las fechas del trabajo de campo y el tamaño de la muestra.
* Han pasado menos de 90 días desde la fecha de la encuesta.
* En el caso de *trackers*, solo se incluyen encuestas en las que la muestra sea completamente distinta. Por ejemplo, si un medio publica un *tracker* diario de 600 entrevistas, con 200 entrevistas nuevas cada día, incluimos la encuesta más reciente, excluimos las dos anteriores, e incluimos la de hace 3 días.

Damos mayor importancia a las encuestas más recientes porque pueden capturar cambios en el electorado. Para conseguirlo, utilizo una formula de [decadencia exponencial](https://en.wikipedia.org/wiki/Exponential_decay), como hace [Nate Silver en *FiveThirtyEight*](https://fivethirtyeight.com/features/how-the-fivethirtyeight-senate-forecast-model-works/). La importancia de este factor aumenta conforme nos acercamos a las elecciones. Cuando faltan muchos días para la cita con las urnas, no queremos dar excesiva importancia a las encuestas más recientes, ya que las nuevas tendencias pueden revertirse por regresión a la media. Sin embargo, los cambios en los últimos días de la campaña tienen mayor importancia. Por eso, empezamos la fórmula de decadencia exponencial con un factor λ=40. Con este factor, una encuesta de hace 4 semanas tienen la mitad de peso que una encuesta hecha hoy. A partir de los 40 días para las elecciones, el factor λ comienza a decrecer de manera lineal hasta llegar a λ=10 a 10 días de las elecciones. A partir de entonces, una encuesta de hace una semana tiene la mitad de peso que una encuesta hecha hoy.

Utilizo un segundo ajuste para evitar que una única empresa de encuestas domine la media. Cuando la misma encuestadora ha publicado varias encuestas, el peso de cada encuesta es una quinta parte de lo que le correspondería, excepto la más reciente.

Otros promedios de encuestas incluyen más ajustes. Por ejemplo, tanto [Nate Silver en *FiveThirthyEight*](https://fivethirtyeight.com/features/how-the-fivethirtyeight-senate-forecast-model-works/) como [Kiko Llaneras en *El País*](https://elpais.com/politica/2018/11/28/actualidad/1543408692_128203.html) dan mayor peso a las encuestas con muestras grandes. Mi promedio es más simple y no utiliza este ajuste porque el valor marginal de ampliar la muestra desciende con rapidez. Es cierto que una muestra grande es mejor que una pequeña, pero el impacto es modesto. Nate Silver también da mayor peso a las encuestadoras que aciertan más. Este sería otro ajuste interesante para considerar en el futuro.

Cuando hablamos de la fecha de una encuesta, nos referimos al punto medio de su trabajo de campo.

## Paso 2: Simular las elecciones 5000 veces

Las encuestas fallan, así que no podemos quedarnos solo con el promedio: para interpretar bien las encuestas, hay que tener en cuenta cuánto suelen equivocarse.

Para responder a esta pregunta, he analizado 630 encuestas publicadas en los meses anteriores a todas las elecciones generales desde 1986 hasta 2016. A partir de esas encuestas, he calculado el promedio en 60 fechas distintas y he comparado cuánto suele desviarse el promedio de encuestas del resultado final.

El factor más importante para saber cuánto se equivocan las encuestas es el tamaño del partido: Las encuestas se equivocan muy poco con los partidos pequeños, apenas unas décimas (en parte porque muchos de ellos son regionales). Sin embargo, suelen fallar más con los partidos grandes. Otro factor relevante es el tiempo que falta para las elecciones: Es más fácil acertar cuando queda una semana que cuando faltan dos meses.

Simulo las elecciones 5000 veces para tener en cuenta la incertidumbre. En cada simulación introduzco errores aleatorios para cada partido en un sentido o en otro: a veces simulamos que las encuestas subestiman al partido y otras veces que lo sobrestiman. A veces el error es pequeño y otras veces es más grande. La media de los errores en las 5000 simulaciones se corresponde al error medio de las encuestas desde 1986, teniendo en cuenta el tamaño del partido y el tiempo que falta para las elecciones. La media de la estimación de voto para cada partido en las 5000 simulaciones se corresponde con la media de las encuestas.

Para estimar la distribución de los errores, utilizo [la distribución t de Student](https://es.wikipedia.org/wiki/Distribuci%C3%B3n_t_de_Student), que tiene una forma similar a la distribución normal pero otorga más probabilidad a casos extremos. Esto nos permitiría anticipar mejor errores extremos en las encuestas, como las andaluzas de 2018, las europeas de 2014 o las gallegas de 2012. Nate Silver [utiliza esta distribución](https://fivethirtyeight.com/features/election-update-why-our-model-is-more-bullish-than-others-on-trump/) en sus modelos de predicción electoral.

## Paso 3: Estimar el voto en cada provincia

Al terminar el Paso 2, tenemos los resultados de 5000 elecciones distintas a nivel nacional, pero aún no sabemos cuántos escaños tendría cada partido en cada una de las 5000 simulaciones. Para calcular escaños, necesitamos estimar el voto en cada provincia. Uso un método muy parecido al que describe Alberto Penadés en [*La cocina electoral en España*](https://www.catarata.org/libro/la-cocina-electoral-en-espana_93255/). La suposición principal es que el cambio del voto (*swing*) será uniforme en todo el país. Es decir, si un partido sube 4 puntos a nivel nacional con respecto a las últimas elecciones, asumo que subirá 4 puntos en todas las provincias.

Al igual que las encuestas, este método es imperfecto. Por eso, hemos calculado cuánto suele equivocarse analizando todas las elecciones generales desde 1979. Incluso sabiendo el resultado final a nivel nacional, el método habría fallado entre 2 y 3 puntos de media a nivel provincia. Cuando estimo el voto en cada provincia, tengo esto en cuenta e introduzco errores aleatorios.

Estos errores son especialmente preocupantes porque las provincias no son independientes (en el sentido estadístico), sino que se comportan parecido a provincias similares. Por ejemplo, si un partido baja a nivel nacional pero sube en Albacete, es probable que también suba en Ciudad Real. Por eso, he agrupado provincias con comportamiento electoral similar con respecto al voto nacional. Parte de los errores aleatorios de la estimación provincial se calcula a nivel grupo. Los grupos son los siguientes:
* A Coruña, Lugo, Ourense, Pontevedra
* Álava/Araba, Bizkaia, Gipuzkoa
* Albacete, Ciudad Real, Cuenca, Guadalajara, Toledo
* Alicante, Murcia, Valencia
* Ávila, Burgos, La Rioja, Palencia, Segovia, Soria
* Badajoz, Cáceres
* Barcelona, Girona, Lleida, Tarragona
* Cádiz, Córdoba, Málaga, Sevilla
* Granada, Huelva
* Huesca, Teruel

Para poder usar el método, realizamos algunos ajustes:

### Partidos regionales
En el caso de los partidos regionales (Coalición Canaria, ERC, PNV, etc.), primero ajustamos el promedio de encuestas nacionales para estimar el voto en el territorio en el que se presentan, y a partir de ahí calculamos el *swing* con respecto a las elecciones anteriores.

### Vox
Vox apenas obtuvo votos en las elecciones de 2016, por lo que este método no puede aplicarse. Para estimar la distribución territorial del voto de Vox, utilizo la suma de PP y Ciudadanos en 2016 como *proxy*. Esta suma es el mejor predictor del voto de Vox en las andaluzas de diciembre. Además, varias encuestas sobre flujos de voto muestran que Vox se nutre principalmente del electorado de PP y Ciudadanos y que ambos partidos pierden porcentajes similares de sus electorados respectivos en beneficio de Vox.  Para estimar el voto de Vox en cada provincia necesitamos un punto de referencia, así que pretendemos que en 2016 Vox obtuvo el 10% del voto, que ese voto se distribuyó geográficamente igual que la suma de PP y Ciudadanos, y que esos votantes salieron en proporciones similares de PP y de Ciudadanos. La suposición del 10% del voto solo afecta a la distribución territorial: para estimar el voto nacional de cara a estas elecciones utilizo el promedio de encuestas.

### Comunidad Valenciana
En 2016, Compromís y Podemos se presentaron juntos en la Comunidad Valenciana, pero en 2019 se presentan por separado. Para saber qué proporción del voto corresponde a Podemos y qué proporción a Compromís, utilizo las autonómicas de 2015 como referencia. En esas elecciones, Compromís obtuvo el 68% de la suma Compromís+Podemos en Valencia, el 55% en Castellón y el 51% en Alicante. Este método es arriesgado porque el voto en las elecciones autonómicas suele beneficiar a partidos de ámbito autonómico, por lo que quizás estemos sobrestimando a Compromís y subestimando a Podemos. La coincidencia de las elecciones autonómicas con las generales disipa en parte esa preocupación.

### Galicia
En Galicia ha ocurrido una ruptura similar entre En Marea y Podemos. Este caso es distinto porque las dos formaciones nunca han competido directamente, por lo que no tenemos un punto de referencia para saber cuántos votantes irán con En Marea y cuántos con Podemos. De momento, [las encuestas](https://www.lavozdegalicia.es/noticia/elecciones/2019/03/23/centroderecha-gana-izquierda-galicia-pese-remontada-socialistas/00031553367812157389682.htm) no han separado a los dos partidos, por lo que no tenemos ningún dato para saber cómo se repartirá el voto. Por ahora, asumo una división del 50% para cada uno, pero revisaré esta cifra cuando se publiquen más encuestas en Galicia.

*Actualización: La encuesta de Celeste-Tel [publicada el 5 de abril en El Diario](https://www.eldiario.es/politica/mantiene-Ciudadanos-perderia-votantes-Vox_0_885062121.html) separa por primera vez el voto a Podemos en Galicia de En Marea. En esta encuesta, En Marea recibe un 70% del reparto y UP un 30%. A partir del 6 de abril utilizaremos estos porcentajes.*

### Navarra
En Navarra UPN, PP y Ciudadanos se presentan en coalición bajo el nombre Navarra Suma. Mi modelo primero estima cuántos votos obtendrían por separado (UPN+PP por un lado, Ciudadanos por otro), y después suma los dos bloques antes del reparto de escaños. En el reparto de escaños, asigno a UPN los dos primeros escaños, al PP el tercero y el quinto, y a Ciudadanos el cuarto.

## Paso 4: Calcular escaños

Al completar el Paso 3, tenemos resultados a nivel provincial para las 5000 elecciones simuladas. Para terminar, calculo cómo se repartirían los escaños en cada provincia si se diese ese resultado. Utilizo el [método d'Hondt](https://es.wikipedia.org/wiki/Sistema_D%27Hondt) y establezco una barrera de entrada del 3%. La suma de todas las provincias nos da 5000 composiciones del Congreso de los Diputados, todas ellas igualmente posibles.

*Para consultar la metodología del segundo modelo, haz click [aquí](https://www.inakiarbeloa.com/metodologia-del-segundo-modelo-la-eleccion-del-presidente-2).*