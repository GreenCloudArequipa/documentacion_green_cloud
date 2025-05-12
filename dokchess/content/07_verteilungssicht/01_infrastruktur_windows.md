+++
title = "Infraestructura de Windows"
menuTitle = "7.1 Infraestructura de Windows"
weight = 11
+++

## 7.1 Infraestructura de Windows

El diagrama de distribución a continuación muestra el uso de Green Cloud en un entorno Windows, sin depender de bibliotecas externas. En lugar de una biblioteca de apertura, Green Cloud utiliza una interfaz gráfica de usuario (GUI) accesible a través de plataformas móviles y web, optimizadas para proporcionar un monitoreo intuitivo de los ecosistemas y facilitar la interacción con el sistema. La interfaz es crucial para la visualización de datos relacionados con el estado ambiental, lo que permite a los usuarios tomar decisiones informadas sobre el cuidado de las plantas y la gestión de recursos.

En este caso, la plataforma Green Cloud se integra perfectamente con las herramientas de monitoreo ambiental, sin necesidad de líneas de comando, lo que proporciona una experiencia fluida en dispositivos móviles y web, adaptándose a las necesidades de los usuarios sin requerir conocimientos técnicos previos.. ([→ Entscheidung 9.1 „Wie kommuniziert die Engine mit der Außenwelt?“](/09_entscheidungen/01_anbindung/)).

![Deployment von DokChess auf einem Windows-PC](/images/Abb09_17_DeploymentDokChess.png "Deployment von DokChess auf einem Windows-PC")

*Imagen: Implementación de GreenCloud en movil *

*Imagen: Implementación de GreenCloud *

* Aplicación móvil para Android/iOS, que permita a los usuarios interactuar con la plataforma.
* Versión de navegador web compatible con los principales navegadores (Chrome, Firefox, Edge, Safari, etc.).
Conexión a Internet para el uso de la interfaz gráfica y la comunicación con el sistema de evaluación de datos.
* La plataforma puede integrar funciones como la monitorización de la sostenibilidad y el cuidado de plantas en tiempo real, brindando una experiencia interactiva sin la necesidad de utilizar comandos.

El proyecto Green Cloud se implementará en plataformas web y móviles, eliminando la necesidad de scripts como .bat o archivos Java de tipo.jar. En lugar de eso, se utilizarán interfaces gráficas accesibles tanto en la web como en aplicaciones móviles, con todas las dependencias necesarias integradas en el sistema.

### Puntos abiertos
Algunas interfaces en dispositivos móviles o navegadores web pueden tener limitaciones en cuanto a la integración de ciertos componentes de software, como servicios o módulos externos. En estos casos, Green Cloud debe asegurarse de que todos los módulos y servicios que componen el sistema puedan ser ejecutados de man
