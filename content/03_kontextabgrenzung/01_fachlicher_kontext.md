+++
title = "Contexto Empresarial"
menuTitle = "3.1 Contexto empresarial"
weight = 1
+++

## 3.1 Contexto empresarial

![Contexto técnico de DokChess](/img/DIAGRAMA_DE_CONTEXTO.png "Contexto técnico de DokChess")
##### Imagen: Contexto empresarial de Greencloud

-----

#### Usuario  (interacción con el sistema)
El Usuario interactúa directamente con el sistema "Green Cloud - Sistema de Cuidado de Plantas" a través de la Aplicación Móvil. Esta interacción le permite monitorear el estado de sus plantas, visualizar los datos recopilados por los Sensores IoT, y potencialmente recibir alertas o recomendaciones basadas en esta información. La Aplicación Móvil sirve como la interfaz principal para que el usuario pueda comprender y gestionar el entorno de sus plantas.

#### Administrador (Monitoreo del sistema)
El Administrador tiene la función de supervisar el correcto funcionamiento del "Green Cloud - Sistema de Cuidado de Plantas". Esto implica el monitoreo del flujo de datos desde los Sensores IoT hacia el Firebase Backend, así como la disponibilidad y rendimiento de la Aplicación Móvil y la infraestructura del backend. El Administrador se asegura de la integridad y confiabilidad del sistema para todos los usuarios.

#### Aplicación Móvil (Accede y actualiza datos)
La Aplicación Móvil es la interfaz de usuario principal a través de la cual los usuarios interactúan con el sistema. Se conecta al Firebase Backend para acceder y visualizar los datos de los sensores, así como para potencialmente enviar comandos o configuraciones al sistema. La Aplicación Móvil facilita la comprensión del estado de las plantas y permite a los usuarios tomar decisiones informadas sobre su cuidado.

#### Sensores IoT (Envían datos de sensores)
Los Sensores IoT son los encargados de recopilar información ambiental relevante para el cuidado de las plantas, como la humedad del suelo, la temperatura, la luminosidad, etc. Estos dispositivos envían continuamente los datos recopilados al Firebase Backend para su almacenamiento y posterior análisis. La información proporcionada por los Sensores IoT es fundamental para que el sistema pueda ofrecer información precisa sobre el estado de las plantas.

#### Firebase Backend (Almacenamiento y gestión de datos)
El Firebase Backend actúa como el centro de almacenamiento y gestión de todos los datos del sistema. Recibe la información enviada por los Sensores IoT y la almacena de manera organizada. Además, sirve como la fuente de datos para la Aplicación Móvil, permitiendo a los usuarios acceder a la información de sus plantas en tiempo real. El Firebase Backend es crucial para la persistencia y disponibilidad de los datos del sistema.

Esta adaptación asegura que el sistema Green Cloud aproveche al máximo los recursos externos, optimizando tanto la funcionalidad como la experiencia del usuario.