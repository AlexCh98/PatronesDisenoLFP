# Elección de patrón para la gestión de entradas y tornos

* Status: Decidida 
* Deciders: Lucas Gómez Torres
* Date: 2018-10-31 


## Context and Problem Statement

Queremos elegir un patrón arquitectónico para el sistema de sincronización de entradas y para la gestión de tornos de entrada.



## Considered Options

* Arquitectura dirigida por eventos
* Pipes/filters

## Decision Outcome

Chosen option: "Arquitectura dirigida a eventos", because para gestionar las entradas y el sistema de tornos va a ser muy útil  ya que va a ocurrir varios cambios significativos en un estado concreto, por ejemplo la entrada pasa de estado "se vende" a se ha "vendido", y los tornos de "sin abrir" a "abierto".


## Pros and Cons of the Options 


### Arquitectura dirigida por eventos

La Arquitectura dirigida por eventos es un patrón de arquitectura software que promueve la producción, detección, consumo de, y reacción a eventos. Un evento puede ser definido como un cambio significativo en un estado

* Good, because se desvinculan productores y consumidores.
* Good, because se desvinculan productores y consumidores.
* Good, because es fácil agregar nuevos consumidores al sistema.
* Good, because los consumidores pueden responder a eventos inmediatamente a medida que llegan.
* Good, because  es muy escalable y distribuida.
* Good, because los subsistemas tienen vistas independientes del flujo de eventos.

* Bad, because posibilidad de desborde.
* Bad, because no se puede medir la escalabilidad.
* Bad, because tiene pobre comprensibilidad: Puede ser difícil prever qué pasará en respuesta a una acción.
* Bad, because cada evento se transmite de forma acoplada

### Pipes/filters

La Arquitectura pipes and filters es un patrón de arquitectura software que promueve una estructura para los sistemas que procesan un flujo de datos. Cada paso de procesamiento se encapsula en un componente de filtro. Los datos pasan a través de tuberías entre filtros adyacentes.



* Good, because tiene flexibilidad intercambiando filters. 
* Good, because no requieren archivos intermedios.


* Bad, because compartir información de estado es costoso e inflexible.
* Bad, because no tienes un buen manejo de errores
* Bad, because no se usan adecuadamente los filtros y buffer
* Bad, todos los filtros tienen el mismo pie (ineficiencia )


## Links:
* [ADR-0002](0002-Patron-Sistemas-Estadio.md)
