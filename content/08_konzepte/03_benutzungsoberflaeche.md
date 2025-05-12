+++
title = "Interfaz de usuario"
menuTitle = "8.3 Interfaz de usuario"
weight = 3
+++

## 8.3	Interfaz de usuario

Green Cloud no incluye una interfaz gráfica integrada directamente en su núcleo, pero permite la interacción con los usuarios y el entorno externo a través de su plataforma web y aplicación móvil.
La comunicación entre los sensores, el sistema central y los usuarios se realiza mediante protocolos estándar que aseguran la transferencia confiable de datos en tiempo real.

Los usuarios acceden al ecosistema Green Cloud a través de navegadores web o aplicaciones móviles, donde pueden visualizar el estado de las plantas, recibir alertas y ejecutar acciones (como activar el riego o modificar parámetros). Esta arquitectura permite mantener el sistema modular y adaptable para diversas configuraciones. ([→ Decisión 9.1](/09_entscheidungen/01_anbindung/)). Esto se describe brevemente a continuación.

EEl sistema Green Cloud utiliza un protocolo basado en texto para la comunicación avanzada entre el núcleo del sistema y los dispositivos externos o usuarios con conocimientos técnicos.
Iniciar Green Cloud desde una línea de comando (terminal de Unix, símbolo del sistema de Windows, etc.) permite interactuar directamente con el sistema si se dominan los comandos principales diseñados para gestionar sensores y datos.

Estos comandos incluyen funcionalidades para:

* Configurar y calibrar sensores.
* Consultar el estado de los maceteros.
* Ejecutar acciones específicas, como activar riego o ajustar iluminación.
* Este enfoque basado en comandos permite una interacción flexible y potente para usuarios técnicos, sin necesidad de utilizar la interfaz gráfica estándar.

 (ver imagen en [Sección 4](/04_loesungsstrategie/)).

la siguiente tabla muestra un ejemplo de cómo un niño interactuaría con el sistema Green Cloud a través de su dispositivo móvil o aplicación, donde la mascota digital guiaría la experiencia y promovería la conciencia ambiental. Todos los comandos se completan con una nueva línea, y la mascota digital interactúa y proporciona retroalimentación al niño.

|Niño -> Green Cloud | Green Cloud -> Niño | observación|
|--------------------|--------------------|-----------|
| Iniciar Maceta	         |            | El niño solicita que la maceta inteligente se active y empiece a funcionar. |
|              | Maceta Activada       | La mascota digital responde diciendo: "¡Hola! Soy tu amigo verde. Vamos a cuidar a tus plantas." |
| Revisar Estado Maceta     |            |	El niño consulta el estado de la planta en su maceta. |
|        | Planta: 80% Saludable, Necesita Agua | La mascota responde: "¡Tu planta está bien, pero necesita un poquito de agua!" |
| Regar Planta           |            | El niño activa el riego para la planta. |
|         | Riego Activado    | La mascota digital dice: "¡Gracias por regar! Tu planta ahora estará feliz." |
| Ajustar Luz Maceta           |        | DEl niño ajusta la luz para la planta (si la planta necesita más luz). |
|          |     Luz Ajustada: 70%   | La mascota responde: "¡Ahora la planta tendrá más luz! ¡Estás haciendo un gran trabajo!" |
| Finalizar Interacción          |        | El niño finaliza la interacción con la maceta. |
|        |      Interacción Finalizada	  | La mascota se despide: "¡Hasta pronto! Recuerda cuidar siempre tu planta para un mundo más verde!" |


*Tabla: Ejemplo de comunicación entre un niño y Green Cloud a través de la mascota digital.*

Este sistema fomenta una interacción divertida y educativa para los niños, donde la mascota digital actúa como guía para enseñarles sobre el cuidado de las plantas y la importancia de la sostenibilidad. Los niños reciben información y retroalimentación de manera amigable, y el sistema realiza tareas automáticas como el riego o la regulación de luz, mientras la mascota promueve la conciencia ambiental.