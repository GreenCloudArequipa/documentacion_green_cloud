+++
title = "Evaluación de recursos"
menuTitle = "6.1 Detección de trenes"
weight = 11
+++

## 6.1 Evaluación de recursos

Después de configurar el sistema de monitoreo del ecosistema, el cliente (usuario o dispositivo) inicia una evaluación especificando una acción de intervención en el ecosistema, como "plantación de árboles" o "restauración de hábitat".
El diagrama de secuencia a continuación muestra una interacción ejemplar a nivel de subsistema desde la entrada "plantar 5 árboles" (acción del usuario para plantar 5 árboles) hasta la respuesta de Green Cloud, es decir, la salida "respuesta: aumento de la biodiversidad en un 10%" (medición del impacto positivo en el ecosistema). Esta respuesta puede estar relacionada con el tipo de planta, la zona elegida, o los recursos necesarios para la acción. (caballo negro b8-c6,[„Nimzowitsch-Verteidigung“](https://de.wikipedia.org/wiki/Nimzowitsch-Verteidigung)).

![Beispielhaftes Zusammenspiel für eine Zugermittlung](/images/Abb09_16_ZugErmittlungWalkthrough.png "Beispielhaftes Zusammenspiel für eine Zugermittlung")

*Imagen: Ejemplo de interacción para la determinación de un tren*

Primero, el subsistema de monitoreo de ecosistemas valida la entrada de la acción del usuario utilizando las reglas del juego definidas (→ 8.4 „Plausibilisierung und Validierung“). En este caso, la acción "plantar 5 árboles nativos" se reconoce como válida y se ejecuta en el motor de simulación ambiental (con estado).
Luego, el subsistema solicita al motor que determine el impacto de la acción en el ecosistema.

Dado que el cálculo del impacto de una acción puede llevar tiempo, pero Green Cloud debe poder responder rápidamente, la llamada se realiza de manera asincrónica. El motor, entonces, informa sobre los posibles impactos de la acción.

Primero, el motor verifica si el sistema de recursos ecológicos tiene recomendaciones previas basadas en datos históricos o en una base de datos de apertura de acciones. Este no es el caso en este ejemplo.
Por lo tanto, el motor calcula el impacto de la acción por su cuenta. Para hacerlo, utiliza las reglas ecológicas del juego (como la adaptabilidad de las especies a diferentes zonas) y determina las posibles intervenciones.

El motor examina y evalúa los posibles impactos, y gradualmente informa los resultados, como el aumento de la biodiversidad o la mejora de la calidad del suelo, cada vez con mayor precisión. Esto se logra mediante el patrón Observer (implementación con Reactive Extensions).

El diagrama de ejemplo muestra dos posibles resultados de la plantación (mejora de la biodiversidad en un 5%, aumento de la retención de agua en un 3%) y, finalmente, un mensaje de que la evaluación de la acción se ha completado y no se pueden predecir mejoras adicionales.
El subsistema de Green Cloud ejecuta la acción final (plantar los árboles) y luego muestra los resultados en la interfaz de usuario o en la salida estándar del sistema: "acción: plantar 5 árboles nativos, impacto: aumento de biodiversidad en un 5%".