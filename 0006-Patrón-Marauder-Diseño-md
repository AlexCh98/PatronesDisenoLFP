# Elección de patrón para el subsistema Marauder

* Status: Decidida 
* Deciders: Daniel Carmona Pedrajas
* Date: 2018-10-31 


## Context and Problem Statement

Queremos elegir un patrón arquitectónico para el sistema Marauder cuyo objetivo principal analizar Internet en busca de cualquier web que esté realizando un streaming ilegal o que
comparta enlaces a emisiones ilegales de los partidos de fútbol comparando con la BBDD de fotogramas que tiene Marauder los fotorgramas de las páginas analizadas


## Considered Options

* Patrón por capas
* Patrón Pipe & Filter


## Decision Outcome

Chosen option: "Patrón Pipe & Filter", because puede detectar varias páginas ilegales a la vez.


## Pros and Cons of the Options

### Patrón por capas

El patrón por capas crea varios servicios en cada capa que pueden ser utilizados por el sistema superior

* Good, because el usuario decide cuántas IAs lanzar.
* Good, because permite la reutilización de niveles.
* Good, because seguridad por las jerarquías.
* Bad, because solo hay una base de datos que analizar y se ralentiza cuando hay muchas IAs comparando.
* Bad, because lento porque necesita analizar todos los fotogramas.
* Bad, because difícil implementar la IA.

### Patrón Pipe & Filter

El patrón Pipe & Filter permite generar flujos de datos en tiempo real.

* Good, because permite analizar varias páginas en paralelo.
* Good, because permite que los filtros actuen concurrentemente al generar datos de salida antes de leer todos los de entrada.
* Good, because rápido porque no hace falta analizar todos los fotogramas detectados por la IA.
* Good, because guarda todas las páginas analizadas en el Data Sink. 
* Bad, because necesita un filtro (BBDD) por pipe (IAs) por lo que necesita gran espacio de almacenamiento.
* Bad, because dificil implementar la IA.
