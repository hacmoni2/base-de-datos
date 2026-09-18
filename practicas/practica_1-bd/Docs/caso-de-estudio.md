# Ejercicio 5. Caso de estudio y modelo entidad-relación

## 1. Identificación del problema

Se propone desarrollar un sistema de gestión para torneos de baloncesto que permita organizar y consultar la información relacionada con los equipos, jugadores, partidos, sedes, árbitros y estadísticas.

En la organización de un torneo, la información puede llegar a manejarse mediante diferentes archivos, hojas de cálculo o registros manuales. Esto puede dificultar la consulta de resultados, la actualización de los datos y el seguimiento de la participación de los jugadores y equipos durante el torneo.

El problema principal consiste en no contar con una base de datos centralizada que permita relacionar toda la información del torneo y mantener un historial organizado de los partidos y sus resultados.

El sistema propuesto permitirá registrar los equipos participantes, sus jugadores, los partidos programados, las sedes donde se realizan, los árbitros asignados y las estadísticas obtenidas durante cada encuentro.

---

## 2. Descripción de la problemática y entrevista con el cliente

### Descripción de la problemática

Se considera el caso de una organización encargada de realizar un torneo de baloncesto con varios equipos y diferentes jornadas de competición.

El responsable del torneo necesita conocer en todo momento qué equipos participan, qué jugadores pertenecen a cada equipo, qué partidos se han realizado, dónde se jugaron, quiénes fueron los árbitros y cuáles fueron los resultados.

Además, es necesario conservar las estadísticas de los jugadores en cada partido, ya que un mismo jugador puede participar en varios encuentros y obtener diferentes cantidades de puntos, rebotes, asistencias y faltas.

Para conocer las necesidades del sistema, se plantea una entrevista simulada con el responsable de la organización.

### Entrevista simulada

**Pregunta 1. ¿Qué información necesita registrar del torneo?**

**Respuesta esperada:**
Se necesita almacenar el nombre del torneo, la categoría, la fecha de inicio y la fecha de finalización. También debe ser posible identificar los equipos que participan en cada torneo.

---

**Pregunta 2. ¿Qué información se necesita de los equipos?**

**Respuesta esperada:**
Se requiere registrar el nombre del equipo, la ciudad a la que pertenece y el entrenador. También es necesario conocer en qué torneos se encuentra inscrito cada equipo.

---

**Pregunta 3. ¿Qué información se necesita de los jugadores?**

**Respuesta esperada:**
Se necesita registrar el nombre del jugador, su número, posición y fecha de nacimiento. Cada jugador debe estar relacionado con el equipo al que pertenece.

---

**Pregunta 4. ¿Qué información se necesita de los partidos?**

**Respuesta esperada:**
Se requiere registrar la fecha, hora y sede del partido, además de identificar los equipos que participaron y el resultado obtenido.

---

**Pregunta 5. ¿Cómo se identifica al equipo local y al visitante?**

**Respuesta esperada:**
En cada partido se debe indicar qué equipo participó como local y cuál como visitante. Esta información puede cambiar dependiendo del partido, por lo que no debe considerarse una característica permanente del equipo.

---

**Pregunta 6. ¿Es necesario registrar dónde se realiza cada partido?**

**Respuesta esperada:**
Sí. Se necesita conocer la sede, su nombre, dirección y capacidad. Una misma sede puede utilizarse para diferentes partidos.

---

**Pregunta 7. ¿Se necesita registrar a los árbitros?**

**Respuesta esperada:**
Sí. Se debe conocer qué árbitros fueron asignados a cada partido, ya que un partido puede contar con más de un árbitro y un árbitro puede participar en diferentes partidos.

---

**Pregunta 8. ¿Qué estadísticas de los jugadores se necesitan registrar?**

**Respuesta esperada:**
Se requiere registrar los puntos, rebotes, asistencias, faltas y minutos jugados por cada jugador en cada partido.

---

**Pregunta 9. ¿Con qué frecuencia se consultaría la información?**

**Respuesta esperada:**
La información se consultaría durante todo el torneo, principalmente antes y después de los partidos. Se necesitarían consultas frecuentes sobre calendarios, resultados, equipos y estadísticas.

---

**Pregunta 10. ¿Qué reportes serían necesarios?**

**Respuesta esperada:**

* Lista de equipos participantes.
* Lista de jugadores por equipo.
* Calendario de partidos.
* Resultados de los partidos.
* Partidos realizados en cada sede.
* Árbitros asignados a cada partido.
* Estadísticas de cada jugador.
* Puntos, rebotes y asistencias acumuladas por jugador.
* Historial de partidos de un equipo.
* Información de los equipos participantes en un torneo.

---

## 3. Requerimientos del sistema

### 3.1 Datos que debe almacenar

La base de datos deberá almacenar la siguiente información:

* **Torneos**

  * Identificador del torneo.
  * Nombre.
  * Categoría.
  * Fecha de inicio.
  * Fecha de finalización.

* **Equipos**

  * Identificador del equipo.
  * Nombre.
  * Ciudad.
  * Entrenador.

* **Jugadores**

  * Identificador del jugador.
  * Nombre.
  * Número de jugador.
  * Posición.
  * Fecha de nacimiento.
  * Equipo al que pertenece.

* **Inscripciones**

  * Torneo.
  * Equipo.
  * Fecha de inscripción.

* **Partidos**

  * Identificador del partido.
  * Torneo al que pertenece.
  * Fecha.
  * Hora.
  * Sede.

