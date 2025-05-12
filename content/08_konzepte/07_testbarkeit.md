+++
title = "Capacidad de prueba"
menuTitle = "8.7 Capacidad de prueba"
weight = 7
+++

## 8.7 Capacidad de prueba

En el contexto de Green Cloud, cualquier desviación del comportamiento esperado de los módulos, ya sea por una operación inválida o una anomalía detectada en el monitoreo de la planta, se considera una transgresión del estado válido. La integridad funcional de cada módulo del sistema se robustece mediante un riguroso esquema de pruebas unitarias.

La arquitectura del código fuente de Green Cloud adopta una organización donde, paralelamente al directorio principal (src/main), reside un directorio dedicado a las pruebas (src/test). Este directorio replica la estructura modular del código principal, albergando las pruebas unitarias correspondientes a cada clase y función. La ejecución de estas pruebas, implementadas con JUnit 4, garantiza la correcta operatividad de las interacciones y configuraciones a nivel granular.

Dentro de Green Cloud, la convención de nomenclatura para las pruebas unitarias de clases individuales sigue el patrón NombreDeLaClaseTest. Adicionalmente, se implementan pruebas de integración para validar la comunicación y colaboración entre distintos módulos, y en escenarios que demandan una visión holística, se ejecutan pruebas de sistema para verificar la correcta interacción de los componentes en su conjunto.

Las pruebas de integración, localizadas en el directorio src/integTest, abarcan casos de uso más complejos y de mayor duración. Estas pruebas    pueden simular flujos de trabajo completos, como el ciclo de vida integral de una planta bajo supervisión.

Para la inicialización de diversos escenarios de prueba, es fundamental definir un estado inicial o una condición de partida para la planta, que puede incluir su etapa de desarrollo o las variables ambientales relevantes. Con este fin, se emplea una notación de estado compacta (análoga a la notación FEN del ajedrez), que permite representar de forma concisa el estado del ecosistema sin la necesidad de múltiples líneas. Esta representación optimiza la automatización de las pruebas, facilitando la verificación eficiente de múltiples condiciones y escenarios.
![Beispielstellung](/img/fuente.png "Beispielstellung")



En Green Cloud, las pruebas de funcionamiento no solo verifican que el sistema interactúe correctamente con los elementos del ecosistema, sino que también miden el rendimiento en condiciones reales. Esto incluye verificar si los tiempos de respuesta son adecuados cuando se presentan situaciones de monitoreo ejemplares, como la recopilación de datos o la respuesta del sistema a cambios en el entorno de las plantas.

Estas pruebas utilizan la anotación @Test junto con un parámetro de tiempo de espera. El éxito de estas pruebas depende del hardware disponible, asegurando que los tiempos de respuesta se ajusten a los requerimientos establecidos, similar a cómo se manejan las limitaciones en sistemas de alta demanda como los motores de ajedrez.