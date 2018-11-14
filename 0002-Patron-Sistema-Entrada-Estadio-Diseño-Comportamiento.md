# Elección de patrón para el sistema de Entradas y Usuario????

* Status: Decidido 
* Deciders: Alejandro Checa Folguera, Ivan Martín Sanz, Jose Luis Lavado Sánchez
* Date: 2018-11-13 


## Context and Problem Statement

Tenemos varias interfaces que tienen que ser accedidas e intercomunicadas.Buscamos un patrón de arquitectura que nos permita enlazar todos los subsistemas en un sistema global.



## Considered Options

* Command
* Observer
* Iterator


## Decision Outcome

Chosen option: "Command", because 


## Pros and Cons of the Options

### Command

Este patrón permite solicitar una operación a un objeto sin conocer realmente el contenido de esta operación, ni el receptor real de la misma. Para ello se encapsula la petición como un objeto, con lo que además facilita la parametrización de los métodos.

* Good, because Facilitar la parametrización de las acciones a realizar.
* Good, because Independizar el momento de petición del de ejecución.
* Good, because Desarrollar sistemas utilizando órdenes de alto nivel que se construyen con operaciones sencilla.
* Bad, because Potencial imprevisión de escalabilidad
* Bad, because Mal soporte de recuperacion en caso de fallo parcial

### Observer

Define una dependencia de uno-a-muchos entre objetos, de forma que cuando un objeto cambie de estado se notifique y se actualicen automáticamente todos los objetos que dependen de él

* Good, because Acoplamiento abstracto entre Subject y Observer.
* Good, because Todo lo que un objeto sabe de sus observadores es que tiene una lista de objetos que satisfacen la interfaz Observer.
* Bad, because se pueden producir actualizaciones inesperadas, que provocarían actualizaciones en cascada muy ineficientes.

### Iterator

El patrón Iterador es un mecanismo de acceso a los elementos que constituyen una estructura de datos para la utilización de estos sin exponer su estructura interna.

* Good, because Permite recorrer las acciones sin conocer la organización.
* Good, because Perimite filtrar las acciones a realizar cambiando la implementacion.
* Good, because Simplifica el codigo de las colecciones de objetos pues la iteracciones van en el Iterator
* Bad, because Mayor dedicación inicial en el desarrollo.
* Bad, because Necisita estar acoplado con colecciones e iterador.


## Links:
* [ADR-0001](0001-Patron-PW-App-Usuario.md)
* [ADR-0002](0002-Patron-Sistemas-Estadio.md)
* [ADR-0003](0003-Patron-Gestion-Entrada-Tornos.md)
* [ADR-0004](0004-Patron-VAR.md)
* [ADR-0005](0005-Patron-Ojo-Halcon.md)
* [ADR-0006](0006-Patron-Marauder.md)
