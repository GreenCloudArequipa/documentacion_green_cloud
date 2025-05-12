+++
title = "Conexión frontal"
menuTitle = "9.1 Conexión frontal"
weight = 1
+++

## 9.1 ¿Cómo se comunica la plataforma con el mundo exterior?

### Respecto a la pregunta

En Green Cloud, la comunicación con el mundo exterior se gestiona mediante la interacción entre la aplicación móvil o web y los sensores conectados al ecosistema vegetal. La clave está en crear una experiencia de usuario fluida y accesible, especialmente para los niños, que permita monitorear y gestionar el estado de las plantas mediante una mascota digital.

### Factores de influencia relevantes

* Condiciones de contorno
 * Operación de los front-end al menos en sistemas operativos de escritorio Windows
 * Soporte para interfaces disponibles gratuitamente
 * Preferencia por los estándares establecidos ([→ 2.3 Convención](/02_randbedingungen/03_konventionen/))
* Características de calidad significativamente afectadas. ([→ 1.2 Metas de calidad](/01_einfuehrung/02_qualitaetsziele/))
 * Objetivo de calidad: utilizar interfaces existentes (interoperabilidad)
 * Objetivo de calidad: plataforma de experimentación atractiva (cambiabilidad)
 * Adaptabilidad (al futuro software de ajedrez)
* Riesgos involucrados
 * La conexión con el frontend falla ([→ 11.1 Riesgo de falla ](/11_risiken/01_frontend/))

### Suposiciones

* Explorar interfaces menos disponibles conduce a todas las opciones de integración interesantes.

### Alternativas consideradas para la implementación de interfaces en el proyecto GREEN CLOUD

A lo largo del desarrollo del proyecto GREEN CLOUD: Ecosistema Vegetal Sostenible, se evaluaron las siguientes alternativas para implementar las interfaces gráficas:

Plataforma Blynk (código abierto, enfocada en IoT, con compatibilidad para dispositivos móviles y navegadores web).
Plataforma Node-RED (código abierto, basada en flujos visuales, compatible con múltiples protocolos y dispositivos IoT).
Framework Flutter (código abierto, proporciona compatibilidad multiplataforma para aplicaciones móviles y web).
Como resultado de esta evaluación, se identificaron dos opciones principales de protocolos de comunicación entre sensores y la interfaz gráfica:

Opción 1: Protocolo MQTT (Protocolo de Telemetría de Colas de Mensajes, ampliamente utilizado en IoT, basado en la publicación/suscripción de mensajes, ver detalles aquí).
Opción 2: Protocolo HTTP/REST (Protocolo de Transferencia de Hipertexto, común en aplicaciones web y móviles, ver detalles aquí).
Aunque ninguno de estos protocolos cuenta con una estandarización formal exclusiva para el contexto del proyecto, ambos están documentados públicamente y ampliamente soportados en el ámbito del IoT.

Ambos protocolos utilizan comunicaciones basadas en texto y permiten la interacción entre sensores, la plataforma IoT, y la interfaz gráfica a través de conexiones de red. Los datos recopilados por los sensores son procesados en tiempo real y visualizados mediante la interfaz seleccionada.

La siguiente tabla muestra cuál de las plataformas evaluadas implementa qué protocolo:

*Tabla: Protocolos y frontends*

| Plataforma     | Protocolo MQTT |Protocolo HTTP/REST |
|------------------|----------------|--------------------|
| Blynk            | si             | si                 |
| Node-RED         | si             |  si                | 
| Flutter          | no             |  si                | 

### Decisión
En principio, tanto el protocolo MQTT como HTTP/REST son capaces de cumplir con los objetivos de calidad establecidos bajo las condiciones límite del proyecto. Sin embargo, la elección del protocolo tiene implicaciones sobre las interfaces gráficas que se pueden implementar.

Tras una evaluación técnica, se tomó la decisión de implementar el protocolo MQTT. Esta elección se realizó considerando que la estructura modular del sistema GREEN CLOUD permite agregar protocolos de comunicación alternativos (como HTTP/REST u otros) sin modificar el núcleo del sistema, según las dependencias detalladas en la arquitectura de bloques ([ver Sección 5.1]).

La plataforma preferida para la interfaz gráfica es Blynk, ya que está disponible de manera gratuita para uso básico y ofrece ventajas significativas en términos de funcionalidad. Entre estas ventajas se encuentran:

Compatibilidad nativa con MQTT.
Opciones avanzadas para la visualización en tiempo real de los datos recolectados por los sensores.
Configuración intuitiva para flujos de datos y alertas en dispositivos móviles y navegadores web.
Además, al optar por el protocolo MQTT, se garantiza la compatibilidad con un ecosistema más amplio de dispositivos y sistemas operativos (incluidos Windows, macOS, Linux, Android e iOS). Esta interoperabilidad fue un factor decisivo, ya que permite que un mayor número de usuarios interesados interactúen con el sistema GREEN CLOUD.

Finalmente, la flexibilidad del protocolo MQTT para gestionar redes IoT robustas y escalables, junto con su soporte para integración con plataformas futuras, asegura que el proyecto pueda evolucionar y expandirse sin mayores restricciones.

