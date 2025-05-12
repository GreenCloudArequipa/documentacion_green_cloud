+++
title = "motor"
pre = "5.4 "
weight = 14
+++

## 5.4 Motor (caja negra)

### Propósito/Responsabilidad
Este subsistema implica determinar la acción siguiente en función de una situación ambiental específica. Esta situación es captada a través de sensores y otros dispositivos externos. La plataforma del sistema mantiene un estado constante y opera de manera integrada con el ecosistema vegetal sostenible. La implementación predeterminada requiere un conjunto definido de reglas de control ambiental para funcionar correctamente, aunque la personalización de estos parámetros por parte del usuario es opcional.



### Interfaces
El subsistema proporciona su funcionalidad a través de una interfaz de plataforma denominada GreenCloud.Interface.Platform. La implementación predeterminada está representada por la clase GreenCloud.Platform.DefaultImplementation, la cual define las operaciones básicas para la gestión del ecosistema vegetal sostenible. Esta arquitectura permite la integración de nuevas implementaciones personalizadas, garantizando flexibilidad y escalabilidad dentro del sistema.




![Schnittstelle Engine, Implementierung](/images/Abb09_11_Schnittstellen_Engine.png "Schnittstelle Engine, Implementierung")

*Imagen: interfaz de la plataforma *


| Método | Breve descripción |
|---------|------------------|
|configurar_ecosistema| Establece el estado inicial de la plataforma en función de la configuración especificada. Si actualmente se está ejecutando un análisis ambiental, este se cancelará.|
| determinar_acción|Inicia la determinación de una acción adecuada para la situación ambiental actual. Devuelve opciones sugeridas de manera asincrónica a través de un observable. La plataforma no ejecuta automáticamente las acciones.([→ Laufzeitsicht 6.1](/06_laufzeitsicht/01_zugermittlung/)). |
| ejecutar_acción | Ejecuta la acción especificada, es decir, actualiza el estado de la plataforma en función de la intervención realizada. Si actualmente se está ejecutando un análisis ambiental, este se cancelará.|
| cerrar_plataforma| Cierra la plataforma. Este método libera los recursos utilizados, y no se permitirá realizar más análisis o acciones posteriores.|

*Tabla: Métodos de la interfaz de la plataforma*

----


|Método | Breve descripción |
|---------|------------------|
| establecer_reglas_ambientales | Configura una implementación de las reglas ambientales que rigen el funcionamiento del ecosistema sostenible. Estas reglas determinan cómo los sensores y actuadores interactúan con las condiciones detectadas., [→ 5.3 Spielregeln (Blackbox)](/05_bausteinsicht/03_spielregeln/)|
|configurar_biblioteca_de_respuestas| Establece una biblioteca opcional de respuestas predeterminadas para condiciones específicas del ecosistema. Estas respuestas tienen prioridad sobre las evaluaciones dinámicas del sistema..[→ 5.5 Eröffnung (Blackbox)](/05_bausteinsicht/05_eroeffnung/)|

*Tabla: Métodos de la clase DefaultImplementation (además de PlatformInterface)*

----

[Konzept 8.2 („Schach-Domänenmodell“)](/08_konzepte/02_domaenenmodell/)Este concepto describe los parámetros de entrada y salida utilizados en la interfaz, tales como _Condición_ (estado ambiental actual) y _Acción_ (intervención sugerida).

Los detalles adicionales sobre el subsistema de la plataforma se pueden consultar en la vista de caja blanca en  [Abschnitt 5.6](/05_bausteinsicht/06_ebene_2_engine/).

### Ubicación/archivo de almacenamiento
La implementación y las pruebas unitarias están debajo de los paquetes. _greencloud.platform.engine_

