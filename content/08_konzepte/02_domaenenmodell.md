+++
title = "Modelo de dominio"
menuTitle = "8.2 Modelo de dominio"
weight = 2
+++

## 8.2 Modelo de dominio

> "El ecosistema Green Cloud opera mediante la interacción entre sensores electrónicos, plantas autóctonas y usuarios. Estos componentes colaboran para monitorear y mantener el bienestar de las plantas en un entorno inteligente, gestionado a través de una plataforma móvil y web."
>

Las distintas partes del sistema Green Cloud intercambian datos específicos relacionados con el ecosistema vegetal.
Esto incluye principalmente el estado del macetero (como humedad, temperatura, y nivel de luz), así como las interacciones del usuario y las acciones automatizadas del sistema.
Las mismas clases se utilizan como parámetros de entrada y retorno en todos los módulos del sistema.

A continuación, se presenta una descripción general aproximada de estas estructuras de datos y sus interdependencias.
Los detalles específicos están contenidos en la documentación técnica del proyecto.
Las clases y enumeraciones (enums) utilizadas se encuentran organizadas en el paquete com.greencloud.domain.

Una planta en el sistema Green Cloud se caracteriza por sus atributos biológicos (como especie, tamaño, y necesidades específicas) y sus parámetros ambientales actuales (como nivel de agua y exposición a la luz).
En el modelo de dominio de Green Cloud, una planta no almacena información sobre el dispositivo donde está conectada.
La clase que representa a una planta es inmutable, como todas las demás en el modelo de dominio.

![Eine Figur hat eine Farbe und eine Art](/img/diagrama_clases.png "Eine Figur hat eine Farbe \(z.B. weiß\) und eine Art \(z.B. Bauer\)")

*Imagen: Diagrama de clases GreenCloud*

El sistema de monitoreo Green Cloud organiza su espacio virtual de forma que cada macetero inteligente se vincula a un único módulo de Sensor. La Planta monitoreada reside en este macetero. Aunque una ubicación (implícitamente ligada a un macetero) generalmente contiene una sola Planta, el sistema debe contemplar la eventualidad de reemplazar una Planta por otra con diferentes requerimientos, lo cual podría influir en las ReglaCuidado asociadas.

La interacción principal dentro del sistema se centra en la recopilación de datos por los Sensores y su transmisión para su posterior análisis y visualización. Las lecturas de los Sensores se registran como instancias de LecturaSensor, asociadas a un Sensor específico y a la Planta que está monitoreando. Estas lecturas son cruciales para evaluar el estado de la Planta y determinar si se deben aplicar las ReglaCuidado definidas.

Las acciones automatizadas, como el ajuste dinámico de las condiciones ambientales (riego, iluminación), son orquestadas por el PlantCareScheduler basándose en las ReglaCuidado y los datos proporcionados por los Sensores. Estas reglas definen umbrales y acciones específicas para diferentes tipos de Sensores (humedad, luz, temperatura, etc.).

El EstadoSistema se puede conceptualizar como la colección actual de las Plantas monitoreadas y las últimas LecturaSensores asociadas. Esta información, junto con el estado de las ReglaCuidado activas, permite al sistema evaluar las condiciones y generar Notificaciones para los PerfilUsuarios cuando se detectan situaciones que requieren atención.

La gestión de los PerfilUsuarios implica el seguimiento de las Plantas que tienen asociadas y las Notificaciones que han recibido. El sistema mantiene un registro del estado actual del ecosistema, incluyendo los parámetros ambientales proporcionados por los Sensores, el estado de salud de las Plantas y cualquier acción programada o en curso. Las Alertas generadas por el incumplimiento de las ReglaCuidado también forman parte de este estado.

La inmutabilidad del EstadoSistema implica que cualquier acción, como la recepción de una nueva LecturaSensor o la aplicación de una ReglaCuidado por el PlantCareScheduler, resulta en la creación de un nuevo estado que refleja los cambios, manteniendo el estado anterior para fines de auditoría y análisis histórico. Este principio asegura la coherencia de los datos y facilita el seguimiento de la evolución del entorno de cuidado de las Plantas.
