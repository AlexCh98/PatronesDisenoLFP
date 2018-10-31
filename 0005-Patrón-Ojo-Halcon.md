# Elecci�n de patr�n para el Ojo Halc�n

* Status: Pendiente 
* Deciders: Israel Pe�alver S�nchez
* Date: 2018-10-31


## Context and Problem Statement

Vamos a elegir un patr�n para resolver el problema de detectar cuando la pelota ha traspasado la linea de gol exactamente y asi poder tomar la decision de si se da por v�lisdo un gol o no.

## Considered Options

* Patr�n por eventos
* Modelo-Vista-Controlador
* Patr�n Cliente-Servidor

## Decision Outcome

Chosen option: "Patr�n por eventos", because optamos por la simplicidad de esta arquitectura y que el arbitro pueda tomar inminentemente la decision en base al evente sucedido.


## Pros and Cons of the Options

### Patr�n por Eventos

Las arquitecturas dirigidas por eventos (EDA Event-driven Architectures) se
basan en la detecci�n, consumo y reacci�n a eventos.
Un evento representa un cambio significativo en el estado de un sistema.
Los eventos se transmiten entre sistema poco acoplados (�loosely coupled�) mediante mensajes.


* Good, because Simplicidad
* Good, because Modularidad, una sola modalidad para eventos diversos
* Good, because Evoluci�n, se pueden reemplazar componentes suscriptoses
* Bad, because Posibilidad de desborde
* Bad, because Pobre comprensibilidad
* Bad, because No hay mucho soporte de recuperac�n en caso de fallo parcial


### Modelo-Vista-Controlador

Modelo-vista-controlador (MVC) es un patr�n de arquitectura de software, que separa los datos y la l�gica de negocio de una aplicaci�n de su representaci�n y el m�dulo encargado de gestionar los eventos y las comunicaciones. Para ello MVC propone la construcci�n de tres componentes distintos que son el modelo, la vista y el controlador.

* Good, because Implementaci�n modular 
* Good, because Las vistas simpre est�n actualizadas.
* Good, because La modificaci�n de una parte no afecta a las dem�s --> facil extensibilad y mantenimiento
* Bad, because Mayor dedicaci�n inicial en el desarrollo.
* Bad, because Requiere la existencia de una arquitectura inicial sobre la que construir clases e interfaces.
* Bad, becasue Es orientada a objetos por lo que su implentaci�n sumamente costosa y d�ficil en lenguajes no POO.

### Patr�n Cliente-Servidor

Se trata del modelo m�s utilizado en Internet. Los clientes acceden a datos y aplicaciones en los servidores. Hay C/S distribuidos (redes peer-to-peer). Peticiones as�ncronas y respuestas a eventos

* Good, because Centralizaci�n del control. 
* Good, because Facil mantenimiento.
* Good, because Escalabilidad, se pueden aumentar los clientes.
* Bad, because Robustez.
* Bad, because Congesti�n del tr�fico.

## Links:
* [ADR-0004](0004-Patron-VAR.md)
