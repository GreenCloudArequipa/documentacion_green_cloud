+++
title = "Reglas del juego"
pre = "5.3 "
weight = 13
+++

## 5.3	Reglas del juego (caja negra)

### Propósito/Responsabilidad
Este subsistema contiene las reglas fundamentales para la gestión de las plantas autóctonas en el proyecto Green Cloud. Define las condiciones óptimas de crecimiento para cada planta, como humedad, temperatura y nutrientes, y verifica si las condiciones actuales cumplen con los parámetros ideales para su desarrollo sostenible. Además, detecta alertas críticas, como deshidratación o exposición extrema, asegurando el bienestar del ecosistema.

### interfaz
El subsistema expone su funcionalidad a través de la interfaz Java com.greencloud.reglas.PlantRules.

La implementación predeterminada de esta interfaz se encuentra en la clase com.greencloud.reglas.DefaultPlantRules.

![Schnittstelle Spielregeln](/images/Abb09_10_Schnittstelle_Spielregeln.png "Schnittstelle Spielregeln")

*Imagen: Interfaz de reglas del juego*

----

| Método | Breve descripción |
|---------|------------------|
| entregar configuración básica |Proporciona la configuración inicial de los parámetros óptimos de crecimiento para las plantas, como humedad y luz.|
| entregar condiciones válidas | Devuelve el conjunto de condiciones ambientales válidas para el crecimiento saludable de una planta específica.|
| verificar estrés ambiental | Comprueba si la planta está bajo estrés debido a factores externos como sequía o exceso de luz.|
|buscar condición crítica |Evalúa si una planta se encuentra en condiciones críticas que podrían llevar a su deterioro si no se corrigen.|
|comprobar estado de equilibrio| Comprueba si las condiciones ambientales actuales están en equilibrio, asegurando que no se requieran ajustes inmediatos.|

*Tabla: Métodos de reglas del juego de interfaz*

----

[Konzept 8.2 („Schach-Domänenmodell“)](/08_konzepte/02_domaenenmodell/)describe los parámetros de llamada y retorno utilizados en la interfaz (_Zug_, _Stellung_, _Farbe_).
Se pueden encontrar más detalles en la documentación del código fuente (javadoc).

### Ubicación/archivo de almacenamiento
La implementación del subsistema Green Cloud se encuentra en el paquete com.greencloud.rules...

### Puntos abiertos
* El subsistema actualmente no reconoce todas las condiciones críticas para el monitoreo ambiental y las plantas. En particular, las siguientes funcionalidades aún no se han implementado (→ Riesgo 11.2 „Complejidad de la Implementación“):

* Reglas avanzadas de sostenibilidad, como el agotamiento de nutrientes tras ciclos prolongados.
Verificación de condiciones repetitivas que podrían indicar un estado de estrés crónico.






