# Elección de patrón para prducir el evento del Ojo Halcón

* Status: Pendiente 
* Deciders: Israel Peñalver Sánchez
* Date: 2018-11-14


## Context and Problem Statement

Vamos a elegir un patrón para resolver el problema de como creamos el objeto que va a generar el evento, en este caso el objeto del que hablamos es el balón que genera eventos según este localizadoo en el campo.

## Considered Options

* Singleton
* Prototype

## Decision Outcome

Chosen option: "Singleton", because optamos por que solo pueda haber en cada instante una instancia del objeto que queremos que genere el evento.


## Pros and Cons of the Options

### SINGLETON

Singleton o instancia única es un patrón de diseño que permite restringir la creación de objetos pertenecientes a una clase o el valor de un tipo a un único objeto.
Su intención consiste en garantizar que una clase solo tenga una instancia y proporcionar un punto de acceso global a ella


* Good, because hay un acceso controlado a la única instancia
* Good, because reduce el espacio de nimbres que utilizamos.
* Good, because mayor flexibilidad en las operaciones de clase.
* Bad, because dificultad para realizar testing.
* Bad, because promociona el alto acoplamiento.
* Bad, because restriccion de ejecuciones paralelas.

## Prototype
Tiene como finalidad crear nuevos objetos clonando una instancia creada previamente.
 
* Good, because permite ocultar las clases producto (prototipos concretos) del cliente.
* Good, because permite que el cliente trabaje con clases dependientes de la aplicación sin cambios.
* Good, because hace posible añadir y eliminar productos en tiempo de ejecución, esto proporciona una configuración dinámica de la aplicación.
* Bad, because la jerarquía de prototipos debe ofrecer la posibilidad de clonar un elemento y esta operación puede no ser sencilla de implementar.
* Bad, because la clonación se produce frecuentemente, el coste puede ser importante.

## Links:
* [ADR-0004](0004-Patrón-VAR.md)
