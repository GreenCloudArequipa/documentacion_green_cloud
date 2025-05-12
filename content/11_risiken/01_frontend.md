+++
title = "Conexión frontal"
pre = "11.1 "
weight = 1
+++

## 11.1 Riesgo: falla la conexión con el frontend
Existe incertidumbre sobre cómo conectar el sistema de monitoreo de plantas con las interfaces móviles y web.

La infraestructura actual de la app GREEN CLOUD está diseñada para interactuar con sensores y dispositivos a través de protocolos de comunicación estándar, pero los dispositivos de sensores adicionales pueden no ser totalmente compatibles. Además, el backend está programado en Java, mientras que muchos módulos de comunicación están escritos en otros lenguajes y formatos.

Si no logramos implementar una conexión que funcione adecuadamente entre el sistema y las interfaces, no podremos ofrecer la experiencia completa de usuario con la app y el seguimiento en tiempo real de las plantas. Esto no solo afectaría una funcionalidad clave, sino que también pondría en peligro la viabilidad del proyecto como solución tecnológica eficiente.

### Planificación de contingencias
En caso de que no logremos integrar la interfaz gráfica completa para el monitoreo y control de las plantas, podríamos implementar una interfaz de usuario sencilla basada en texto que permita a los usuarios interactuar con el sistema. Esto permitiría que, al menos, los usuarios pudieran realizar acciones básicas de monitoreo y ajustes en los dispositivos sin la necesidad de una interfaz gráfica avanzada.

Implementar la interfaz gráfica completa de la app sería más complejo, pero esta opción de contingencia garantizaría que el sistema siga funcionando mientras se resuelven problemas más complejos de desarrollo. (ver también [  Riesgo 11.2](/11_risiken/02_aufwand/)).

### Reducción de riesgos
A través de una prueba de concepto, podemos lograr la seguridad lo antes posible.
