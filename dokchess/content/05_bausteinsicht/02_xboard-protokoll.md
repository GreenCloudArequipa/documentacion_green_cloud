+++
title = "Texto de IU"
pre = "5.2 "
weight = 12
+++

## 5.2 Protocolo XBoard (caja negra)

### Propósito/Responsabilidad

Este subsistema implementa la comunicación con los usuarios a través de una interfaz gráfica (por ejemplo, en aplicaciones móviles o web), utilizando protocolos interactivos adaptados a Green Cloud (→ Entscheidung 9.1).
El subsistema procesa datos ingresados por los usuarios o sensores, los compara con las condiciones óptimas de las plantas y envía instrucciones al módulo de análisis.
Las respuestas del sistema, como recomendaciones de cuidado o alertas ambientales, son recibidas y formateadas para ser presentadas de forma clara e interactiva a los usuarios.
Este subsistema coordina las actividades de monitoreo y gamificación, impulsando toda la experiencia de interacción en Green Cloud. También alberga el método principal del sistema.

### Interfaces

El subsistema pone su funcionalidad por encima de eso.Java-Klassen _de.dokchess.xboard.XBoard_ und _de.dokchess.xboard.Main_ bereit:

![Klassen XBoard und Main](/images/Abb09_09_Schnittstellen_Xboard.png "Klassen XBoard und Main")
*Imagen: Clases XBoard y Principal*

----

| Método  |  Breve descripción |
|---------|------------------|
| setEntradaDatos | Configura la fuente de entrada del sistema mediante inyección de dependencias (→ Konzept 8.1). Por defecto, utiliza la entrada estándar (stdin), mientras que pruebas automáticas o simulaciones pueden emplear fuentes específicas, como datos de sensores. ([→ Konzept 8.1](/08_konzepte/01_abhaengigkeiten/)). |
| setSalidaDatos | Configura el destino de salida del sistema. Generalmente, la salida estándar (stdout) se usa para pruebas, pero en operación normal puede enviarse a interfaces gráficas o aplicaciones web.|
| setReglasEcosistema | Configura la implementación de las reglas de cuidado y monitoreo de plantas, → 5.3 Reglas del Ecosistema Vegetal (Blackbox). Estas incluyen parámetros como humedad, luz y nutrientes. [→ 5.3 Spielregeln (Blackbox)](/05_bausteinsicht/03_spielregeln/)
| setAnalizadorAmbiental | Configura el módulo encargado de evaluar las condiciones ambientales, → 5.4 Analizador Ambiental (Blackbox). Este módulo permite ajustes automáticos para optimizar el ecosistema. [→ 5.4 Engine (Blackbox)](/05_bausteinsicht/04_engine/) |
| iniciarSistema | Inicia el ciclo principal de comunicación (entrada/procesamiento/salida), gestionando los datos en tiempo real y ofreciendo recomendaciones o acciones hasta recibir un comando de cierre.|

*Tabla: Métodos de la clase XBoard*


### Ubicación/Archivo de Almacenamiento
La implementación del subsistema se encuentra organizada bajo los paquetes:
greencloud.ecosistema.interfaz...

### Puntos Pendientes
La implementación actual de la plataforma Green Cloud no cubre todas las funcionalidades posibles. Sin embargo, satisface los requisitos esenciales para su operatividad. Las siguientes características aún no están implementadas:

* Gestión avanzada de cronogramas de riego y mantenimiento.
* Predicciones dinámicas basadas en aprendizaje continuo mientras se recopilan nuevos datos.
* Generación automática de alertas ante eventos críticos (como sequía o plagas) mediante IA.
* Soporte para variantes de ecosistemas personalizados, como configuraciones específicas para cultivos o invernaderos especializados.