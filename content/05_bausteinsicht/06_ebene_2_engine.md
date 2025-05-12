+++
title = "Nivel 2:  Firebase services"
pre = "5.6 "
weight = 16
+++

## 5.6 Nivel 2:  Firebase services (Caja Blanca)

Este módulo principal del subsistema "Firebase Services" se encarga de la persistencia y la gestión de toda la información relevante para la plataforma Green Cloud utilizando la infraestructura de datos de Firebase (principalmente Firestore). Su función principal es proporcionar una capa robusta y escalable para el almacenamiento y la recuperación de datos del ecosistema vegetal sostenible.



![Subsystem Engine, Bausteinsicht, Ebene 2](/img/firebase_service_estructura.png "Subsystem Engine, Bausteinsicht, Ebene 2")

*Imagen: Subsistema de la Plataforma, Vista de Bloques, Nivel 2*

----

| Módulo | Breve descripción |
|-------|------------------|
| Módulo Principal 1: Gestión de Datos | Este módulo se centra en la persistencia y el acceso a los datos dentro de la plataforma Firebase, utilizando principalmente la base de datos NoSQL (Firestore) y, opcionalmente, la base de datos en tiempo real. También abarca la definición del esquema de datos, la lógica de consultas, los mecanismos de caché y la seguridad de acceso a la información.|
| Módulo Principal 2: Autenticación y Funcionalidades Adicionales |Este módulo se encarga de gestionar la identidad de los usuarios (autenticación, registro, inicio de sesión) y proporciona funcionalidades adicionales ofrecidas por Firebase más allá del almacenamiento de datos, como la ejecución de lógica de backend sin servidor, el envío de notificaciones push y el almacenamiento de archivos.|

*Tabla: Módulos del subsistema de la Plataforma Green Cloud*
