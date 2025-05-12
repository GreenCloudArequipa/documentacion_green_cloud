+++
title = "Dependencias"
menuTitle = "8.1 Dependencias"
weight = 1
+++

## 8.1 Dependencias entre módulos

La plataforma Green Cloud fomenta la experimentación y expansión de su arquitectura, permitiendo a los usuarios implementar y ajustar sus propios módulos y componentes. Los módulos de la plataforma están diseñados para interactuar con interfaces específicas, las cuales pueden ser modificadas o extendidas según las necesidades del usuario.

En lugar de depender de un marco de Inyección de Dependencias (DI) específico, como se vería en algunas plataformas, Green Cloud permite a los usuarios gestionar sus dependencias creando implementaciones adecuadas e integrándolas a través de métodos establecidos. Este enfoque permite una gran flexibilidad, ya que los usuarios pueden experimentar con implementaciones alternativas y mejorar la funcionalidad mediante el uso de patrones de diseño como el Decorator.

Este tipo de estructura facilita la integración con tecnologías externas y es compatible con enfoques orientados a aspectos (AOP) basados en proxies dinámicos. Además, al seguir este enfoque de gestión de dependencias, se mejora la capacidad de prueba de los componentes. (→ Konzept 8.7).

A pesar de que no se utiliza un marco DI particular, los módulos de la plataforma están disponibles para personalización y prueba dentro del sistema. Los usuarios pueden integrar fácilmente sus propias soluciones para la inyección de dependencias, sin que se les restrinja a una configuración específica o un marco predefinido.






