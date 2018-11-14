# Elección de patrón de diseño creacional para el sistema global

* Status: Pendiente 
* Deciders: Alejandro Checa Folguera, Ivan Martín Sanz, Jose Luis Lavado Sánchez
* Date: 2018-11-13


## Context and Problem Statement

Tenemos varias interfaces que tienen que ser accedidas e intercomunicadas.Buscamos un patrón de diseño que nos permita acceder a todos los subsistemas mediante servicios.




## Considered Options

* Object Pool
* Abstract Factory
* Prototype


## Decision Outcome

Chosen option: "Object Pool", because favorece la reutilización de objetos, además permite controlar el número de instancias, y reduce el coste de creación de objetos


## Pros and Cons of the Options

### Object Pool

Un patrón de diseño object pool puede resultar útil cuando es necesario trabajar con un gran número de objetos que son particularmente costosos para instanciar y cada objeto solo se necesita durante un corto período de tiempo.

* Good, because Reduce el coste de instancia a una sola vez.
* Good, because Se puede controlar el numero de instancias a un servicio.
* Good, because Solo se instancia el servicio una sola vez.
* Bad, because Si llegas al maximo de servicios puede desbordar o generar excepciones.
* Bad, because Necesita una implementación extra para cuando el pool esta vacío.

### Abstract Factory

Este patrón, está aconsejado cuando se prevé la inclusión de nuevas familias de productos, pero puede resultar contraproducente cuando se añaden nuevos productos o cambian los existentes, puesto que afectaría a todas las familias creadas.


* Good, because le permite probar fácilmente la unión de una aplicación (es decir, simular / apilar) ciertas partes de su aplicación para que pueda construir y probar las otras partes
* Good, because le permite cambiar el diseño de su aplicación más fácilmente, esto se conoce como acoplamiento suelto
* Bad, because Hace que el código sea más difícil de leer, ya que su código está detrás de una abstracción que a su vez puede ocultar abstracciones.
* Bad, because Puede clasificarse como antipatrón cuando se usa incorrectamente, 


### Prototype

Tiene como finalidad crear nuevos objetos clonando una instancia creada previamente.

* Good, because permite ocultar las clases producto (prototipos concretos) del cliente.
* Good, because permite que el cliente trabaje con clases dependientes de la aplicación sin cambios.
* Good, because hace posible añadir y eliminar productos en tiempo de ejecución, esto proporciona una configuración dinámica de la aplicación.
* Bad, because la jerarquía de prototipos debe ofrecer la posibilidad de clonar un elemento y esta operación puede no ser sencilla de implementar.
* Bad, because la clonación se produce frecuentemente, el coste puede ser importante.


## Links:
* [ADR-0001](0001-Patron-PW-App-Usuario.md)
* [ADR-0002](0002-Patron-Sistemas-Estadio.md)
* [ADR-0003](0003-Patron-Gestion-Entrada-Tornos.md)
* [ADR-0004](0004-Patron-VAR.md)
* [ADR-0005](0005-Patron-Ojo-Halcon.md)
* [ADR-0006](0006-Patron-Marauder.md)

