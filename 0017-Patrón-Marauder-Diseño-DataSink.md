# Elección de patrón de diseño para DataSink de Marauder

* Status: En evaluación
* Deciders: Daniel Carmona Pedrajas
* Date: 2018-11-13 


## Context and Problem Statement

Hemos elegido el patrón arquitectónico Pipes & Filters para el subsistema antipiratería Marauder.
Queremos elegir un patrón de diseño para el Data Sink. Almacenará las denuncias.

## Considered Options

* Patrón Proxy Virtual

## Decision Outcome

Chosen option: "Patrón Proxy Virtual", because único que permite almacenar de forma eficiente las denuncias.


## Pros and Cons of the Options

### Patrón Proxy Virtual

Este patrón proporciona un representante de otro objeto para controlar el acceso a éste.

* Good, becuase consume pocos recursos.
* Good, because evita la duplicación de objetos.
* Good, because facilita la comuncación con servidores.
* Bad, because añade otra capa de abstracción lo que puede ser malo si se accede al código del objeto real desde un cliente y se modifica.
