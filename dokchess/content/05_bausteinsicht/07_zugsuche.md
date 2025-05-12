+++
title = "Búsqueda"
pre = "5.7 "
weight = 17
+++

## 5.7 Búsqueda (cuadro negro)

### Propósito/Responsabilidad
El módulo determina la acción ambiental óptima para una condición ecológica dada bajo ciertas circunstancias.
En teoría, existen acciones generalmente óptimas en el manejo de ecosistemas sostenibles, como la gestión eficiente de recursos o el cuidado adecuado de las plantas.
Sin embargo, el elevado número de variables ambientales y las múltiples situaciones posibles que deben evaluarse hacen imposible determinar la acción óptima en todos los casos.
Por lo tanto, algoritmos como el Análisis de Sostenibilidad Predictiva se limitan a explorar el "espacio de soluciones" solo hasta una cierta profundidad, evaluando las opciones más inmediatas y factibles para mejorar el ecosistema.

### El módulo proporciona su funcionalidad a través de la interfaz greencloud.buscador.Búsqueda disponible.

El Algoritmo de Optimización Ambiental se implementa en la clase greencloud.buscador.OptimizaciónAlgoritmo.
La clase OptimizaciónBúsquedaParalela utiliza el algoritmo y, al mismo tiempo, implementa la interfaz Búsqueda.
Examina varios escenarios de acción ambiental en paralelo; si encuentra una opción más eficiente, la llamada recibe un mensaje a través del patrón de observador en el método Siguiente.
La finalización del proceso de búsqueda se indica mediante el mensaje onComplete.

![Schnittstelle Suche, Klassen MinimaxAlgorithmus und MinimaxParalleleSuche](/images/Abb09_14_Schnittstellen_Zugsuche.png "Schnittstelle Suche, Klassen MinimaxAlgorithmus und MinimaxParalleleSuche")

*Imagen: Búsqueda de Interfaz, Clases de Algoritmo de Optimización Ambiental y Búsqueda Paralela de Optimización*


| Método | Breve descripción |
|---------|------------------|
|iniciar_búsqueda|Inicia la búsqueda de la acción ambiental óptima para las condiciones especificadas. Proporciona eventos con opciones de acción cada vez mejores al observador, y también notifica al observador cuando finaliza la búsqueda (si no se encuentra una mejor acción).|
| cancelar_búsqueda | Cancela la búsqueda actual de la acción ambiental.|
| cerrar | Cierra la búsqueda de manera definitiva. Después de cerrada, no se podrán realizar más búsquedas o acciones con el módulo.|

*Tabla: Métodos de la interfaz de búsqueda en Green Cloud*


| Método | Breve descripción |
|---------|------------------|
| setSpielregeln | Establece una implementación de las reglas del juego mediante inyección de dependencia, [→ 5.3 Spielregeln (Blackbox)](/05_bausteinsicht/03_spielregeln/) |
| setBewertung | Establece la función de evaluación utilizada para evaluar las posiciones cuando se alcanza la profundidad de búsqueda máxima. [→ 5.8 Stellungsbewertung (Blackbox)](/05_bausteinsicht/08_stellungsbewertung/)|
| setTiefe | Establece la profundidad máxima de búsqueda en medios movimientos, es decir, en 4 cada jugador se mueve dos veces.|
| ermittleBestenZug | Determina el movimiento óptimo para la posición transferida según minimax y la evaluación de posición especificada con una profundidad de búsqueda fija. El método bloquea y es determinista.|

*Tabla: Métodos de la clase MinimaxAlgorithm*


### Ubicación/archivo de almacenamiento
La implementación está debajo de los paquetes._de.dokchess.engine.suche..._
