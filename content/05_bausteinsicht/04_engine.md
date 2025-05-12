+++
title = "Firebase Services"
pre = "5.4 "
weight = 14
+++

## 5.4 Firebase Services (caja negra)

### Propósito/Responsabilidad
Este subsistema, "Firebase Services", actúa como la capa de interacción con la plataforma Firebase para la gestión de datos y la funcionalidad de la aplicación GreenCloud. 



### Interfaces
El subsistema "Firebase Services" expone su funcionalidad para la gestión de datos y la autenticación dentro del sistema GreenCloud a través de los servicios proporcionados por la plataforma Firebase. La interacción con la base de datos (Firestore), la autenticación de usuarios (Firebase Authentication) y, potencialmente, la ejecución de lógica de backend (Firebase Cloud Functions) constituyen los principales medios a través de los cuales otros subsistemas del sistema GreenCloud acceden a las capacidades de "Firebase Services". Esta arquitectura basada en Firebase facilita la escalabilidad, la gestión de datos en tiempo real y la seguridad de la aplicación. La flexibilidad se mantiene al permitir que la lógica específica de la aplicación GreenCloud (como las reglas de control ambiental) se implemente y se conecte a estos servicios de Firebase según sea necesario.




![Schnittstelle Engine, Implementierung](/img/firebase_service.png "Schnittstelle Engine, Implementierung")




| Método | Breve descripción |
|---------|------------------|
|autenticarUsuario(credenciales: Map) : Usuario|Autentica a un usuario utilizando las credenciales proporcionadas (por ejemplo, email y contraseña) y devuelve un objeto Usuario.|
|guardarDatos(coleccion: String, documento: String, datos: JSON) : boolean|	Guarda los datos proporcionados en formato JSON en una colección y documento específicos dentro de Firestore.|
|obtenerDatos(coleccion: String, documento: String) : JSON|	Recupera los datos en formato JSON de una colección y documento específicos dentro de Firestore.|
|escucharCambios(coleccion: String, listener: Listener)|	Establece un mecanismo para recibir notificaciones en tiempo real cada vez que hay modificaciones en la colección especificada de Firestore.|
|ejecutarFuncionNube(nombreFuncion: String, parametros: JSON) : JSON|	Invoca una función desplegada en Firebase Cloud Functions con los parámetros proporcionados en formato JSON y devuelve su resultado también en JSON.|
|onDataChanged(data: JSON)|	Método definido en la interfaz Listener que se invoca cuando se reciben nuevos datos o cambios desde Firestore.|
|onError(error: Exception)|	Método definido en la interfaz Listener que se invoca cuando ocurre un error al escuchar los cambios en Firestore.|

----

[(8.2 Modelo de dominio)](/08_konzepte/02_domaenenmodell/)Este concepto describe los parámetros de entrada y salida utilizados en la interfaz, tales como _Condición_ (estado ambiental actual) y _Acción_ (intervención sugerida).

Los detalles adicionales sobre el subsistema de la plataforma se pueden consultar en la vista de caja blanca en  [(5.6 Plataforma)](/05_bausteinsicht/06_ebene_2_engine/).

### Ubicación/archivo de almacenamiento
La implementación y las pruebas unitarias están debajo de los paquetes. _greencloud.platform.engine_

