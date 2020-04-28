---
permalink: /modelo-prediccion-elecciones-andaluzas-2018/
---
# Modelo de Predicción para las Elecciones Andaluzas 2018

He construido un modelo estadístico sencillo para simular la composición del próximo parlamento de Andalucía. El modelo parte de todas las encuestas publicadas en los últimos tres meses y realiza 20.000 simulaciones teniendo en cuenta cuánto suelen equivocarse las encuestas, cómo vota cada provincia y el grado de acuerdo entre las encuestas publicadas.

Publicaré actualizaciones diarias a lo largo de la campaña [aquí](https://inakiarbeloa.com/elecciones-andaluzas-2018).

## ¿Quién tendrá la mayoría?
![Distribución de fuerza izquierda-derecha](/images/2018_andalucia_election_forecast/2018.11.17_izquierda_derecha.png)

En 49 de cada 50 simulaciones, la suma de PP y Ciudadanos queda por debajo de los 55 escaños necesarios para la mayoría absoluta. Cualquier otra coalición factible implica al PSOE.

## ¿Quién gobernará?
![Probabilidad de cada partido de alcanzar la presidencia](/images/2018_andalucia_election_forecast/2018.11.17_presidencia.png)

Esta proyección se basa en dos suposiciones:

1. Si PP y Ciudadanos suman mayoría, se pondrán de acuerdo para gobernar. En ese supuesto, asumimos que la presidencia recaería en el partido con más escaños, y en caso de empate en quien tuviese más votos.
2. En caso contrario, el PSOE conseguirá mantener el gobierno. Bien con Adelante Andalucía, bien con Ciudadanos; con o sin Susana Díaz al frente.

El gráfico simula una ruleta. La probabilidad de que la bola caiga en la zona coloreada de cada círculo indica las posibilidades de que el partido alcance la presidencia. El PSOE tiene altísimas probabilidades de mantener la presidencia de la Junta (98%). En el improbable caso de que no lo consiguiese, no está claro si PP (1.2%) o Ciudadanos (0.8%) liderarían el gobierno.

## ¿Cómo quedará el parlamento?
![Horquillas de escaños](/images/2018_andalucia_election_forecast/2018.11.17_escaños.png)

El número de escaños de cada partido está dentro de la franja coloreada en el 80% de las 20.000 simulaciones. El PSOE será con toda probabilidad el mayor grupo parlamentario, aunque lejos de la mayoría absoluta. Los otros tres partidos están bastante igualados en la lucha por el segundo puesto, con el PP en cierta ventaja sobre Ciudadanos (Cs) y Adelante Andalucía (AA).

PSOE y Cs presentan más incertidumbre (franja de 10 escaños) que PP y AA (8 escaños). Esto se debe principalmente a que las encuestas están de acuerdo en sus estimaciones de voto para PP y AA, pero divergen mucho en las estimaciones de PSOE y Cs.

## Próximamente
En los próximos días añadiré algunos artículos para explicar cómo el modelo responde a las incógnitas más interesantes de estas elecciones:
* ¿Quién liderará el bloque del centro derecha: PP o Ciudadanos?
* ¿Tendrá el PSOE mayoría simple respecto al centro derecha?
* ¿Cómo se reparte el voto por provincias?
* ¿Cómo ha evolucionado la estimación de voto a lo largo de las últimas semanas?

También añadiré un apartado sobre la metodología.

## Referencias
Este ejercicio esta inspirado principalmente por el trabajo de Nate Silver y su equipo en [FiveThirthyEight](https://projects.fivethirtyeight.com/2018-midterm-election-forecast/house/). También he seguido con interés a Nate Cohn en [The Upshot](https://www.nytimes.com/interactive/2018/11/06/us/elections/results-house-forecast.html), a G. Elliott Morris y su blog [The Crosstab](https://www.thecrosstab.com/project/2018-midterms-forecast/), el modelo de predicción de [The Economist](https://www.economist.com/graphic-detail/2018/05/24/whos-ahead-in-the-mid-term-race) y el trabajo de Kiko Llaneras en [El País](https://elpais.com/politica/2017/12/18/ratio/1513610647_109254.html).
