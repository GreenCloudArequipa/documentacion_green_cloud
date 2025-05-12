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

![Eine Figur hat eine Farbe und eine Art](/images/Abb09_18_Figur.png "Eine Figur hat eine Farbe \(z.B. weiß\) und eine Art \(z.B. Bauer\)")

*Imagen: Una figura tiene un color (por ejemplo, blanco) y un tipo (por ejemplo, granjero)*

El entorno de monitoreo de Green Cloud consta de un área virtual estructurada, donde cada módulo de sensores está asociado a un único macetero inteligente.
La clase Zona describe cada ubicación dentro del sistema. Dado que una ubicación puede estar asociada a un máximo de una planta, basta con especificar una interacción indicando el cambio de estado o la transferencia de datos entre sensores y el sistema central.

La única excepción ocurre cuando se realiza una acción especial, como el reemplazo de una planta por otra con diferentes necesidades (por ejemplo, intercambiar una Azorella compacta por una Stipa ichu).
Las acciones automáticas avanzadas, como el ajuste dinámico de las condiciones ambientales (por ejemplo, activar riego o luces LED específicas), también son manejadas dentro de este esquema.

Los movimientos en el sistema, como la transferencia de datos desde los sensores al usuario a través de la aplicación, se representan mediante flujos de comunicación directa, organizados por las clases responsables de cada interacción.

![Ein Zug geht von einem Feld zu einem Feld](/images/Abb09_19_Zug.png "Ein Zug geht von einem Feld zu einem Feld")

*Imagen: Una jugada va de un campo a otro*

La clase EstadoSistema representa la situación actual en el ecosistema Green Cloud.
Se refiere principalmente a las plantas monitoreadas y los datos recopilados por los sensores, que internamente están configurados como una matriz bidimensional representando los maceteros disponibles en una estructura organizada (por ejemplo, una cuadrícula de 4 x 4 o personalizada según el entorno).

Si un macetero está desocupado, su posición en la matriz tendrá un valor nulo o predeterminado.
Para completar el monitoreo del ecosistema, se necesita información adicional, como:

Los parámetros ambientales actuales (humedad, luz, temperatura, etc.).
Las plantas presentes y su estado de salud.
Las acciones programadas o automáticas en curso (como riego o ajuste de luz).
Si hay alertas activas (como niveles críticos de humedad o fallos en los sensores).
Este modelo asegura que el sistema puede evaluar y tomar decisiones automáticas, además de informar al usuario sobre las condiciones en tiempo real.

![Die Klasse Stellung](/images/Abb09_20_Stellung.png "Die Klasse Stellung \(Ausschnitt, Details wie Rochade fehlen\)")

*Imagen: La clase de posición (detalle, faltan detalles como el enroque)*

La clase EstadoSistema también es inmutable. El método aplicaAccion() devuelve un nuevo estado del sistema con los datos actualizados tras la acción aplicada.

Por ejemplo, si se realiza una acción como activar el riego o cambiar la planta de un macetero, el método genera un nuevo estado que refleja estas modificaciones, mientras mantiene intacto el estado anterior para referencia o auditoría.

Esta inmutabilidad garantiza consistencia en el manejo de datos y facilita el rastreo de cambios en el ecosistema, permitiendo comparar estados pasados y actuales para análisis de tendencias o resolución de problemas.([→ Entscheidung 9.2 „Sind Stellungsobjekte veränderlich oder nicht?“](/09_entscheidungen/02_stellungsobjekte/)).
