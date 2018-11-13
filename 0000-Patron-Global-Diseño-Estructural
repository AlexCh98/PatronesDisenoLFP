# Elección de patrón de desiño estructural para el sistema global

* Status: Pendiente 
* Deciders: Alejandro Checa Folguera, Ivan Martín Sanz, Jose Luis Lavado Sánchez
* Date: 2018-11-13 


## Context and Problem Statement

Tenemos varias interfaces que tienen que ser intercomunicadas.Buscamos un patrón estructural que nos permita comunicar los servicios con cada subsistema.



## Considered Options

* Adapter
* Facade
* Proxy


## Decision Outcome

Chosen option: "Facade", because permite usar una o varias fachadas para relacionar la peticiones con los subsistemas generando un respuesta de manera desacoplada y optima.


## Pros and Cons of the Options

### Adapter 

Convierte la interfaz de una clase en otra interfaz que el cliente espera. El adaptador permite a las clases trabajar juntas, lo que de otra manera no podría hacerse debido a sus interfaces incompatibles.

* Good, because Permite compatibilidad entre interfaces.
* Good, because Permite encapsular laas respuestas.
* Bad, because Añade complejidad al diseño.
* Bad, because Pierde caractersticas importantes si no se implementa con objetos y clases
* Bad, because La version mas simple necesita programación orientada a objetos,.

### Facade

Se aplica el patrón fachada cuando se necesite proporcionar una interfaz simple para un subsistema complejo, o cuando se quiera estructurar varios subsistemas en capas, ya que las fachadas serían el punto de entrada a cada nivel.

* Good, because Reduce la dependencia de los subsistemas.
* Good, because Si cambia la respuesta podemos cambiar la fachada si cambiar la petición.
* Good, because El cliente no necesita saber como implenta las respuestas.
* Bad, because Si son subsistemas muy distintos puede necesitar varias fachadas lo que aumenta la complejidad.

### Proxy

Es un patrón estructural que tiene como propósito proporcionar un subrogado o intermediario de un objeto para controlar su acceso

* Good, because se introduce un nivel de indirección en el acceso al objeto.
* Good, because facilita otra optimización, relacionada con la creación de objetos por demanda.
* Bad, because un proxy remoto puede ocultar el hecho de que un objeto reside en otro espacio de direcciones.
* Bad, because un proxy virtual puede realizar optimizaciones, como crear objetos bajo demanda.

## Links:
* [ADR-0001](0001-Patron-PW-App-Usuario.md)
* [ADR-0002](0002-Patron-Sistemas-Estadio.md)
* [ADR-0003](0003-Patron-Gestion-Entrada-Tornos.md)
* [ADR-0004](0004-Patron-VAR.md)
* [ADR-0005](0005-Patron-Ojo-Halcon.md)
* [ADR-0006](0006-Patron-Marauder.md)
