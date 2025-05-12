+++
title = "Evaluación"
pre = "5.8 "
weight = 18
+++

## 5.8 Evaluación (cuadro negro)

### El módulo evalúa el estado del ecosistema desde la perspectiva de su sostenibilidad.
El resultado es un número, donde 0 describe una situación ambiental equilibrada, un número positivo indica una ventaja en términos de recursos o bienestar ecológico, y un número negativo señala una desventaja o un impacto ambiental negativo.
Cuanto mayor sea la magnitud del número, mayor será la ventaja o desventaja en la salud y sostenibilidad del ecosistema.
El módulo permite comparar diferentes condiciones ambientales entre sí para determinar cuál es más sostenible o beneficiosa para el medio ambiente.

### Interfaces
El módulo proporciona su funcionalidad a través de la interfaz greencloud.evaluacion.Evaluacion. La clase greencloud.evaluacion.EvaluacionBasica es una implementación simple que calcula la evaluación del estado del ecosistema basado en parámetros básicos como recursos disponibles, salud de las plantas y el impacto ambiental.
La interfaz también incluye constantes para evaluaciones típicas, como el nivel de sostenibilidad y el equilibrio ecológico, que se utilizan para realizar comparaciones rápidas entre diferentes condiciones.

![Schnittstelle Bewertung, Klasse ReineMaterialBewertung](/images/Abb09_15_SchnittstellenBewertung.png "Schnittstelle Bewertung, Klasse ReineMaterialBewertung")

*Imagen: Evaluación de interfaz, clase de evaluación de material puro*


| Método | Breve descripción |
|---------|------------------|
| evaluarEstado |Proporciona una evaluación del estado del ecosistema desde la perspectiva de la sostenibilidad y el bienestar ecológico. Cuanto mayor sea el valor, mejor será el estado del ecosistema.|
*Tabla: Métodos de evaluación de la interfaz*


### Calificación de material puro
La implementación sólo tiene en cuenta los recursos existentes (material).
Cada tipo de recurso o elemento en el ecosistema tiene un valor asignado (por ejemplo, plantas autóctonas 3, árboles 5, etc.). Los recursos en el ecosistema se suman en consecuencia.
Tus propios recursos cuentan positivamente, mientras que los recursos perdidos o dañados (como especies en peligro o recursos agotados) cuentan negativamente.
De la misma manera, si el ecosistema está equilibrado, el resultado es 0. Si pierdes un recurso clave, como un árbol o una especie autóctona, el valor bajará en consecuencia.

### Ubicación/archivo de almacenamiento
La implementación está debajo de los paquetes._de.dokchess.engine.bewertung..._

### Puntos abiertos
Al evaluar los recursos únicamente, no importa dónde se encuentren.
Una planta autóctona en una zona degradada tiene el mismo valor que una planta autóctona en un ecosistema prístino.
De manera similar, un árbol en una región marginal tiene el mismo valor que uno en una zona central del ecosistema.
Este enfoque simplificado permite realizar una evaluación básica del estado de los recursos, aunque hay un amplio margen para mejorar la evaluación, ya que Green Cloud busca fomentar la experimentación y la exploración de nuevas formas de calcular el valor ecológico en función de la ubicación y otros factores del entorno.
