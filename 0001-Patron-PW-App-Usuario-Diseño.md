# Elección de patrón creacional para la aplicación de usuario.

* Status: Pendiente 
* Deciders: Alejandro Checa Folguera, Ivan Martín Sanz, Jose Luis Lavado Sánchez
* Date: 2018-11-13 


## Context and Problem Statement

Buscamos un patron para el diseño de la pagina y las aplicaciones externas para usuarios



## Considered Options

* Composite
* Module
* Modelo-Vista-Controlador


## Decision Outcome

"Modelo-Vista-Controlador", because a pesar de que se tarda más en la planificación inicial, permite una mejor adaptación a distintos entornos y sistemas (implementación modular), además de que tiene una mayor escalabilidad.

## Pros and Cons of the Options

### Composite

Sirve para construir objetos complejos a partir de otros más simples y similares entre sí, gracias a la composición recursiva y a una estructura en forma de árbol.

* Good, because simplifica el código del cliente que interactua con estructuras más complejas.
* Good, because permite añadir facilmente nuevos tipos de componentes.
* Bad, because crea diseños de clases demasiado genéricos.

### Module

Es un patrón de diseño utilizado para implementar el concepto de módulos de software definidos por el paradigma de programación modular, en un lenguaje de programación que no lo soporta, o lo soporta parcialmente.Util dado que el MVC necesitwa programacion orientada a objetos.

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



## Links:
* [ADR-0001](0001-Patron-PW-App-Usuario.md)
* [ADR-0002](0002-Patron-Sistemas-Estadio.md)
* [ADR-0003](0003-Patron-Gestion-Entrada-Tornos.md)
* [ADR-0004](0004-Patron-VAR.md)
* [ADR-0005](0005-Patron-Ojo-Halcon.md)
* [ADR-0006](0006-Patron-Marauder.md)

