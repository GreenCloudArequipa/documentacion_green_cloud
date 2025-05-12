+++
title = "Explotación florestal"
menuTitle = "8.6 Explotación florestal"
weight = 6
+++

## 8.6 Registro, registro, seguimiento

as opciones de análisis en Green Cloud son útiles para mejorar y ampliar el sistema, especialmente cuando se detectan comportamientos incorrectos.

La funcionalidad del sistema se puede verificar mediante pruebas unitarias, garantizando que las reglas de interacción (como las condiciones de las plantas y el funcionamiento de la mascota digital) se implementen correctamente.

Esto aplica principalmente a la correcta implementación de las configuraciones ambientales y al funcionamiento del sistema de monitoreo. ([→ 8.7 „Testbarkeit“](/08_konzepte/07_testbarkeit/)) y también para tus propias extensiones.

En Green Cloud, no se utiliza una salida de registro detallada, como log4j, para evitar la dependencia de bibliotecas de terceros y mantener el código limpio y simple.

En lugar de registros complejos, el sistema prioriza la comunicación directa con el usuario a través de la interfaz gráfica (móvil o web). Además, el sistema permite la comunicación entre el cliente y Green Cloud a través de protocolos sencillos y accesibles, asegurando una experiencia de usuario fluida sin complicaciones técnicas. ([→ 8.3 Benutzungsoberfläche](/08_konzepte/03_benutzungsoberflaeche/)) En Green Cloud, existe la opción para que el cliente registre la interacción con la maceta inteligente. Esto puede hacerse guardando un historial de actividades (como el crecimiento de las plantas y las interacciones con la mascota digital) en archivos de registro o mostrando una ventana en tiempo real durante el uso.

Esta funcionalidad permite a los usuarios revisar su progreso y tomar decisiones informadas sobre el cuidado de sus plantas, mejorando la experiencia educativa y de conciencia ambiental.



![Protokollfenster zum XBoard-Protokoll in Arena](/images/Abb09_23_ProtokollfensterArena.png "Protokollfenster zum XBoard-Protokoll in Arena")

*Imagen: Ventana de protocolo para el protocolo XBoard en Arena*

n Green Cloud, las herramientas de registro son valiosas cuando el sistema experimenta fallos y no está claro qué acción se estaba ejecutando. Dado que estas herramientas están disponibles, no se implementa un seguimiento detallado de las interacciones dentro del sistema, permitiendo que el usuario o el sistema identifiquen rápidamente cualquier inconveniente sin sobrecargar el código con funciones adicionales.