* **Participación de equipos en partidos**

  * Partido.
  * Equipo.
  * Rol dentro del partido: local o visitante.
  * Puntos obtenidos.

* **Sedes**

  * Identificador de la sede.
  * Nombre.
  * Dirección.
  * Capacidad.

* **Árbitros**

  * Identificador del árbitro.
  * Nombre.
  * Teléfono.

* **Asignaciones de árbitros**

  * Partido.
  * Árbitro.
  * Rol del árbitro.

* **Estadísticas de los jugadores**

  * Partido.
  * Jugador.
  * Puntos.
  * Rebotes.
  * Asistencias.
  * Faltas.
  * Minutos jugados.

### 3.2 Funciones que debe permitir el sistema

El sistema deberá permitir:

1. Registrar nuevos torneos.
2. Registrar equipos y sus datos.
3. Registrar jugadores y asociarlos con un equipo.
4. Inscribir equipos en un torneo.
5. Registrar los partidos de un torneo.
6. Asignar una sede a cada partido.
7. Registrar qué equipos participaron en cada partido.
8. Identificar al equipo local y al visitante.
9. Registrar el resultado de cada partido.
10. Registrar los árbitros asignados.
11. Registrar las estadísticas individuales de los jugadores.
12. Consultar el historial de partidos de un equipo.
13. Consultar las estadísticas de un jugador.
14. Consultar los partidos realizados en una determinada sede.
15. Consultar los equipos participantes de un torneo.

---

## 4. Modelo entidad-relación

El modelo entidad-relación se construirá utilizando una herramienta de modelado como ChartDB, dbdiagram.io, drawSQL u otra herramienta equivalente.

Las principales entidades consideradas son:

* **TORNEO**
* **EQUIPO**
* **JUGADOR**
* **INSCRIPCION**
* **PARTIDO**
* **PARTICIPACION_PARTIDO**
* **SEDE**
* **ARBITRO**
* **ASIGNACION_ARBITRO**
* **ESTADISTICA_PARTIDO**

### Relaciones principales

* Un **torneo** puede tener muchos equipos inscritos mediante `INSCRIPCION`.
* Un **equipo** puede participar en diferentes torneos.
* Un **equipo** puede tener varios jugadores.
* Un **torneo** puede tener muchos partidos.
* Una **sede** puede albergar muchos partidos.
* Un **partido** debe contar con la participación de dos equipos, identificando a uno como local y al otro como visitante.
* Un **partido** puede tener varios árbitros.
* Un **árbitro** puede participar en diferentes partidos.
* Un **jugador** puede participar en diferentes partidos.
* Un **partido** puede contar con estadísticas de varios jugadores.

La entidad `PARTICIPACION_PARTIDO` permite registrar el papel que desempeña cada equipo en un encuentro mediante el atributo `rol`, cuyos valores pueden ser **LOCAL** o **VISITANTE**.

La entidad `ESTADISTICA_PARTIDO` permite relacionar a los jugadores con los partidos y almacenar las estadísticas obtenidas específicamente en cada encuentro.

---

## 5. Justificación del modelo

Las entidades propuestas se definieron a partir de la información que necesita administrar la organización de un torneo de baloncesto.

La entidad **TORNEO** permite identificar y separar diferentes competencias. Esto es importante porque un mismo equipo puede participar en distintos torneos a lo largo del tiempo.

La entidad **EQUIPO** almacena la información básica de cada conjunto participante, mientras que **JUGADOR** permite registrar a los integrantes de cada equipo. La relación entre ambas entidades permite consultar fácilmente los jugadores pertenecientes a un equipo.

La entidad **INSCRIPCION** se utiliza para representar la relación entre torneos y equipos. Esta separación permite que un equipo pueda participar en diferentes torneos sin duplicar su información.

La entidad **PARTIDO** representa cada encuentro realizado dentro de un torneo. Se relaciona con **SEDE** para conocer dónde se realizó el partido y con **TORNEO** para identificar a qué competencia pertenece.

Para representar a los equipos que participan en cada encuentro se utiliza **PARTICIPACION_PARTIDO**. Esta entidad permite indicar si un equipo actuó como local o visitante y registrar los puntos obtenidos. De esta manera, el atributo `LOCAL` o `VISITANTE` depende del partido y no del equipo, ya que un mismo equipo puede ser local en un encuentro y visitante en otro.

La entidad **ARBITRO** almacena los datos de las personas encargadas de dirigir los encuentros, mientras que **ASIGNACION_ARBITRO** permite registrar qué árbitros participaron en cada partido.

Finalmente, **ESTADISTICA_PARTIDO** permite conservar las estadísticas individuales de los jugadores en cada encuentro. Esto evita almacenar las estadísticas directamente en la entidad `JUGADOR`, ya que los valores de puntos, rebotes, asistencias y faltas pueden cambiar en cada partido.

En conjunto, el modelo permite centralizar la información del torneo y establecer relaciones entre los diferentes elementos que intervienen en su organización. Esto facilita la consulta de resultados, participantes, estadísticas, sedes y árbitros, además de conservar un historial de los partidos realizados.

## Conclusión

El caso de estudio plantea una problemática que puede presentarse en la organización de un torneo de baloncesto cuando la información se encuentra distribuida entre diferentes registros y no existe una estructura centralizada.

El modelo entidad-relación propuesto permite organizar la información de manera estructurada y establecer relaciones entre torneos, equipos, jugadores, partidos, sedes, árbitros y estadísticas.

La implementación de una base de datos con este modelo permitiría reducir la duplicación de información y facilitar consultas frecuentes relacionadas con la organización y seguimiento del torneo.
