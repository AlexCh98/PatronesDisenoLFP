# Elección de patrón para el sistema del estadio

* Status: Decidida 
* Deciders: Alejandro Checa Folguera, Ivan Martín Sanz, Jose Luis Lavado Sánchez
* Date: 2018-10-31 


## Context and Problem Statement

Tenemos varias interfaces que tienen que ser accedidas e intercomunicadas.Buscamos un patrón de arquitectura que nos permita enlazar todos los subsistemas como cámaras de videovigilancia, además de la venta de entradas y tornos, en un único sistema donde poder consultar todo a través de una aplicación.



## Considered Options

* Arquitectura dirigida por eventos
* Arquitectura de tres niveles
* Modelo-Vista-Controlador


## Decision Outcome

Chosen option: "Arquitectura de tres niveles", because hay una mayor reutilización de niveles cosa que viene bien para este subsistema, además las dependencias se limitan a intracapas 


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
* Bad, because Perdida de eficiencia y trabajo innecesario por parte de capas mas internas

### Modelo-Vista-Controlador

Modelo-vista-controlador (MVC) es un patrón de arquitectura de software, que separa los datos y la lógica de negocio de una aplicación de su representación y el módulo encargado de gestionar los eventos y las comunicaciones. Para ello MVC propone la construcción de tres componentes distintos que son el modelo, la vista y el controlador.

* Good, because Implementación modular 
* Good, because Las vistas simpre están actualizadas.
* Good, because La modificación de una parte no afecta a las demás --> facil extensibilad y mantenimiento
* Bad, because Mayor dedicación inicial en el desarrollo.
* Bad, because Requiere la existencia de una arquitectura inicial sobre la que construir clases e interfaces.
* Bad, becasue Es orientada a objetos por lo que su implentación sumamente costosa y díficil en lenguajes no POO. 



## Links:
* [ADR-0003](0003-Patron-Gestion-Entrada-Tornos.md)
