+++
title = "Infraestructura en la nube"
menuTitle = "7.1 Infraestructura en la nube"
weight = 11
+++

## 7.1 Infraestructura en la nube

El diagrama de despliegue ilustra la arquitectura de Green Cloud, una solución completamente alojada en la nube. Los usuarios interactúan con el sistema a través de una App Móvil en sus Mobile Devices. Los datos ambientales son recolectados por Sensores integrados como IoT Devices, los cuales envían la información a la infraestructura en la nube.

El núcleo de la lógica de la aplicación reside en Firebase Cloud, utilizando Cloud Functions para el procesamiento de eventos y la orquestación de tareas. Los datos persistentes, tanto la información recopilada por los sensores como los metadatos de la aplicación, se almacenan en Firestore / Storage, también parte de la plataforma Firebase.

Para tareas de procesamiento computacionalmente intensivas o que requieren un entorno específico, Firebase Cloud puede delegar trabajo a Funciones de Procesamiento que se ejecutan en un DigitalOcean Droplet, un servidor virtual en la nube.

El monitoreo del rendimiento del sistema y la aplicación de inteligencia artificial para el análisis de datos se centralizan en un Monitoring Server, donde se encuentran desplegados Grafana para la visualización de métricas operativas y Hugging Face AI para la implementación de modelos de aprendizaje automático.

El ciclo de vida del desarrollo y la implementación de Green Cloud se gestiona mediante una infraestructura de CI/CD (Integración Continua/Entrega Continua) alojada en la nube, utilizando herramientas como GitHub para el control de versiones del código fuente y Azure DevOps para la automatización de los procesos de construcción, prueba y despliegue.

Esta arquitectura, basada en servicios en la nube, permite a los usuarios acceder a la funcionalidad de Green Cloud de manera intuitiva a través de sus dispositivos móviles, sin necesidad de una interfaz de línea de comandos o conocimientos técnicos avanzados sobre la infraestructura subyacente. La plataforma aprovecha la escalabilidad y confiabilidad de los proveedores de la nube para ofrecer una solución robusta y accesible.

![Deployment von DokChess auf einem Windows-PC](/img/DIAGRAMA_DE_DESPLIEGUE.png "Deployment von DokChess auf einem Windows-PC")


*Imagen: Implementación de GreenCloud*

* Aplicación móvil para Android/iOS, que permita a los usuarios interactuar con la plataforma.
* Versión de navegador web compatible con los principales navegadores (Chrome, Firefox, Edge, Safari, etc.).
Conexión a Internet para el uso de la interfaz gráfica y la comunicación con el sistema de evaluación de datos.
* La plataforma puede integrar funciones como la monitorización de la sostenibilidad y el cuidado de plantas en tiempo real, brindando una experiencia interactiva sin la necesidad de utilizar comandos.

El proyecto Green Cloud se implementará en plataformas web y móviles, eliminando la necesidad de scripts como .bat o archivos Java de tipo.jar. En lugar de eso, se utilizarán interfaces gráficas accesibles tanto en la web como en aplicaciones móviles, con todas las dependencias necesarias integradas en el sistema.

### Puntos abiertos
Algunas interfaces en dispositivos móviles o navegadores web pueden tener limitaciones en cuanto a la integración de ciertos componentes de software, como servicios o módulos externos. En estos casos, Green Cloud debe asegurarse de que todos los módulos y servicios que componen el sistema puedan ser ejecutados de man
