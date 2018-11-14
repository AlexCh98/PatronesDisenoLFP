# Elección de patrón de diseño para la implementación de al gestión de entradas y tornos

* Status: Pendiente 
* Deciders: Lucas Gómez Torres
* Date: 13-11-18 


## Context and Problem Statement

Queremos elegir un patrón de diseño de comportamiento para la implementación del sistema de gestión de entradas y el de tornos de entrada y ver como se relacionan los objetos y las clases.

## Considered Options

* Chain of Responsibility
* 

## Decision Outcome

Chosen option: "Facade", because se utiliza para proporcionar una interfaz unificada de alto nivel para un conjunto de clases en un subsistema, lo que permite una mayor facilidad de uso y Simplifica el acceso a dicho conjunto de clases, ya que el cliente sólo se comunica con ellas a través de una única interfaz.
En definitiva que todos los eventos que se creen se organizen en una clase de alto nivel para que luego sea mas facil usarlas al estar comunicados con los clientes a través de una sola interfaz.

## Pros and Cons of the Options 


### Proxy

 El patrón proxy es un patrón de diseño estructural que tiene como propósito proporcionar un intermediario de un objeto para controlar su acceso.
Dependiendo de la clase de proxy, el objeto proxy redirige las peticiones al objeto real que representa.

* Good, because se tiene más Control: Podemos restringir acceso a usuarios y dar salida solamente al proxy.
* Good, because usa filtros: Nuestro proxy puede denegar peticiones de algunos lugares.
* Good, because son anónimos: Todos los usuarios se identificarán como uno solo entonces es difícil identificar cuál es cuál.
* Good, because permite un número variable de instancias: Hace que sea fácil permitir mas de una instancia de la clase. Solo se necesitaría cambiar la operación que otorga acceso a la instancia del Singleton.
* Good, because se introduce un nivel de indirección en el acceso al objeto, que permite al apoderado remoto ocultar el hecho de que el objeto reside en un espacio de direcciones distinto, al apoderado virtual realizar optimizaciones como la creación de objetos por demanda y al apoderado de protección y a las referencias “inteligentes” realizar tareas adicionales de vigilancia sobre el objeto al que se accede. No obstante todo esto puede resultar un inconveniente, por motivos de claridad e inteligibilidad del diseño.
* Good, because facilita otra optimización, relacionada con la creación de objetos por demanda: la técnica de COPY-ON-WRITE, que sólo hace efectiva la copia de un objeto oneroso cuando el acceso a él es de escritura, no de lectura.



* Bad, because almacenar las páginas y objetos que los usuarios solicitan puede suponer una violación de la intimidad para algunas personas.
* Bad, because promociona el alto acoplamiento: Si hay algo que debe ser alto en la orientación a objetos es la cohesión y no el acoplamiento. El Singleton es instanciado directamente desde su propia clase promocionando el uso de métodos privados y estáticos. Esto acopla la clase que los use además de impedir el uso adecuado de inyección de dependencias.
* Bad, because tiene una restricción de ejecuciones paralelas: Aunque un objetivo del Singleton sea la gestión de un recurso compartido esto restringe operar de forma paralela a la aplicación y lo transforma en un cuello de botella de operaciones seriales que no es recomendable cuando la demanda es alta.








### Facade

El  facade es un patrón de diseño estructural que viene  motivado por la necesidad de estructurar un entorno de programación y reducir su complejidad con la división en subsistemas, minimizando las comunicaciones y dependencias entre estos.

Los clientes que se comunican con el subsistema enviando peticiones al objeto Fachada, el cual las reenvía a los objetos apropiados del subsistema.
Los objetos del subsistema realizan el trabajo final, y la fachada hace algo de trabajo para pasar de su interfaz a las del subsistema.
Los clientes que usan la fachada no tienen que acceder directamente a los objetos del subsistema.


* Good, because para modificar las clases de los subsistemas, sólo hay que realizar cambios en la interfaz/fachada, y los clientes pueden permanecer ajenos a ello. Además, y como se mencionó anteriormente, los clientes no necesitan conocer las clases que hay tras dicha interfaz.
* Good, because al separar al cliente de los componentes del subsistema, se reduce el número de objetos con los que el cliente trata, facilitando así el uso del subsistema.
* Good, because se promueve un acoplamiento débil entre el subsistema y sus clientes, eliminándose o reduciéndose las dependencias.
* Good, because no existen obstáculos para que las aplicaciones usen las clases del subsistema que necesiten. De esta forma podemos elegir entre facilidad de uso y generalidad.

* Bad, because varios clientes necesiten acceder a subconjuntos diferentes de la funcionalidad que provee el sistema, podrían acabar usando sólo una pequeña parte de la fachada, por lo que sería conveniente utilizar varias fachadas más específicas en lugar de una única global.
* Bad, because se tiene considerar el caso en que varios clientes necesiten acceder a subconjuntos diferentes de la funcionalidad que provee el sistema, podrían acabar usando sólo una pequeña parte de la fachada, por lo que sería conveniente utilizar varias fachadas más específicas en lugar de una única global.




## Links:
* [ADR-0002](0002-Patron-Sistemas-Estadio.md)
