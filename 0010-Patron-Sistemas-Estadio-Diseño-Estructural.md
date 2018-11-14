# Elección de patrón estructural para el sistema del estadio.

* Status: Decidido 
* Deciders: Alejandro Checa Folguera, Ivan Martín Sanz, Jose Luis Lavado Sánchez
* Date: 2018-10-31 


## Context and Problem Statement

Tenemos varias interfaces que tienen que ser accedidas e intercomunicadas.Buscamos un patrón de arquitectura que nos permita enlazar todos los subsistemas en un sistema global.



## Considered Options

* Bridge
* Adapter
* Flyweight


## Decision Outcome

Chosen option: "Flyweight", because Reduce en gran cantidad el peso de los datos en un servidor, permitiendo así mejorar la velocidad en el tránsito de datos, permitiendo eliminar la redundancia cuando tenemos gran cantidad de objetos.


## Pros and Cons of the Options

### Bridge

Es una técnica usada en programación para desacoplar una abstracción de su implementación, de manera que ambas puedan ser modificadas independientemente sin necesidad de alterar por ello la otra.

* Good, because desacopla interfaz e implementación.
* Good, because mejora la extensibilidad.
* Good, because esconde los detalles de la implementación a los clientes.


### Adapter 

Convierte la interfaz de una clase en otra interfaz que el cliente espera. El adaptador permite a las clases trabajar juntas, lo que de otra manera no podría hacerse debido a sus interfaces incompatibles.

* Good, because Permite compatibilidad entre interfaces.
* Good, because Permite encapsular laas respuestas.
* Bad, because Añade complejidad al diseño.
* Bad, because Pierde caractersticas importantes si no se implementa con objetos y clases
* Bad, because La version mas simple necesita programación orientada a objetos.

### Flyweight

El patrón de dsieño estructural Flyweight sirve para eliminar o reducir la redundancia cuando tenemos gran cantidad de objetos que contienen información idéntica, además de lograr un equilibrio entre flexibilidad y rendimiento

* Good, because Reduce en gran cantidad el peso de los datos en un servidor.
* Good, because La modificación de una parte no afecta a las demás --> facil extensibilad y mantenimiento
* Bad, because Consume un poco más de tiempo para realizar las búsquedas.
* Bad, because Se complica la codificación lo que puede redundar en el aumento en la aparición de errores.
* Bad, becasue El cliente debe tener algún conocimiento de la implementación. Por esto, puede romper con la estructura cliente-servidor.



## Links:
* [ADR-0001](0001-Patron-PW-App-Usuario.md)
* [ADR-0002](0002-Patron-Sistemas-Estadio.md)
* [ADR-0003](0003-Patron-Gestion-Entrada-Tornos.md)
* [ADR-0004](0004-Patron-VAR.md)
* [ADR-0005](0005-Patron-Ojo-Halcon.md)
* [ADR-0006](0006-Patron-Marauder.md)

