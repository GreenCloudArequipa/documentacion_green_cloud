+++
title = "Escenarios de calidad"
pre = "10.2 "
description = "Estos escenarios de calidad (o escenarios de evaluación) especifican los objetivos de calidad "
weight = 2
+++

## 10.2 Escenarios de calidad

Las primeras letras de los identificadores (ID) de los escenarios en la siguiente tabla representan la característica de calidad de nivel superior, por ejemplo W para mantenibilidad.
Diese Bezeichner finden auch im [Qualitätsbaum](/10_qualitaetsanforderungen/01_qualitaetsbaum/) Usar.
Los escenarios no siempre pueden asignarse claramente a una característica.
Por lo tanto, a veces aparecen varias veces en el árbol de calidad.
Los identificadores (ID) de los escenarios en la siguiente tabla están relacionados con las características de calidad de nivel superior, como **Mantenibilidad** (W), **Funcionalidad** (F), **Eficiencia** (E), y **Correctitud** (Z). Estos escenarios se emplean también en el **Árbol de Calidad** del proyecto GREEN CLOUD.

| ID   | Descripción |
|------|-------------|
| W01  | Un usuario con conocimientos básicos de tecnología de sensores y plantas desea empezar a utilizar GREEN CLOUD. La interfaz y la funcionalidad del sistema son claras en 15 minutos. |
| W02  | Un desarrollador busca documentación y ejemplos sobre cómo integrar sensores adicionales al sistema. Encuentra ejemplos inmediatos en la documentación y en el código fuente. |
| W03  | Un programador experimentado de Python quiere implementar un módulo para nuevos tipos de sensores. Encuentra el código fuente bien estructurado sin necesidad de ayuda externa. |
| W04  | Un desarrollador quiere implementar un nuevo algoritmo de control para las plantas en GREEN CLOUD. El algoritmo se integra fácilmente en el sistema sin modificar el código existente. |
| W05  | Un desarrollador integra una nueva representación de datos sobre el estado de las plantas utilizando un modelo de sensores basado en bits. El esfuerzo necesario es de una semana como máximo, incluida la adaptación de representaciones anteriores. |
| K01  | Un usuario quiere integrar un nuevo protocolo de comunicación para los sensores dentro de la interfaz de GREEN CLOUD. La configuración se realiza sin esfuerzo adicional en menos de 10 minutos. |
| F01  | El sistema debe detectar automáticamente cuando las condiciones de la planta son anormales y responder con una sugerencia de acción o alerta. |
| F02  | En una simulación del sistema, si una planta muestra signos de bajo riego, el sistema sugiere un plan de riego sin necesidad de intervención humana. |
| F03  | El sistema detecta una condición crítica de temperatura y ajusta la configuración de riego o luz automáticamente para prevenir el daño de la planta. |
| F04  | El sistema responde correctamente a una simulación de diversas condiciones extremas y ajusta el ambiente para asegurar el bienestar de la planta. |
| E01  | Durante la operación, el sistema responde a cualquier solicitud del usuario con un tiempo máximo de 3 segundos para mostrar el estado de la planta o realizar ajustes en los parámetros. |
| E02  | En una interfaz gráfica, el sistema responde en 5 segundos cuando el usuario solicita un cambio en las condiciones de la planta. El sistema notifica al usuario en un máximo de 10 segundos que está procesando el cambio. |
| Z01  | Si el sistema recibe un dato de sensor inválido o corrupto, rechaza el dato, permite ingresar uno nuevo y continúa funcionando sin errores. |
| Z02  | Si el sistema recibe un dato de sensor ilegal al inicio de la simulación, lo reconoce y termina el proceso sin continuar. |
| P01  | Un programador quiere integrar un nuevo tipo de sensor en GREEN CLOUD. Puede hacerlo sin modificar el código principal del sistema y solo con pequeñas configuraciones adicionales. |