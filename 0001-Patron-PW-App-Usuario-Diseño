# Elección de patrón para el sistema global

* Status: Decidido 
* Deciders: Alejandro Checa Folguera, Ivan Martín Sanz, Jose Luis Lavado Sánchez
* Date: 2018-10-31 


## Context and Problem Statement

Tenemos varias interfaces que tienen que ser accedidas e intercomunicadas.Buscamos un patrón de arquitectura que nos permita enlazar todos los subsistemas en un sistema global.



## Considered Options

* Arquitectura dirigida por eventos
* Arquitectura de tres niveles
* Modelo-Vista-Controlador
* Arquitectura orientada a servicios(SOA)


## Decision Outcome

Chosen option: "Arquitectura orientada a servicios", because favorece la reutilización de código además del desarrollo en paralelo, fácil mantenimiento y mayor escalabilidad. 


## Pros and Cons of the Options

### Arquitectura dirigida por eventos

La Arquitectura dirigida por eventos es un patrón de arquitectura software que promueve la producción, detección, consumo de, y reacción a eventos. Un evento puede ser definido como un cambio significativo en un estado

* Good, because Simplicidad
* Good, because Modularidad una sola modalidad para eventos diversos
* Bad, because Posibilidad de desborde
* Bad, because Potencial imprevisión de escalabilidad
* Bad, because Mal soporte de recuperacion en caso de fallo parcial

### Arquitectura de tres niveles

La programación por niveles o capas es un modelo de desarrollo software en el que el objetivo primordial es la separación (desacoplamiento) de las partes que componen un sistema software. Tres niveles: capa de presentación, capa negocio, capa de datos.

* Good, because Reutilización de niveles
* Good, because Permite la estandarización
* Good, because Las dependencias se limitan a intracapas --> contencion de cambios a una o pocas capas
* Bad, because A veces no se logra la contención del cambio y se requiere una casacada de cambios entre varias capas
* Bad, because Perdidad de eficiencia y trabajo innecesario por parte de capas mas internas

### Modelo-Vista-Controlador

Modelo-vista-controlador (MVC) es un patrón de arquitectura de software, que separa los datos y la lógica de negocio de una aplicación de su representación y el módulo encargado de gestionar los eventos y las comunicaciones. Para ello MVC propone la construcción de tres componentes distintos que son el modelo, la vista y el controlador.

* Good, because Implementación modular 
* Good, because Las vistas simpre están actualizadas.
* Good, because La modificación de una parte no afecta a las demás --> facil extensibilad y mantenimiento
* Bad, because Mayor dedicación inicial en el desarrollo.
* Bad, because Requiere la existencia de una arquitectura inicial sobre la que construir clases e interfaces.
* Bad, becasue Es orientada a objetos por lo que su implentación sumamente costosa y díficil en lenguajes no POO. 

### Arquitectura orientada a servicios(SOA)

La Arquitectura Orientada a Servicios es un patrón de aruitectura de software apoyada en la orientación a servicios. La orientación a servicios es una forma de pensar en servicios, su construcción y sus resultados. Un servicio es una representación lógica de una actividad de negocio que tiene un resultado de negocio específico

* Good, because Reduce el nivel de acoplamiento --> Facil testeo y mantenimiento 
* Good, because Definición de seguridad mas clara
* Good, because Favorece reutilización, desarrollo en paralelo, mantenimiento y escalabilidad
* Good, because Permite mapeo directo entre procesos y los sistemas a la vez que la interoperabilidad 
* Bad, because Dependencia de la implementación de estadares
* Bad, because Dificil y costoso cumplir con los protocolos
* Bad, becasue A la hora de actualizar un sevicio debe evaluarse previamente el impacto y tener sumo cuidado con la implementación


## Links:
* [ADR-0001](0001-Patron-PW-App-Usuario.md)
* [ADR-0002](0002-Patron-Sistemas-Estadio.md)
* [ADR-0003](0003-Patron-Gestion-Entrada-Tornos.md)
* [ADR-0004](0004-Patron-VAR.md)
* [ADR-0005](0005-Patron-Ojo-Halcon.md)
* [ADR-0006](0006-Patron-Marauder.md)

