+++
title = "Módulo Principal 1: Gestión de Datos"
pre = "5.7 "
weight = 17
+++

## 5.7 Módulo Principal 1: Gestión de Datos (cuadro negro)

### Propósito/Responsabilidad
Este módulo es responsable de la estructura, el almacenamiento y la recuperación eficiente de la información crucial para la operación y el análisis del ecosistema Green Cloud dentro de la plataforma Firebase (principalmente Firestore). Dada la complejidad y la gran cantidad de variables ambientales y datos generados,

### El módulo proporciona su funcionalidad a través de la interfaz GreenCloud.

Este módulo proporciona la infraestructura fundamental para la persistencia y el acceso a los datos esenciales del ecosistema Green Cloud dentro de la plataforma Firebase (principalmente Firestore). Su funcionalidad se expone a través de mecanismos que permiten a otros módulos interactuar con la información almacenada de manera eficiente y segura.

![Schnittstelle Suche, Klassen MinimaxAlgorithmus und MinimaxParalleleSuche](/img/modulo1.png "Schnittstelle Suche, Klassen MinimaxAlgorithmus und MinimaxParalleleSuche")
*Imagen: Diagrama Módulo Principal 1: Gestión de Datos*



| Método | Breve descripción |
|---------|------------------|
|saveData(entity: IDataModel) : boolean	|Guarda una nueva entidad de datos (IDataModel) o actualiza una existente en la base de datos. Devuelve true si la operación |fue exitosa, false en caso contrario.|
|getData(id: String, type: Class) : IDataModel	|Recupera una entidad de datos específica de la base de datos basándose en su identificador (id) y el tipo de la entidad (type). Devuelve la entidad encontrada o null si no existe.|
|readDocument(collection: String, documentId: String) : JSON|	Lee un documento específico (documentId) de una colección (collection) en la base de datos Firestore y devuelve los datos en formato JSON.|
|writeDocument(collection: String, documentId: String, data: JSON) : boolean	|Escribe o actualiza un documento específico (documentId) en una colección (collection) de la base de datos Firestore con los datos proporcionados en formato JSON. Devuelve true si la operación fue exitosa.|
|getValue(path: String) : JSON|	Obtiene el valor ubicado en una ruta específica (path) |dentro de la base de datos en tiempo real de Firebase y lo devuelve en formato JSON.|
|setValue(path: String, value: JSON) : boolean|	Establece un valor en una ruta específica (path) dentro de la base de datos en tiempo real de Firebase con los datos proporcionados en formato JSON. Devuelve true si la operación fue exitosa.|
|save(entity: IDataModel) : boolean	|Guarda una entidad de datos (IDataModel) en la base de datos. Similar a saveData, pero podría tener una semántica más específica dentro del contexto del Data Access Object.|
|findById(id: String, type: Class) : IDataModel|	Busca y devuelve una entidad de datos (IDataModel) por su identificador único (id) y tipo (type). Similar a getData, pero específico para el patrón Data Access Object.|
|find(query: String, type: Class) : Collection<IDataModel>|	Busca y devuelve una colección de entidades de datos (IDataModel) que coinciden con los criterios de búsqueda especificados en la query y son del tipo (type) indicado.|
|get(key: String) : Any|	Recupera un valor almacenado en la caché utilizando la clave (key) proporcionada. Devuelve el valor encontrado o null si la clave no existe en la caché.|
|put(key: String, value: Any)|	Almacena un valor (value) en la caché, asociándolo con una clave (key).|
invalidate(key: String)|	Elimina la entrada de la caché asociada con la clave (key) proporcionada.|
|authorizeRead(user: User, entity: IDataModel) : boolean|	Verifica si un usuario (user) tiene permiso para leer una entidad de datos específica (entity) basándose en las reglas de seguridad definidas. Devuelve true si el acceso está permitido.|
|authorizeWrite(user: User, entity: IDataModel) : boolean	|Verifica si un usuario (user) tiene permiso para modificar o crear una entidad de datos específica (entity) basándose en las reglas de seguridad definidas. Devuelve true si el acceso está permitido.|


### Ubicación/archivo de almacenamiento
La implementación está debajo de los paquetes._de.dokchess.engine..._
