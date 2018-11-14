# Elección de patrón de diseño para el sistema VAR

* Status: Decidido 
* Deciders: Israel Peñalver Sánchez
* Date: 2018-11-14


## Context and Problem Statement

Vamos a tener una serie de cámaras situadas en el campo y se tendrá acceso a estas cámaras desde una sala en la que se mostraran todas las imágenes de las diferentes cámaras, se estará “emitiendo” a tiempo real en esta sala
Además se proporcionará al rarbitro a pie de campo una imagen sobre la que el pueda tomar una decisión en un determinado momento.

## Considered Options

* Observer
* Command
* Facade

## Decision Outcome

Chosen option: "Arquitectura de 3 niveles", because queremos realizar una separacion entre lo que ve el arbitro y los que ven los arbitros de sala y para ello usaremos la capa de interfaz de usuario, la de negocio y el acceso a datos.


## Pros and Cons of the Options

## Facade
Se aplica el patrón fachada cuando se necesite proporcionar una interfaz simple para un subsistema complejo, o cuando se quiera estructurar varios subsistemas en capas, ya que las fachadas serían el punto de entrada a cada nivel.

* Good, because Reduce la dependencia de los subsistemas.
* Good, because Si cambia la respuesta podemos cambiar la fachada si cambiar la petición.
* Good, because El cliente no necesita saber como implenta las respuestas.
* Bad, because Si son subsistemas muy distintos puede necesitar varias fachadas lo que aumenta la complejidad.

## Links:
* [ADR-0005](0005-Patrón-Ojo-Halcon.md)
