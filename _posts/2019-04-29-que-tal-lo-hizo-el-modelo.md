---
permalink: /que-tal-lo-hizo-el-modelo/
---
# ¿Qué tal lo hizo el modelo?

Empezamos este ejercicio hace un mes con el objetivo [declarado](https://www.inakiarbeloa.com/metodologia-2019) de "cuantificar la incertidumbre". Partíamos de la premisa de que no podemos saber qué ocurrirá con certeza, pero podemos organizar la información disponible para saber la probabilidad de ocurrir de varias situaciones. Las encuestas son un instrumento imperfecto y se equivocan con frecuencia, pero no son puro ruido: contienen información valiosa. El objetivo es traducir la información imperfecta de las encuestas en predicciones probabilísticas.

## La predicción del Congreso

El modelo funcionó bien. Los resultados de todos los partidos entraron dentro de las horquillas de predicción:
<div>
    <a href="https://plot.ly/~iarbeloa/28/?share_key=WB6cVbR8Lg96iwluAD9a5y" target="_blank" title="Escaños_todos copy" style="display: block; text-align: center;"><img src="https://plot.ly/~iarbeloa/28.png?share_key=WB6cVbR8Lg96iwluAD9a5y" alt="Escaños_todos copy" style="max-width: 100%;width: 900px;"  width="900" onerror="this.onerror=null;this.src='https://plot.ly/404.png';" /></a>
</div>

Llama la atención el resultado del PP, que entra dentro la horquilla por la mínima. Este resultado reivindica el uso de horquillas amplias: Las encuestas sobreestimaron al PP, pero el modelo tuvo en cuenta esta posibilidad y estimó que los 66 escaños entraban dentro de esta horquilla del 80% de probabilidad.

## Las encuestas

Las encuestas acertaron con una excepción: No capturaron el desplome del PP, al que daban 4 puntos más de los que obtuvo. Un error de 4 puntos es bastante habitual. Sin ir mas lejos, en las últimas elecciones el mismo Partido Popular sufrió un error de 4 puntos, aunque en la dirección contraria: las encuestas le subestimaron. La utilidad de este tipo de modelos reside precisamente en anticipar estas situaciones y ayudarnos a interpretar mejor las encuestas.

![](/images/04.2019_general_election_forecast/posts/2019-04-29-postmortem-encuestas.png)

En los últimos días antes de las elecciones, muchos auguraban con convicción una enorme subida de Vox por encima de las encuestas. Este augurio se basaba más en la intuición y los rumores que en evidencia empírica. El resultado de Vox es una victoria de las encuestas sobre las corazonadas. Las encuestas son solo una aproximación, pero son un instrumento objetivo, empírico y frío que ayudan a mantener a raya nuestras subjetividades humanas.

No es la primera vez: Al contrario de lo que se suele decir, las encuestas avisaron que el referendum del Brexit [estaba apretado](https://www.economist.com/graphic-detail/2016/06/24/who-said-brexit-was-a-surprise) y que la victoria de Trump era [muy posible](https://projects.fivethirtyeight.com/2016-election-forecast/), pero la intuición colectiva nos traicionó.

## La predicción del presidente

Un rasgo diferenciador de mi modelo de predicción es el intento de pronosticar quién será presidente. Este experimento intenta superar una de las limitaciones de los modelos de predicción en sistemas parlamentarios multipartidistas: Los escaños de cada partido no bastan para saber quién gobernará. Ni siquiera basta con saber los escaños de las diferentes coaliciones posibles, ya que también importan las interacciones entre diferentes coaliciones: El escenario cambia dependiendo de si el PSOE tiene dos coaliciones posibles (UP+nacionalistas por un lado y Ciudadanos por otro) o si tiene solo una opción.

El pronóstico del presidente tiene muchas limitaciones y elementos subjetivos, que se pueden consultar en [su metodología](https://www.inakiarbeloa.com/metodologia-del-segundo-modelo-la-eleccion-del-presidente-2). En algunos casos, aun sabiendo la composición exacta del parlamento no podemos saber quién acabará siendo investido. Sin embargo, en muchos escenarios el ganador está claro, y en los demás casos podemos identificar elementos objetivos que refuerzan o debilitan las opciones de cada candidato.

El modelo estimaba que Pedro Sánchez tenía 2 entre 3 posibilidades de conseguir la reelección. El favorito del modelo será presidente del gobierno, por lo que a ojos de muchos "ha acertado".
<div>
    <a href="https://plot.ly/~iarbeloa/9/?share_key=q3hyXFXJEwUXJsQfZs06i3?width=100%" target="_blank" title="Plot 9" style="display: block; text-align: center;"><img src="https://plot.ly/~iarbeloa/9.png?share_key=q3hyXFXJEwUXJsQfZs06i3" alt="Plot 9" style="max-width: 100%;width: 3000px;"  width="3000" onerror="this.onerror=null;this.src='https://plot.ly/404.png';" /></a>
</div>

¡Ojo! El modelo no decía que Sánchez sería presidente con total certeza. Si el modelo está bien calibrado, 1 de cada 3 veces Pedro Sánchez no acabaría siendo presidente con estas encuestas. Al contrario de la predicción del Congreso, es difícil saber el grado de calibración del modelo de presidente, dado su componente cualitativo no-testable.

Más allá del porcentaje exacto de cada candidato, el valor de este modelo ha sido identificar las tendencias: Cuando tenemos señales confusas en direcciones opuestas, como por ejemplo una bajada de UP y una subida del PSOE al mismo tiempo, el modelo agrega las señales y traduce de forma sencilla su impacto en las opciones de los candidatos. El modelo de presidente nos ha permitido saber que las opciones de Sánchez subían considerablemente durante la campaña, mientras las de Casado caían y las de Rivera se esfumaban.

## Otras predicciones

A lo largo de la campaña publicamos otras predicciones basadas en el modelo del Congreso, que también han funcionado bien.

[Este artículo](https://www.inakiarbeloa.com/el-voto-mas-util/) publicado el viernes pronosticaba qué partido sacaría el último escaño en cada provincia. Hice 275 predicciones y estos fueron los resultados:

![](/images/04.2019_general_election_forecast/posts/2019-04-29-postmortem-provincias.png)

El modelo de predicción del Congreso parece estar bien calibrado: Cuando un evento tenía entre el 10% y el 30% de opciones de ocurrir, ocurrió el 19% de las veces. Y cuando un evento tenía más del 30% de opciones de ocurrir, ocurrió más del 30% de las veces (un 42%). 5 de 50 partidos con "pocas opciones" de entrar en alguna provincia consiguieron escaño. Se trata de UP en las tres provincias valencianas (donde sorprendió al derrotar con contundencia a Compromís), Vox en Cádiz y UP en Murcia.

[Este artículo](https://www.inakiarbeloa.com/escenarios-post-electorales) analizaba el tablero electoral y estimaba las probabilidades de cada escenario post-electoral, como se puede ver en esta tabla. A falta de terminar el recuento del voto exterior, estamos en el recuadro naranja, que era el segundo más probable:

![](/images/04.2019_general_election_forecast/posts/2019-04-29-postmortem-escenarios.png)

## Postdata: El error

El único escaño que el modelo no tuvo en cuenta fue el del Partido Regionalista de Cantabria, que no se presentó a las elecciones anteriores, apenas aparecía en las encuestas y [cuando aparecía](https://twitter.com/dmontanes/status/1109748677990641664) no obtenía representación, por lo que ni siquiera lo incluí en el modelo.