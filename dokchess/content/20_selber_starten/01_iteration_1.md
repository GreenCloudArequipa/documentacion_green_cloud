+++
title = "Iteración 1: perforar"
weight = 11
+++

### Objetivo de iteración

El motor interactúa con los jugadores humanos a través de una interfaz gráfica. Un “juego” se desarrolla a lo largo de varios movimientos.

### decisiones centrales

* Representación de la situación del juego (“posición”)
* Selección de una interfaz gráfica

### Tareas de implementación

* Representación del "tablero", campos, movimientos, etc.
* Conexión al frontend gráfico
* Generador de trenes trivial

### Inspiración de DokChess
* El modelo de dominio DokChess proporciona una forma de describir situaciones de juego en estructuras de datos. Puede encontrar una descripción general aquí (“8.2 Modelo de dominio de ajedrez”).
* Puede leer sobre la decisión de utilizar XBoard como protocolo de comunicación para conectar DokChess a interfaces gráficas aquí ("9.1 ¿Cómo se comunica el motor con el mundo exterior?"). Allí también se discuten alternativas.
* El tipo de comunicación entre DokChess y una interfaz gráfica se explica en uno de los conceptos: "8.3 Interfaz de usuario", puedes encontrarlo aquí.