+++
title = "Nivel 1: Plataforma"
pre = "5.1 "
weight = 11
+++

## 5.1	Nivel 1


El Sistema de Cuidado de Plantas ‘Green Cloud’ se estructura en diversos subsistemas interconectados. Existen dos tipos de usuarios principales: el Usuario y el Administrador. El Usuario interactúa con una Aplicación Móvil que forma parte del subsistema de Integración, el cual también se comunica con los Sensores IoT para recolectar datos ambientales clave. Estos datos se envían tanto al subsistema de Firebase Services como al Backend desplegado en DigitalOcean.

El subsistema de Firebase Services gestiona funciones como los perfiles de usuario, el historial de datos y la programación del cuidado de las plantas. A su vez, este subsistema interactúa con File Storage para guardar los datos históricos recolectados.

Por otro lado, el Administrador utiliza el subsistema de Monitoring & Analytics, que integra herramientas como Grafana para la visualización y análisis de datos en tiempo real. Las herramientas de Development Tools, como Azure DevOps y GitHub, permiten la automatización de pruebas, integración continua y despliegue del sistema completo, facilitando la gestión y mantenimiento del ecosistema Green Cloud
([→ 3.2 Contexto de implementación](/03_kontextabgrenzung/02_technischer_kontext/)).

![GreenCloud, vista de bloques, nivel 1](/img/nivel1.png "GreenCloud, Bausteinsicht, Ebene 1")

Imagen:Green Cloud, vista de bloque

----

| subsistema | Breve descripción |
|-----------|------------------|
| [Development Tools](/05_bausteinsicht/02_xboard-protokoll/) |Gestiona el desarrollo, integración continua y automatización de pruebas del sistema.|
| [Integration](/05_bausteinsicht/03_spielregeln/) | Recibe datos desde sensores IoT y la aplicación móvil para integrarlos al sistema. |
| [Backend (DigitalOcean)](/05_bausteinsicht/04_engine/) | Aloja servicios que procesan datos y facilitan la lógica de negocio del sistema.|
| [Firebase Services](/05_bausteinsicht/05_eroeffnung/) | Gestiona perfiles de usuario, almacenamiento de datos históricos y funciones en la nube.|
| [Monitoring & Analytics](/05_bausteinsicht/05_eroeffnung/) | Permite visualizar y analizar en tiempo real los datos recolectados, usando herramientas como Grafana.|

*Tabla: Descripción general de los subsistemas de DokChess*

Sección [→ 6.1 Evalucaion de recursos](/06_laufzeitsicht/01_zugermittlung/)) Facilita la interacción del usuario con el sistema a través de una plataforma web y móvil.
