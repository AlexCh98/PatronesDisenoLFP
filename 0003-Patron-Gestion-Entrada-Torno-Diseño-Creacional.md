# Elección de patrón para la gestión de entradas y tornos

* Status: Decidida 
* Deciders: Lucas Gómez Torres
* Date: 2018-10-31 


## Context and Problem Statement

Queremos elegir un patrón de diseño para programar  el sistema de gestión de entradas y el de tornos de entrada.



## Considered Options

* Singleton
* Abstract Factory

## Decision Outcome

Chosen option: "Singleton", because para gestionar las entradas y el sistema de tornos va a ser muy útil  ya que va a ocurrir varios cambios significativos en un estado concreto, por ejemplo la entrada pasa de estado "se vende" a se ha "vendido", y los tornos de "sin abrir" a "abierto".


## Pros and Cons of the Options 


### Singleton

 El patrón singleton es un patrón de diseño que permite restringir la creación de objetos pertenecientes a una clase o el valor de un tipo a un único objeto.
Su intención consiste en garantizar que una clase solo tenga una instancia y proporcionar un punto de acceso global a ella.

* Good, because tiene acceso controlado a una única instancia: encapsula su única instancia, puede tener un control estricto sobre como y cuando acceden a ella los clientes.
* Good, because tiene un espacio de nombres reducido: Es una mejora sobre las variables globales. Evita contaminar el espacio de nombres con variables globales que almacenan las instancias.
* Good, because permite el refinamiento de operaciones y la representación: Se puede crear una subclase de la clase Singleton, y es fácil configurar una aplicación con una instancia de esta clase extendida, incluso en tiempo de ejecución.
* Good, because permite un número variable de instancias: Hace que sea fácil permitir mas de una instancia de la clase. Solo se necesitaría cambiar la operación que otorga acceso a la instancia del Singleton.

* Bad, because tiene una cierta dificultad para realizar testing: Un Singleton es como una valor de variable global. Lo global y la orientación a objeto no son buenos amigos ya que introduce un “estado persistente”, es decir valores que se mantienen siempre dificultando el uso de objeto de reemplazo(mock) en test.
* Bad, because promociona el alto acoplamiento: Si hay algo que debe ser alto en la orientación a objetos es la cohesión y no el acoplamiento. El Singleton es instanciado directamente desde su propia clase promocionando el uso de métodos privados y estáticos. Esto acopla la clase que los use además de impedir el uso adecuado de inyección de dependencias.
* Bad, because tiene una restricción de ejecuciones paralelas: Aunque un objetivo del Singleton sea la gestión de un recurso compartido esto restringe operar de forma paralela a la aplicación y lo transforma en un cuello de botella de operaciones seriales que no es recomendable cuando la demanda es alta.








### Abstract Factory

El  Abstract Factory es un patrón de diseño para el desarrollo de software.
Debemos crear diferentes objetos, todos pertenecientes a la misma familia.
El problema que intenta solucionar este patrón es el de crear diferentes familias de objetos.



* Good, because aisla las clases de implementación: ayuda a controlar los objetos que se creen y encapsula la responsabilidad y el proceso de creación de objetos producto.
* Good, because hace fácil el intercambio de familias de productos. Solo necesitaremos cambiar de factory.
* Good, because fomenta la consistencia entre productos.






* Bad, because soportar nuevas clases de productos es dificil porque su interfaz arregla el bloque que pueden ser creados.
* Bad, because para añadir un nuevo producto, se requiere la implmentación de la interfaz y todos sus métodos.



## Links:
* [ADR-0002](0002-Patron-Sistemas-Estadio.md)
