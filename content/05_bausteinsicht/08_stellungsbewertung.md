+++
title = "Módulo Principal 2: Autenticación y Funcionalidades Adicionales"
pre = "5.8 "
weight = 18
+++

## 5.8 Módulo Principal 2: Autenticación y Funcionalidades Adicionales (cuadro negro)

Este módulo se encarga de la gestión de la identidad de los usuarios de la plataforma Green Cloud y proporciona funcionalidades adicionales que aprovechan los servicios de Firebase más allá del simple almacenamiento de datos. Su objetivo principal es habilitar una experiencia de usuario segura y funcional, así como extender las capacidades del backend.

### Esto incluye:

* Autenticación y gestión de usuarios: Permite a los usuarios registrarse, iniciar sesión y gestionar sus perfiles utilizando Firebase Authentication.
* Ejecución de lógica de backend: Facilita la ejecución de código personalizado en la nube a través de Firebase Cloud Functions, que puede utilizarse para tareas como el procesamiento de datos, la integración con otros servicios o la implementación de lógica de negocio específica.
* Comunicación con los usuarios: Permite el envío de notificaciones push a los dispositivos móviles de los usuarios a través de Firebase Cloud Messaging, para alertarlos sobre eventos importantes o proporcionar información relevante del ecosistema.
* Gestión de archivos: Proporciona la capacidad de almacenar y recuperar archivos (imágenes, documentos, etc.) utilizando Firebase Storage.
* Alojamiento de la aplicación web: Si la interfaz web de Green Cloud está alojada en Firebase Hosting, este módulo podría incluir la gestión de la implementación y configuración del hosting.

![Schnittstelle Bewertung, Klasse ReineMaterialBewertung](/img/modulo2.png "Schnittstelle Bewertung, Klasse ReineMaterialBewertung")

*Imagen: Diagrama Módulo Principal 2: Autenticación y Funcionalidades Adicionales*


| Método | Breve descripción |
|---------|------------------|
|registerUser(credentials: Map) : User|	Registra un nuevo usuario en el sistema utilizando las credenciales proporcionadas (por ejemplo, email y contraseña) y devuelve un objeto User con la información del usuario creado.|
|signInUser(credentials: Map) : User|	Permite a un usuario existente iniciar sesión en el sistema utilizando sus credenciales y devuelve un objeto User con la información del usuario autenticado.|
|triggerCloudFunction(name: String, data: JSON) : JSON|	Invoca una función específica (name) desplegada en Firebase Cloud Functions, enviándole datos (data) en formato JSON y recibiendo una respuesta también en formato JSON.|
|sendPushNotification(userId: String, message: String) : boolean|	Envía una notificación push (message) a un usuario específico identificado por su userId utilizando Firebase Cloud Messaging. Devuelve true si el envío fue exitoso.|
|registerWithEmailAndPassword(email: String, password: String) : User|	Registra un nuevo usuario utilizando su dirección de correo electrónico (email) y una contraseña (password), devolviendo un objeto User con la información del usuario creado.|
|signInWithEmailAndPassword(email: String, password: String) : User|	Permite a un usuario iniciar sesión utilizando su dirección de correo electrónico (email) y contraseña (password), devolviendo un objeto User con la información del usuario autenticado.|
|getCurrentUser() : User|	Obtiene la información del usuario actualmente autenticado en el sistema, devolviendo un objeto User o null si no hay ningún usuario autenticado.|
|callFunction(name: String, data: JSON) : JSON|	Invoca una función específica (name) desplegada en Firebase Cloud Functions, enviándole datos (data) en formato JSON y recibiendo una respuesta también en formato JSON (similar a triggerCloudFunction).|
|sendToUser(userId: String, message: String) : boolean|	Envía un mensaje (message) a un usuario específico identificado por su userId a través de Firebase Cloud Messaging. Devuelve true si el envío fue exitoso (similar a sendPushNotification).|
|sendToTopic(topic: String, message: String) : boolean	|Envía un mensaje (message) a todos los dispositivos suscritos a un tema específico (topic) en Firebase Cloud Messaging. Devuelve true si el envío fue exitoso.|
|uploadFile(path: String, file: File) : URL|	Sube un archivo (file) a Firebase Storage a la ruta especificada (path) y devuelve la URL de descarga del archivo subido.|
|downloadFile(url: URL) : File|	Descarga un archivo desde Firebase Storage utilizando la URL de descarga proporcionada (url) y devuelve el archivo descargado.|


*Tabla: Métodos de Módulo Principal 2: Autenticación y Funcionalidades Adicionales*


### Autenticación y Funcionalidades Adicionales
Este módulo proporciona servicios esenciales para la gestión de usuarios y la extensión de las capacidades del backend de la plataforma Green Cloud utilizando los servicios de Firebase. Su enfoque principal es habilitar una experiencia de usuario segura y funcional, así como proporcionar herramientas para la ejecución de lógica personalizada y la comunicación con los usuarios.

### Ubicación/archivo de almacenamiento

La implementación está debajo de los paquetes._de.dokchess.engine..._

### Puntos abiertos

Actualmente, la implementación de las funcionalidades adicionales y de autenticación presenta las siguientes áreas de mejora y funcionalidades pendientes

* Mecanismos de autenticación multifactor (MFA) no implementados: La seguridad de las cuentas de usuario podría mejorarse añadiendo una capa adicional de verificación más allá de la contraseña.
* Integración con otros proveedores de autenticación ausente: Actualmente, solo se podría soportar la autenticación directa con Firebase, sin opciones para iniciar sesión con cuentas de redes sociales u otros proveedores.
* Gestión de errores y reintentos en las llamadas a Cloud Functions: La robustez del sistema podría mejorarse implementando estrategias para manejar fallos en la invocación de las funciones en la nube.
