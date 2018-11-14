# Elección de patrón para el Ojo Halcón

* Status: Pendiente 
* Deciders: Israel Peñalver Sánchez
* Date: 2018-10-31


## Context and Problem Statement

Vamos a elegir un patrón para resolver el problema de detectar cuando la pelota ha traspasado la linea de gol exactamente y asi poder tomar la decision de si se da por válisdo un gol o no.

## Considered Options

* Facade
* Flyweight

## Decision Outcome

Chosen option: "Singleton", because optamos por la simplicidad de esta arquitectura y que el arbitro pueda tomar inminentemente la decision en base al evente sucedido.


## Pros and Cons of the Options

### Patrón por Eventos

Las arquitecturas dirigidas por eventos (EDA Event-driven Architectures) se
basan en la detección, consumo y reacción a eventos.
Un evento representa un cambio significativo en el estado de un sistema.
Los eventos se transmiten entre sistema poco acoplados (“loosely coupled”) mediante mensajes.


* Good, because Simplicidad
* Good, because Modularidad, una sola modalidad para eventos diversos
* Good, because Evolución, se pueden reemplazar componentes suscriptoses
* Bad, because Posibilidad de desborde
* Bad, because Pobre comprensibilidad
* Bad, because No hay mucho soporte de recuperacón en caso de fallo parcial


### Modelo-Vista-Controlador

Modelo-vista-controlador (MVC) es un patrón de arquitectura de software, que separa los datos y la lógica de negocio de una aplicación de su representación y el módulo encargado de gestionar los eventos y las comunicaciones. Para ello MVC propone la construcción de tres componentes distintos que son el modelo, la vista y el controlador.

* Good, because Implementación modular 
* Good, because Las vistas simpre están actualizadas.
* Good, because La modificación de una parte no afecta a las demás --> facil extensibilad y mantenimiento
* Bad, because Mayor dedicación inicial en el desarrollo.
* Bad, because Requiere la existencia de una arquitectura inicial sobre la que construir clases e interfaces.
* Bad, becasue Es orientada a objetos por lo que su implentación sumamente costosa y díficil en lenguajes no POO.

### Patrón Cliente-Servidor

Se trata del modelo más utilizado en Internet. Los clientes acceden a datos y aplicaciones en los servidores. Hay C/S distribuidos (redes peer-to-peer). Peticiones asíncronas y respuestas a eventos

* Good, because Centralización del control. 
* Good, because Facil mantenimiento.
* Good, because Escalabilidad, se pueden aumentar los clientes.
* Bad, because Robustez.
* Bad, because Congestión del tráfico.

## Links:
* [ADR-0004](0004-Patrón-VAR.md)
