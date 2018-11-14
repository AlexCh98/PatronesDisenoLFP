# Elección de patrón de diseño para la implementación de al gestión de entradas y tornos

* Status: Decidida 
* Deciders: Lucas Gómez Torres
* Date: 13-11-18 


## Context and Problem Statement

Queremos elegir un patrón de diseño de comportamiento para la implementación del sistema de gestión de entradas y el de tornos de entrada y ver como se relacionan los objetos y las clases.

## Considered Options

* Chain of Responsibility
* Iterator

## Decision Outcome

Chosen option: "Chain of Responsability", because los eventos  que piden los respectivos clientes se van a poder controlar por los distintos manejadores que definiran una interfaz especifica para tratar las peticiones de los clientes. 

## Pros and Cons of the Options 


### Chain of Responsibility

 El patrón Chain of Responsibility es un patrón de comportamiento que evita acoplar el emisor de una petición a su receptor dando a más de un objeto la posibilidad de responder a una petición. Para ello, se encadenan los receptores y pasa la petición a través de la cadena hasta que es procesada por algún objeto.
Dependiendo de la clase de proxy, el objeto proxy redirige las peticiones al objeto real que representa.

* Good, because reduce el acoplamiento. El patrón libera a un objeto de tener que saber qué otro objeto maneja una petición. Ni el receptor ni el emisor se conocen explícitamente entre ellos, y un objeto de la cadena tampoco tiene que conocer la estructura de ésta. Por lo tanto, simplifica las interconexiones entre objetos. En vez de que los objetos mantengan referencias a todos los posibles receptores, sólo tienen una única referencia a su sucesor.
* Good, because añade flexibilidad para asignar responsabilidades a objetos. Se pueden añadir o cambiar responsabilidades  entre objetos para tratar una petición modificando la cadena de ejecución en tiempo de ejecución. Esto se puede combinar con la herencia para especializar los manejadores estáticamente.
* Good, because tanto el manejador como el cliente no saben lo que no está en sus manos saber. Tampoco saben de la estructura de la cadena en sí.
* Good, because se sabe como llegar al primer eslabón y se sabe que llegará al último, pero no se sabe la implementación de por medio.

* Bad, because no garantiza la recepción. Dado que las peticiones no tienen un receptor explícito, no hay garantías de que sean manejadas. La petición puede alcanzar el final de la cadena sin haber sido procesada.




### Iterator

El patrón Iterador es un mecanismo de acceso a los elementos que constituyen una estructura de datos para la utilización de estos sin exponer su estructura interna.

* Good, because Permite recorrer las acciones sin conocer la organización.
* Good, because Perimite filtrar las acciones a realizar cambiando la implementacion.
* Good, because Simplifica el codigo de las colecciones de objetos pues la iteracciones van en el Iterator
* Bad, because Mayor dedicación inicial en el desarrollo.
* Bad, because Necisita estar acoplado con colecciones e iterador.




## Links:
* [ADR-0002](0002-Patron-Sistemas-Estadio.md)
