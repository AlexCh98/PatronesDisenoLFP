# Elección de patrón de diseño para la Ingesta de Eventos de Ojo de Halcón

* Status: Pendiente 
* Deciders: Israel Peñalver Sánchez
* Date: 2018-11-14


## Context and Problem Statement

Vamos a elegir un patrón para resolver el problema como hacer llegar al arbitro el mensaje correspondiente una vez que el actor (el balón), genere un evento.

## Considered Options

* Facade (FACHADA)
* Flyweight

## Decision Outcome

Chosen option: "Facade", because proporciona una interfaz simple para un subsistema complejo, una interfaz unificada de alto nivel que, representando a todo un subsistema, facilita su uso.

## Pros and Cons of the Options

### Facade

Se aplica el patrón fachada cuando se necesite proporcionar una interfaz simple para un subsistema complejo, o cuando se quiera estructurar varios subsistemas en capas, ya que las fachadas serían el punto de entrada a cada nivel.

* Good, because Reduce la dependencia de los subsistemas.
* Good, because Si cambia la respuesta podemos cambiar la fachada si cambiar la petición.
* Good, because El cliente no necesita saber como implenta las respuestas.
* Bad, because Si son subsistemas muy distintos puede necesitar varias fachadas lo que aumenta la complejidad.

### Flyweight

El patrón de dsieño estructural Flyweight sirve para eliminar o reducir la redundancia cuando tenemos gran cantidad de objetos que contienen información idéntica, además de lograr un equilibrio entre flexibilidad y rendimiento

* Good, because Reduce en gran cantidad el peso de los datos en un servidor.
* Good, because La modificación de una parte no afecta a las demás --> facil extensibilad y mantenimiento
* Bad, because Consume un poco más de tiempo para realizar las búsquedas.
* Bad, because Se complica la codificación lo que puede redundar en el aumento en la aparición de errores.
* Bad, becasue El cliente debe tener algún conocimiento de la implementación. Por esto, puede romper con la estructura cliente-servidor.

## Links:
* [ADR-0004](0004-Patrón-VAR.md)
