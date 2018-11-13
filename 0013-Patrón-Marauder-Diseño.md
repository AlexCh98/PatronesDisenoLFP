# Elección de patrón de diseño para Pipes de Marauder

* Status: En evaluación
* Deciders: Daniel Carmona Pedrajas
* Date: 2018-11-13 


## Context and Problem Statement

Hemos elegido el patrón arquitectónico Pipes & Filters para el subsistema antipiratería Marauder.
Queremos elegir un patrón de diseño para los Pipes que contienen la IA de Marauder. Los Pipes tienen que crear posibles denuncias que pasarán al Filter.


## Considered Options

* Patrón Builder
* Patrón Strategy


## Decision Outcome

Chosen option: "Patrón Strategy" + "Patrón Builder", because el patrón Strategy permite navegar distintos sitios web y necesita el builder para hacer instancias de Denuncias.


## Pros and Cons of the Options

### Patrón Strategy

El patrón permite adaptar la estrategia que tiene la IA dependiendo de si está buscando en Facebook, Twitter u otra página de internet.

* Good, because optimiza el análisis de las páginas web.
* Good, because se puede pasar datos al algoritmo desde el objeto que contiene a Strategy.
* Good, because aumenta la cohesión de la IA.
* Bad, because tiene menor eficiencia al aumentar el número de objetos creados.

### Patrón Builder

El patrón Builder separa la construcción de un objeto complejo de su representación de modo que con un sólo proceso de construcción se creen distintos tipos de representaciones. Lo usará para generar las denuncias

* Good, because permite crear distintos tipos de denuncias dependiendo de si vienen de Twitter, Facebook u otra página.
* Good, because reduce el acoplamiento.
* Good, because mayor control en el proceso de construcción de un objeto.
