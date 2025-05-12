+++
title = "Colocar objetos"
menuTitle = "9.2 Colocar objetos"
weight = 2
+++

## 9.2 ¿Los objetos posicionales son cambiables o no??

### Respecto a la pregunta

En el contexto del proyecto GREEN CLOUD, la información recolectada por los sensores (datos ambientales como humedad, temperatura, niveles de luz, entre otros) debe ser procesada y compartida entre diferentes módulos del sistema para garantizar la sostenibilidad y la eficiencia del ecosistema vegetal. Surge entonces la pregunta: ¿diseñamos la estructura de datos asociada para que sea mutable o inmutable?

* Análisis
Datos Mutables:
Los datos recolectados por los sensores cambian constantemente a lo largo del tiempo debido a variaciones en el entorno. Durante el procesamiento, los módulos del sistema pueden realizar cálculos predictivos, comparar valores históricos, y decidir sobre acciones (como activar riegos o alertas). Si la estructura de datos es mutable, los módulos podrán actualizar directamente el estado actual, lo que permite un diseño más simple y con menor uso de memoria.

Sin embargo, este enfoque puede complicar la depuración y el manejo de concurrencia, ya que múltiples módulos podrían intentar modificar los mismos datos simultáneamente, generando posibles errores o inconsistencias.

* Datos Inmutables:
En este enfoque, cada cambio en los datos genera una nueva instancia de la estructura, preservando los valores anteriores. Esto facilita el análisis retrospectivo y asegura que cada módulo trabaje con datos consistentes y aislados. Además, el diseño inmutable es más seguro para la concurrencia, ya que no existen riesgos de sobrescritura.

No obstante, este enfoque puede aumentar el consumo de memoria y reducir la eficiencia en operaciones donde los datos cambian con alta frecuencia.

* Decisión
Dado que GREEN CLOUD depende de la interacción de múltiples módulos (sensores, plataforma gráfica, y algoritmos de análisis), y que los cambios en la estructura de datos afectarán a todo el sistema, la elección debe equilibrar simplicidad, seguridad, y eficiencia.

Se optará por una estructura de datos híbrida:

Los datos de entrada (recolectados por los sensores) serán tratados como inmutables para garantizar consistencia y trazabilidad. Cada cambio generará una nueva instancia, preservando un historial que puede ser usado para análisis predictivos y auditoría.
Los datos temporales (utilizados dentro de los módulos para cálculos intermedios) serán mutables, ya que estas estructuras no necesitan ser compartidas entre módulos ni preservadas.
Este enfoque permite implementar algoritmos más eficientes en cada módulo y, al mismo tiempo, mantener la integridad del sistema completo.

### Impacto en GREEN CLOUD
El diseño híbrido asegura:

Trazabilidad completa del estado ambiental.
Robustez en la integración de múltiples módulos.
Flexibilidad para realizar modificaciones futuras en la arquitectura, minimizando el impacto en el sistema general.
La interfaz para el intercambio de datos entre módulos será diseñada cuidadosamente para minimizar dependencias rígidas, permitiendo futuras actualizaciones sin afectar a todo el sistema GREEN CLOUD.


### Factores de influencia relevantes

* Condiciones de contorno ([→ 2.1 „Technische Randbedingungen“](/02_randbedingungen/01_technisch/))
* Lenguaje de implementación 
 * equipo de hardware moderado
* Características de calidad significativamente afectadas. ([→ 1.2 „Qualitätsziele“](/01_einfuehrung/02_qualitaetsziele/))
 *Objetivo de calidad: invitar a una plataforma de experimentación (cambiabilidad)
 * Objetivo de calidad: Nivel de juego aceptable (idoneidad funcional)
 * Objetivo de calidad: Respuesta rápida a los movimientos (eficiencia)
* Riesgos involucrados
 * Esfuerzo de implementación demasiado alto([→ 11.2](/11_risiken/02_aufwand/))
 * Alcanzar el nivel de juego falla ([→ 11.3](/11_risiken/03_spielstaerke/))

### Suposiciones

* Estructura de datos eficiente: Se asumirá que es posible implementar un modelo de objetos sólido (clases como Sensor, Planta, y Acción) para gestionar los datos del ecosistema vegetal, garantizando tiempos de respuesta adecuados.
* Preparación para algoritmos concurrentes: La estructura de datos estará diseñada para soportar futuras implementaciones concurrentes, clave para procesar múltiples sensores y módulos simultáneamente.
* Impacto esperado: Este enfoque permitirá modularidad, compatibilidad con sistemas distribuidos y decisiones rápidas (como activar riego o emitir alertas), cumpliendo con los estándares de calidad y escalabilidad del sistema.

### Alternativas consideradas
### Opción 1: Estructura mutable  
Los métodos modifican directamente el estado de la estructura, por ejemplo, actualizando lecturas de sensores o valores ambientales.

```python
estado = EstadoInicial()  # Estado inicial
estado.actualizar_sensor(humedad=45)  # Actualiza el valor de humedad
estado.revertir_actualizacion()  # Vuelve al estado inicial


### Opción 2: Estructura mutable 
estado = EstadoInicial()  # Estado inicial
nuevo_estado = estado.actualizar_sensor(humedad=45)  # Genera un nuevo estado


