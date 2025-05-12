+++
title = "Contexto de implementación"
menuTitle = "3.2 Contexto de implementación"
weight = 2
+++

## 3.2 Contexto de implementación

![Interacción técnica entre GreenCloud y los involucrados](/img/DIAGRAMA_DE_DESPLIEGUE.png "Interacción técnica entre GreenCloud y los involucrados")
##### Bild: Interacción técnica entre GreenCloud y los involucrados.

-----

#### Frontend (Aplicación Móvil)
El Frontend de la aplicación se materializa en una Aplicación Móvil diseñada para la interacción directa con el usuario. Esta interfaz permite a los usuarios visualizar los datos provenientes del Backend, gestionar sus Perfiles de Usuario, y consultar los Horarios de Cuidado de Plantas. La Aplicación Móvil se comunica con las Funciones Firebase Cloud en el Backend para acceder a la información y realizar acciones dentro del sistema.

#### Backend (Funciones Firebase Cloud, Horarios de cuidado de plantas, Perfiles de Usuario)
El Backend es el corazón lógico del sistema, compuesto por varios componentes interconectados. Las Funciones Firebase Cloud actúan como la capa de lógica de negocio, procesando las solicitudes de la Aplicación Móvil y coordinando el acceso a los datos. Los Horarios de Cuidado de Plantas almacenan la información sobre los regímenes de riego, fertilización y otros cuidados específicos para cada planta. Los Perfiles de Usuario gestionan la información y preferencias de cada usuario del sistema.

#### Integración de Usuario (Sensores IoT, Datos de Sensores)
La sección de Integración de Usuario se enfoca en la recopilación de datos del entorno de las plantas. Los Sensores IoT son los dispositivos físicos encargados de medir variables como la humedad, temperatura, luz, etc. Los Datos de Sensores representan la información cruda recopilada por estos dispositivos, la cual es enviada al Backend para su procesamiento y posterior visualización en la Aplicación Móvil.

#### CI/CD (GitHub, Azure DevOps, Selenium + WebDriver)
La sección de CI/CD (Integración Continua/Entrega Continua) engloba las herramientas y procesos para el desarrollo, prueba y despliegue automatizado del sistema. GitHub se utiliza como repositorio de código fuente y plataforma de colaboración. Azure DevOps proporciona servicios para la gestión de proyectos, construcción y liberación de software. Selenium + WebDriver se emplea para la automatización de pruebas de interfaz de usuario, asegurando la calidad y estabilidad de la Aplicación Móvil.

#### Servicios en la Nube (Funciones DigitalOcean)
Los Servicios en la Nube en este diagrama se representan mediante Funciones DigitalOcean. Estas funciones pueden complementar la lógica del Backend alojada en Firebase, ofreciendo capacidades adicionales de procesamiento o integración con otros servicios externos.

#### Monitoreo y AI (Grafana, Hugging Face AI)
La sección de Monitoreo y AI se centra en la supervisión del rendimiento del sistema y la aplicación de inteligencia artificial. Grafana es una herramienta para la visualización de métricas y la creación de dashboards para monitorear el estado y comportamiento del sistema. Hugging Face AI representa la posible integración de modelos de inteligencia artificial para el análisis avanzado de los Datos de Sensores, como la detección de patrones de crecimiento, enfermedades o la optimización de los Horarios de Cuidado de Plantas.
