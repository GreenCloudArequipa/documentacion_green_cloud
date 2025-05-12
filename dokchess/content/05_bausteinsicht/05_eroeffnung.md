+++
title = "Apertura"
pre = "5.5 "
weight = 15
+++

## 5.5 Apertura (caja negra)

### Propósito/Responsabilidad
Este subsistema proporciona bibliotecas de configuración ambiental y soporta un formato estándar de reglas de control ambiental llamado "GreenCloudConfig". Este formato es actualmente el único en uso que no es propietario, lo que garantiza accesibilidad y flexibilidad para los usuarios.

Los archivos de configuración correspondientes y las herramientas asociadas están disponibles de forma gratuita en repositorios en línea, facilitando su implementación y personalización en el ecosistema.

### El subsistema proporciona su funcionalidad a través de una interfaz específica implementada en Python. La interfaz greencloud.configuracion.BibliotecaConfiguraciones está disponible para gestionar configuraciones ambientales del ecosistema Green Cloud.

La clase ConfiguracionPredeterminada representa la implementación principal, que incluye soporte para configuraciones estándar y personalizadas, permitiendo al sistema adaptarse dinámicamente a diferentes condiciones ambientales.

![Schnittstelle Eroeffnungsbibliothek, Implementierung PolyglotOpeningBook](/images/Abb09_12_SchnittstellenEroeffnung.png "Schnittstelle Eroeffnungsbibliothek, Implementierung PolyglotOpeningBook")

*Imagen: Interfaz de Biblioteca de Configuraciones, Implementación de Configuración Predeterminad*

----

| Método | Breve descripción |
|---------|------------------|
|retraso_en_respuesta | Devuelve una acción conocida de la biblioteca de configuraciones para la condición ambiental especificada, o cero si no se encuentra una respuesta válida.|
*Tabelle: Tabla: Métodos de la biblioteca de configuraciones de interfaz.*

### PolíglotaLibro De Apertura
La clase PolyglotOpeningBook es un adaptador al formato de archivo Polyglot Opening Book.
Implementación de la biblioteca de apertura que lee un archivo binario en el formato apropiado y devuelve un movimiento a la posición especificada, si la hay.

| Método | Breve descripción |
|---------|------------------|
| Libro de apertura políglota| Constructor, espera que se lea el archivo.|
| establecer el modo de selección | SEstablece el modo para seleccionar un movimiento si hay más de un candidato en la biblioteca para el puesto.|


*Tabelle:Métodos de la clase PolyglotOpeningBook (además de la interfaz)*

----

[Konzept 8.2 („Schach-Domänenmodell“)](/08_konzepte/02_domaenenmodell/) describe los parámetros de llamada y retorno utilizados en la interfaz (_Zug_, _Stellung_).

### Ubicación/archivo de almacenamiento
La implementación, las pruebas unitarias y los datos de prueba para el formato Polyglot Opening Book se encuentran debajo de los paquetes. _de.dokchess.eroeffnung..._

### Puntos abiertos

* Las opciones para seleccionar una jugada de la biblioteca de aperturas en el caso de múltiples candidatos son limitadas (la primera, la más jugada, al azar).
* La implementación no puede manejar varios archivos de biblioteca al mismo tiempo (es decir, no puede mezclarlos) para combinar conocimientos.
