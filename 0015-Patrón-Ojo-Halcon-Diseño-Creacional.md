# Elección de patrón para prducir el evento del Ojo Halcón

* Status: Pendiente 
* Deciders: Israel Peñalver Sánchez
* Date: 2018-11-14


## Context and Problem Statement

Vamos a elegir un patrón para resolver el problema de como creamos el objeto que va a generar el evento, en este caso el objeto del que hablamos es el balón que genera eventos según este localizadoo en el campo.

## Considered Options

* Singleton

## Decision Outcome

Chosen option: "Singleton", because optamos por que solo pueda haber en cada instante una instancia del objeto que queremos que genere el evento.


## Pros and Cons of the Options

### SINGLETON

Las arquitecturas dirigidas por eventos (EDA Event-driven Architectures) se
basan en la detección, consumo y reacción a eventos.
Un evento representa un cambio significativo en el estado de un sistema.
Los eventos se transmiten entre sistema poco acoplados (“loosely coupled”) mediante mensajes.


* Good, because Simplicidad
* Good, because Modularidad, una sola modalidad para eventos diversos
* Good, because Evolución, se pueden reemplazar componentes suscriptoses
* Bad, because Posibilidad de desborde
* Bad, because Pobre comprensibilidad
* Bad, because No hay mucho soporte de recuperacón en caso de fallo parcial

## Links:
* [ADR-0004](0004-Patrón-VAR.md)
