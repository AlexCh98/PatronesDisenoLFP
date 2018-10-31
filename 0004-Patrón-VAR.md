# Elección de patrón para el sistema VAR

* Status: Decidido 
* Deciders: Israel Peñalver Sánchez
* Date: 2018-10-31


## Context and Problem Statement

Vamos a tener una serie de cámaras situadas en el campo y se tendrá acceso a estas cámaras desde una sala en la que se mostraran todas las imágenes de las diferentes cámaras, se estará “emitiendo” a tiempo real en esta sala
Además se proporcionará al rarbitro a pie de campo una imagen sobre la que el pueda tomar una decisión een un determinado momento

## Considered Options

* Tuberías y filtros (Pipes and filtes)
* Modelo-Vista-Controlador

## Decision Outcome

Chosen option: "Modelo Vista-Controlador", because queremos realizar una separacion entre lo que ve el arbitro y los que ven los arbitros de sala,
los arbitros de sala acuaran como controlador y seleccionan la vista visible al arbitro de a campo.


## Pros and Cons of the Options

### Tuberías y filtros (Pipes and filtes)

Un filtro lee flujos de datos de sus entradas y genera flujos de datos a sus salidas.
El filtro transforma los datos incrementalmente (se comienza a generar salida antes
de acabar de leer toda la entrada).
La tubería transmite el flujo de datos.

* Good, because Eficiencia, permite procesamiento en paralelo
* Good, because Flexibilidad, capacidad de agregar nuevos filtros
* Good, because Reusabilidad, posible reutilizar filtros
* Good, because Mantenimiento, manipulacion de los filtros por separado
* Bad, because Latencia, un filtro tendra que esperar a otro filtro
* Bad, because Tuberias solo permiten datos unicos, filtros requieren un analisis extra
* Bad, because Manejo de errores


### Modelo-Vista-Controlador

Modelo-vista-controlador (MVC) es un patrón de arquitectura de software, que separa los datos y la lógica de negocio de una aplicación de su representación y el módulo encargado de gestionar los eventos y las comunicaciones. Para ello MVC propone la construcción de tres componentes distintos que son el modelo, la vista y el controlador.

* Good, because Implementación modular 
* Good, because Las vistas simpre están actualizadas.
* Good, because La modificación de una parte no afecta a las demás --> facil extensibilad y mantenimiento
* Bad, because Mayor dedicación inicial en el desarrollo.
* Bad, because Requiere la existencia de una arquitectura inicial sobre la que construir clases e interfaces.
* Bad, becasue Es orientada a objetos por lo que su implentación sumamente costosa y díficil en lenguajes no POO.


## Links:
* [ADR-0005](0005-Patron-Ojo-Halcon.md)
