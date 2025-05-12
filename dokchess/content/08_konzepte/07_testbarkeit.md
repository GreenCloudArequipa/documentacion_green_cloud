+++
title = "Capacidad de prueba"
menuTitle = "8.7 Capacidad de prueba"
weight = 7
+++

## 8.7 Capacidad de prueba

En Green Cloud, un comportamiento incorrecto, como un movimiento inválido o un error en el monitoreo de la planta, es equivalente a un "movimiento ilegal". La funcionalidad de los módulos del sistema se garantiza mediante pruebas unitarias exhaustivas.

En la estructura del código fuente de Green Cloud, además de la carpeta principal de código, se encuentra una carpeta de pruebas que contiene una estructura reflejada de los módulos. Esta carpeta incluye las pruebas unitarias para las clases y funciones correspondientes, asegurando que todas las interacciones y configuraciones funcionen correctamente.  [JUnit 4](https://junit.org/junit4/) se realizan.

En Green Cloud, las pruebas unitarias que validan el comportamiento de clases individuales se denominan de forma similar a la clase que están probando, añadiendo "Test" al final. Además, existen pruebas de integración que validan la interacción entre los módulos, y en casos más complejos, se prueban sistemas completos para asegurar su correcto funcionamiento.

Las pruebas de integración, ubicadas en src/integTest, incluyen escenarios más complejos y de mayor duración. Estas pruebas pueden incluir, por ejemplo, la simulación del ciclo de vida completo de una planta monitoreada.

En muchas pruebas, es necesario presentar una "posición" o situación inicial de la planta, como su estado de crecimiento o los parámetros del entorno. Para ello, utilizamos una notación simplificada (como la notación FEN en ajedrez), que permite representar de manera compacta el estado del ecosistema sin necesidad de saltos de línea. Esto facilita las pruebas automatizadas, permitiendo verificar múltiples condiciones y escenarios de manera eficiente.
![Beispielstellung](/images/Abb09_24_Beispielstellung.png "Beispielstellung")

*Imagen: posición de ejemplo (el blanco en el tren es mate)*

LEn Green Cloud, las pruebas de funcionamiento no solo verifican que el sistema interactúe correctamente con los elementos del ecosistema, sino que también miden el rendimiento en condiciones reales. Esto incluye verificar si los tiempos de respuesta son adecuados cuando se presentan situaciones de monitoreo ejemplares, como la recopilación de datos o la respuesta del sistema a cambios en el entorno de las plantas.

Estas pruebas utilizan la anotación @Test junto con un parámetro de tiempo de espera. El éxito de estas pruebas depende del hardware disponible, asegurando que los tiempos de respuesta se ajusten a los requerimientos establecidos, similar a cómo se manejan las limitaciones en sistemas de alta demanda como los motores de ajedrez.