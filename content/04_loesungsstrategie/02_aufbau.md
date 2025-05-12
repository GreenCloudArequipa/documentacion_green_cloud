+++
title = "Estructura"
pre = "4.2 "
weight = 11
+++

## 4.2 Estructura de GreenCloud

Green Cloud se implementa como un sistema modular utilizando un enfoque basado en objetos. Se divide aproximadamente en las siguientes partes:

* Monitoreo y gestión de las condiciones ambientales (temperatura, humedad, luz, etc.).
* Motor de análisis que procesa los datos de los sensores y determina las necesidades de las plantas (riego, luz, etc.).
* Conexión a una interfaz de usuario (app o plataforma web) que presenta los resultados y permite la interacción del usuario.
* Adaptador para integrar bases de datos externas que contienen información sobre las plantas autóctonas y su cuidado (por ejemplo, requerimientos de agua, luz, etc.).

Esta descomposición permite intercambiar cosas como el protocolo de comunicación o el formato de apertura de la biblioteca cuando sea necesario. Todas las partes se abstraen a través de interfaces, las implementaciones se ensamblan mediante inyección de dependencia. ([→ 5. Vista de Bloques](/05_bausteinsicht/), [→ Conceptos 8.1 „dependencias"](/08_konzepte/01_abhaengigkeiten/).
La descomposición también permite probar fácilmente el software, especialmente los algoritmos, de forma automática. ([→ dependencias 8.7 „Pruebas“](/08_konzepte/07_testbarkeit/)).

La interacción entre el intercambio de algoritmos se produce mediante el intercambio de estructuras de datos técnicamente motivadas, implementadas como clases.(_Figur_, _Zug_, ... [→ Conceptos 8.2 „Modelo de dominio“](/08_konzepte/02_domaenenmodell/)).
El objetivo aquí era conscientemente mejorar la comprensibilidad, a expensas de la eficiencia.
Sin embargo, GreenCloud consigue un nivel de gamificacion, como lo demuestra el juego de los escenarios correspondientes. ([→ 10. Requisitos de calidad ](/10_qualitaetsanforderungen/)).

El elemento central en el diseño de las estructuras de datos de Green Cloud es la situación ambiental de las plantas, que incluye la medición de sensores como temperatura, humedad y luz, y los ajustes necesarios para optimizar su crecimiento. Al implementar estas clases, se priorizó la legibilidad del código sobre la eficiencia, para facilitar el mantenimiento y futuras expansiones del sistema. Además, los objetos que representan las condiciones de las plantas son inmutables, lo que asegura que los datos sean consistentes y el sistema funcione de manera predecible y confiable [→ diseño 9.2 „Posicion de objetos](/09_entscheidungen/02_stellungsobjekte/)
