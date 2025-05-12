+++
title = "Evaluación de recursos"
menuTitle = "6.1 Evaluación de recursos"
weight = 11
+++

## 6.1 Evaluación de recursos

Cuando un Usuario desea obtener información del sistema, inicia una Consulta de datos a través de la Aplicación Móvil. El siguiente diagrama de secuencia ilustra una interacción típica a nivel de componente desde esta consulta inicial hasta la respuesta proporcionada al usuario.

En este escenario, la Aplicación Móvil envía una Request de estado al Firebase Cloud. El Firebase Cloud recibe esta solicitud y procede a Procesar datos. Durante este procesamiento, podría interactuar con una Función DigitalOcean para tareas específicas.

Los datos procesados son luego Enviados para visualización a Grafana, donde se generan representaciones visuales de la información. De manera paralela o posterior, el Firebase Cloud puede enviar datos para un Análisis AI a AI HuggingFace. AI HuggingFace realiza un análisis predictivo y devuelve un Resultado de predicción al Firebase Cloud.

Finalmente, el Firebase Cloud genera una Respuesta al usuario basada en los datos procesados y, potencialmente, en el resultado del análisis de IA. Esta respuesta es enviada de vuelta a la Aplicación Móvil, donde se presenta al Usuario.

Este flujo demuestra cómo una consulta inicial del usuario a través de la Aplicación Móvil desencadena una serie de comunicaciones entre los diferentes componentes del sistema Green Cloud para recuperar, procesar, analizar y finalmente presentar la información solicitada. La respuesta al usuario puede incluir tanto datos visualizados como predicciones generadas por la inteligencia artificial.

![Beispielhaftes Zusammenspiel für eine Zugermittlung](/img/DIAGRAMA_DE_SECUENCIA.png "Beispielhaftes Zusammenspiel für eine Zugermittlung")

*Imagen: Ejemplo Cuando un Usuario desea obtener información del sistema*

Cuando un Usuario desea obtener información del sistema, inicia una Consulta de datos a través de la Aplicación Móvil. El diagrama de secuencia ilustra el flujo de información desde esta consulta inicial hasta la presentación de una respuesta al usuario, posiblemente enriquecida con análisis predictivo.

En este escenario, la Aplicación Móvil envía una Request de estado al Firebase Cloud. El Firebase Cloud recibe esta solicitud y comienza a Procesar datos. Este procesamiento  implica la utilización de una Función DigitalOcean para tareas específicas de manipulación o recuperación de información.

Los datos procesados son entonces Enviados para visualización a Grafana, donde se generan representaciones gráficas que permiten al usuario comprender el estado del sistema o los datos recopilados.

De forma concurrente o posterior, el Firebase Cloud puede enviar datos relevantes para un Análisis AI a AI HuggingFace. AI HuggingFace aplica modelos de inteligencia artificial para generar un Resultado de predicción basado en los datos proporcionados.

Finalmente, el Firebase Cloud integra los datos procesados y el resultado del análisis de IA para construir una Respuesta al usuario, la cual es enviada de vuelta a la Aplicación Móvil y presentada al Usuario. Esta respuesta puede contener tanto la información visualizada en Grafana como las predicciones generadas por el modelo de IA.