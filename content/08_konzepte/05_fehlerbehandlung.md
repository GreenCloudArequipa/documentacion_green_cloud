+++
title = "Manejo de errores"
menuTitle = "8.5 Manejo de errores"
weight = 5
+++

## 8.5 Manejo de errores 
Green Cloud no tiene su propia interfaz exclusiva para la interacción, por lo que debe comunicar los problemas al usuario a través de la interfaz gráfica (móvil o web).

Los métodos que gestionan las interacciones, como la configuración de la planta o el ajuste de las condiciones ambientales, pueden generar excepciones de tiempo de ejecución. Cuando ocurre un error, como intentar configurar condiciones incompatibles para una planta (por ejemplo, temperatura extremadamente baja para una planta tropical), el sistema genera mensajes de error para alertar al usuario, por ejemplo, "Error: Las condiciones son inapropiadas para esta planta."

Si el sistema encuentra un archivo de datos corrupto o una configuración incorrecta (como una planta en un entorno sin suficiente luz), también se lanzan excepciones específicas, como "Error de lectura de archivo" o "Configuración no válida".

Las excepciones específicas se documentan en el sistema, y cualquier error inesperado que no sea una excepción gestionada se considera un error de programación. En estos casos, los usuarios pueden ser dirigidos a un canal de soporte, como un formulario de contacto o una página de informes de errores, para ayudar a mejorar el sistema.

El sistema de Green Cloud también puede comunicar los errores a través de la interfaz gráfica mediante cuadros de diálogo de alerta, asegurando que el usuario reciba retroalimentación clara para corregir el problema.

![DokChess-Fehlermeldung visualisiert durch Arena](/images/Abb09_22_FehlermeldungArena.png "DokChess-Fehlermeldung visualisiert durch Arena")

*Imagen: Mensaje de error de Greencloud visualizado por usuario*

Cuando Green Cloud detecta un error, como la falta de un archivo de configuración, muestra un mensaje claro, por ejemplo:

"Error: Archivo no encontrado."
