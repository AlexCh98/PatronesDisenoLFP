# Elección de patrón de diseño para DataSink de Marauder

* Status: En evaluación
* Deciders: Daniel Carmona Pedrajas
* Date: 2018-11-13 


## Context and Problem Statement

Hemos elegido el patrón arquitectónico Pipes & Filters para el subsistema antipiratería Marauder.
Queremos elegir un patrón de diseño para el Data Sink. Almacenará las denuncias.

## Considered Options

* Patrón Proxy

## Decision Outcome

Chosen option: "Patrón Proxy", because único que permite almacenar de forma eficiente las denuncias.


## Pros and Cons of the Options

### Patrón Proxy

Este patrón permite solicitar una operación a un objeto sin conocer realmente el contenido de esta operación, ni el receptor real de la misma. Para ello se encapsula la petición como un objeto, con lo que además facilita la parametrización de los métodos.

* Good, because permite hacer colas de peticiones.
* Good, because puede hacerse cargo de los distintos tipos de peticiones que le lleguen del Pipe.
* Good, because no necesita saber el emisor de la petición.
* Bad, because puede necesitar muchas clases si se tienen muchas peticiones distintas.

### Patrón Template Method

El patrón Template Method crea el esqueleto de un algoritmo separando cada paso u operación de este en un objeto distinto.

* Good, because optimiza los recursos al poder saltarse pasos.
* Bad, because difícil de depurar y mantener porque hay que tener en cuenta todas las combinaciones de pasos.
