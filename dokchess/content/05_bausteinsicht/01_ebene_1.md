+++
title = "Nivel 1: Plataforma"
pre = "5.1 "
weight = 11
+++

## 5.1	Nivel 1


Green Cloud se divide en cuatro subsistemas principales, como se ilustra en la imagen a continuación. Las flechas discontinuas representan dependencias técnicas entre los subsistemas ("x -> y" significa "x depende de y"). Las cajas en el límite del sistema identifican los puntos de interacción con usuarios externos y sistemas de terceros.
([→ 3.2 Kontextabgrenzung](/03_kontextabgrenzung/02_technischer_kontext/)).

![GreenCloud, vista de bloques, nivel 1](/images/Abb09_08_Bausteinsicht_Ebene1.png "GreenCloud, Bausteinsicht, Ebene 1")

Imagen:Green Cloud, vista de bloque, nivel 1

----

| subsistema | Breve descripción |
|-----------|------------------|
| [XBoard-Protokoll](/05_bausteinsicht/02_xboard-protokoll/) | Realiza el seguimiento de las condiciones ambientales de las plantas y su salud.|
| [Spielregeln](/05_bausteinsicht/03_spielregeln/) | Evalúa los datos de las plantas para proporcionar recomendaciones personalizadas de cuidados. |
| [Engine](/05_bausteinsicht/04_engine/) | Proporciona elementos interactivos para involucrar a los usuarios en el cuidado de las plantas.|
| [Eröffnung](/05_bausteinsicht/05_eroeffnung/) | Proporciona movimientos de la literatura de aperturas para una situación de juego.|

*Tabla: Descripción general de los subsistemas de DokChess*

Abschnitt [→ 6.1 Zugermittlung Walkthrough](/06_laufzeitsicht/01_zugermittlung/)) Facilita la interacción del usuario con el sistema a través de una plataforma web y móvil.
