# Elección de patrón de diseño para el sistema VAR

* Status: Decidido 
* Deciders: Israel Peñalver Sánchez
* Date: 2018-11-14


## Context and Problem Statement

Vamos a tener una serie de cámaras situadas en el campo y se tendrá acceso a estas cámaras desde una sala en la que se mostraran todas las imágenes de las diferentes cámaras, se estará “emitiendo” a tiempo real en esta sala
Además se proporcionará al rarbitro a pie de campo una imagen sobre la que el pueda tomar una decisión en un determinado momento.

## Considered Options

* Facade
* Observer
* Command

## Decision Outcome

Chosen option: "Arquitectura de 3 niveles", because queremos realizar una separacion entre lo que ve el arbitro y los que ven los arbitros de sala y para ello usaremos la capa de interfaz de usuario, la de negocio y el acceso a datos.


## Pros and Cons of the Options

## Facade
Se aplica el patrón fachada cuando se necesite proporcionar una interfaz simple para un subsistema complejo, o cuando se quiera estructurar varios subsistemas en capas, ya que las fachadas serían el punto de entrada a cada nivel.

* Good, because Reduce la dependencia de los subsistemas.
* Good, because Si cambia la respuesta podemos cambiar la fachada si cambiar la petición.
* Good, because El cliente no necesita saber como implenta las respuestas.
* Bad, because Si son subsistemas muy distintos puede necesitar varias fachadas lo que aumenta la complejidad.

## Observer
Define una dependencia de uno-a-muchos entre objetos, de forma que cuando un objeto cambie de estado se notifique y se actualicen automáticamente todos los objetos que dependen de él

* Good, because Acoplamiento abstracto entre Subject y Observer.
* Good, because Todo lo que un objeto sabe de sus observadores es que tiene una lista de objetos que satisfacen la interfaz Observer.
* Bad, because se pueden producir actualizaciones inesperadas, que provocarían actualizaciones en cascada muy ineficientes.

## Command
Este patrón permite solicitar una operación a un objeto sin conocer realmente el contenido de esta operación, ni el receptor real de la misma. Para ello se encapsula la petición como un objeto, con lo que además facilita la parametrización de los métodos.

* Good, because Facilitar la parametrización de las acciones a realizar.
* Good, because Independizar el momento de petición del de ejecución.
* Good, because Desarrollar sistemas utilizando órdenes de alto nivel que se construyen con operaciones sencilla.
* Bad, because Potencial imprevisión de escalabilidad
* Bad, because Mal soporte de recuperacion en caso de fallo parcial

## Links:
* [ADR-0005](0005-Patrón-Ojo-Halcon.md)
