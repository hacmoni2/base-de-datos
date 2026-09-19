# Ejercicio 3. Investigación: ¿Qué es una base de datos?

## Introducción

El manejo de datos forma parte de prácticamente cualquier actividad relacionada con los sistemas informáticos. Una aplicación bancaria necesita conservar información sobre cuentas, movimientos y clientes; una plataforma educativa requiere almacenar usuarios, cursos, evaluaciones y actividades; una tienda en línea debe mantener productos, pedidos, pagos e inventarios; incluso una aplicación aparentemente sencilla necesita alguna forma de conservar información para que los datos no desaparezcan cuando termina una ejecución. La diferencia entre almacenar algunos archivos y administrar una base de datos aparece cuando la cantidad, variedad, importancia y frecuencia de uso de los datos comienzan a crecer.

Una base de datos no debe entenderse únicamente como un conjunto de archivos guardados en una computadora. El concepto implica una organización estructurada de datos y un conjunto de mecanismos destinados a permitir su almacenamiento, consulta, modificación, protección y administración. A esto se suma el sistema gestor de bases de datos, conocido como DBMS por sus siglas en inglés, que funciona como la capa de software encargada de administrar el acceso a la información y de aplicar reglas relacionadas con seguridad, integridad, concurrencia, recuperación y eficiencia (Elmasri & Navathe, 2016; Silberschatz et al., 2019).

La evolución de las bases de datos está relacionada con un problema muy concreto de la informática: los sistemas basados exclusivamente en archivos comenzaron a resultar insuficientes cuando diferentes aplicaciones necesitaban trabajar con los mismos datos. En ese escenario aparecían duplicidades, inconsistencias, dificultades para compartir información y una fuerte dependencia entre los programas y la estructura física de los archivos. La aparición de los sistemas gestores de bases de datos permitió separar progresivamente los datos de las aplicaciones que los utilizaban y establecer mecanismos especializados para administrarlos.

Uno de los momentos fundamentales en esta evolución fue la propuesta del modelo relacional realizada por Edgar F. Codd en 1970. Su trabajo planteó una forma de representar los datos mediante relaciones y buscó reducir la dependencia que tenían los usuarios y los programas respecto de la forma interna en que se almacenaba la información (Codd, 1970). Posteriormente, los conceptos de arquitectura de bases de datos, independencia de datos, lenguajes de consulta y diferentes modelos de almacenamiento contribuyeron a formar el campo de los sistemas de bases de datos modernos.

En la actualidad no existe un único tipo de base de datos adecuado para todos los problemas. El modelo relacional continúa siendo fundamental para aplicaciones que requieren estructuras bien definidas, restricciones de integridad y operaciones transaccionales. Sin embargo, también existen bases de datos orientadas a documentos, sistemas clave-valor, bases de datos de familias de columnas, bases de datos de grafos y sistemas especializados para información temporal, espacial o vectorial. Esta diversidad responde a que los datos también son diversos y a que las necesidades de las aplicaciones modernas no siempre coinciden con las que dieron origen a los sistemas relacionales.

La inteligencia artificial ha aumentado todavía más la importancia de las bases de datos. Los modelos de aprendizaje automático necesitan conjuntos de datos para entrenarse, validarse y evaluarse. Los sistemas de recuperación de información requieren almacenar documentos y metadatos. Los sistemas basados en representaciones vectoriales necesitan mecanismos de búsqueda por similitud. En aplicaciones modernas, la base de datos ya no funciona solamente como un lugar donde se guardan registros administrativos, sino también como parte de la infraestructura que permite construir sistemas inteligentes.

El estudio de las bases de datos, por esta razón, comprende mucho más que aprender instrucciones SQL. Incluye conceptos relacionados con modelos de datos, arquitectura, almacenamiento, procesamiento de consultas, concurrencia, seguridad, recuperación, distribución y selección de tecnologías. Comprender estos fundamentos permite identificar por qué existen diferentes sistemas gestores y por qué una misma información puede requerir estrategias de almacenamiento distintas dependiendo del problema que se busca resolver.

---

# 1. Dato, información y base de datos

## 1.1 El concepto de dato

El concepto de dato constituye el punto de partida para comprender una base de datos. Un dato puede entenderse como una representación de un hecho, característica, medición, objeto o evento que puede ser registrada y posteriormente procesada. Por sí mismo, un dato puede tener un significado limitado si no existe contexto suficiente para interpretarlo.

Por ejemplo, el valor `20` puede representar una edad, una cantidad de productos, una calificación, una temperatura o el número de una habitación. El valor aislado no permite determinar cuál de esas interpretaciones es correcta. Cuando se incorpora información adicional, como un nombre de atributo o una relación con otros datos, el significado comienza a definirse.

En una tabla relacional podría existir un registro como:

```text
Nombre: Ana
Edad: 20
Carrera: Inteligencia Artificial
Semestre: 3
```

En este caso, los valores `20` y `3` dejan de ser números aislados. El contexto proporcionado por los atributos `Edad` y `Semestre` permite interpretar qué representa cada uno.

El dato, por lo tanto, no debe confundirse con la información. El primero constituye una representación que puede ser almacenada y procesada; la segunda aparece cuando los datos son interpretados dentro de un contexto determinado y permiten comprender algún aspecto de una situación.

Los sistemas informáticos trabajan constantemente con datos. Sin embargo, el almacenamiento de datos no constituye por sí mismo una base de datos. Un archivo de texto que contiene cien nombres también almacena datos, pero no necesariamente proporciona mecanismos suficientes para administrar relaciones, restricciones, consultas complejas, concurrencia o recuperación ante fallos.

Esta distinción resulta importante porque permite comprender por qué los sistemas gestores de bases de datos son necesarios. El problema no consiste únicamente en conservar información, sino en administrarla de manera organizada y confiable.

## 1.2 Dato e información

La información puede considerarse como un resultado del procesamiento y contextualización de los datos. La diferencia puede observarse con un ejemplo sencillo.

Supóngase que un sistema registra los siguientes valores:

```text
18
20
19
21
22
```

Estos valores constituyen datos. Si el sistema identifica que representan las edades de cinco estudiantes y calcula un promedio de 20 años, el resultado adquiere un significado concreto. El promedio, acompañado del contexto correspondiente, constituye información útil para determinada actividad.

La relación entre datos e información no es completamente rígida. Un mismo elemento puede actuar como dato en un contexto y como información en otro. La distinción depende del uso que se haga de los elementos registrados.

En los sistemas de información, la transformación de datos en información suele involucrar operaciones como clasificación, filtrado, agregación, comparación, ordenamiento y análisis. Las bases de datos proporcionan una infraestructura para conservar los datos necesarios para esas operaciones.

Por ejemplo, una universidad puede almacenar miles de registros de estudiantes. Cada registro individual contiene datos como matrícula, nombre, carrera, semestre y calificaciones. Cuando esos datos se utilizan para obtener el promedio de una generación, identificar materias con mayor índice de reprobación o generar una lista de estudiantes inscritos en determinado curso, los registros se transforman en información útil para distintas actividades.

La utilidad de la información depende, además, de su calidad. Datos incompletos, duplicados, contradictorios o desactualizados pueden producir información incorrecta. Por esa razón, la administración de bases de datos también incluye mecanismos para mantener la integridad y consistencia de los datos.

## 1.3 Definiciones de base de datos según distintos autores

El concepto de base de datos ha sido abordado desde diferentes perspectivas. Dos referencias clásicas para el estudio del área son Elmasri y Navathe, y Silberschatz, Korth y Sudarshan.

Elmasri y Navathe (2016) presentan una base de datos como una colección de datos relacionados, en la que los datos representan aspectos del mundo real y poseen un significado definido dentro del contexto en el que son almacenados. Esta definición destaca dos características importantes: la relación entre los datos y la existencia de un contexto que permite interpretarlos.

Desde esta perspectiva, una base de datos no es simplemente una colección arbitraria de valores. Los datos deben representar algún dominio determinado. Una base de datos universitaria, por ejemplo, contiene información relacionada con estudiantes, profesores, materias, grupos y evaluaciones. Una base de datos médica contiene información correspondiente a pacientes, consultas, diagnósticos, tratamientos y otros elementos propios del dominio de salud.

Silberschatz et al. (2019) presentan el concepto de sistema de bases de datos desde una perspectiva más amplia, en la que una base de datos constituye una colección de información relacionada y el sistema gestor proporciona los mecanismos para almacenar y recuperar esa información de manera eficiente y segura.

Ambas aproximaciones coinciden en considerar que existe una colección organizada de datos relacionados, pero enfatizan aspectos diferentes. Elmasri y Navathe ponen especial atención en la representación de una parte del mundo real y en las relaciones entre los datos. Silberschatz et al. incorporan con mayor énfasis la función del sistema que permite administrar la información.

Otra referencia fundamental es Date (2004), quien analiza las bases de datos desde el punto de vista de un sistema que permite administrar datos persistentes y compartirlos entre diferentes usuarios y aplicaciones. En esta perspectiva, la base de datos no se encuentra aislada del software encargado de administrarla. Existe una relación entre los datos almacenados, el sistema gestor y los programas que utilizan la información.

La comparación de estas definiciones permite establecer una idea más completa. Una base de datos puede entenderse como una colección estructurada y relacionada de datos que representa información de un dominio determinado y que es administrada mediante mecanismos especializados para permitir su almacenamiento, consulta, actualización, protección y recuperación.

## 1.4 Comparación de las definiciones

Las definiciones mencionadas comparten varios elementos. En primer lugar, reconocen que los datos no se almacenan de manera completamente arbitraria. Existe una estructura que permite establecer relaciones y significado. En segundo lugar, existe la necesidad de mecanismos que permitan administrar los datos. En tercer lugar, el concepto de base de datos está relacionado con la posibilidad de que diferentes usuarios o aplicaciones utilicen la misma información.

La diferencia principal se encuentra en el énfasis utilizado. Elmasri y Navathe (2016) presentan una perspectiva más orientada al significado de los datos y su representación de un dominio del mundo real. Silberschatz et al. (2019) explican el concepto dentro de una visión general de los sistemas de bases de datos, incluyendo almacenamiento, consultas, transacciones y administración. Date (2004), por su parte, profundiza en la separación entre los datos y los programas que los utilizan, así como en los principios que permiten construir sistemas de bases de datos.

Estas diferencias no representan contradicciones. Más bien, muestran que una base de datos puede analizarse desde distintos niveles. Desde un nivel conceptual, interesa saber qué datos existen y qué relaciones tienen. Desde un nivel lógico, interesa saber cómo se estructura esa información. Desde un nivel físico, interesa conocer cómo se almacena y cómo se accede a ella. Finalmente, desde el nivel del sistema gestor, interesa controlar las operaciones que diferentes usuarios y aplicaciones realizan sobre los datos.

Esta separación resulta fundamental para el resto del estudio de las bases de datos. Un sistema puede cambiar la forma física en que almacena los datos sin que necesariamente cambie la estructura lógica que utilizan las aplicaciones. Precisamente este principio se relaciona con la independencia de datos, uno de los conceptos centrales de la arquitectura de bases de datos.

---

# 2. Fundamentos de las bases de datos

## 2.1 Antes de los sistemas gestores de bases de datos

Durante las primeras etapas de la computación empresarial, una forma común de almacenar información consistía en utilizar archivos administrados directamente por los programas. Cada aplicación podía tener sus propios archivos y conocer exactamente cómo estaban organizados.

Esta estrategia funcionaba para sistemas relativamente pequeños. Una aplicación podía abrir un archivo, leer registros, modificarlos y guardar los cambios. Sin embargo, conforme aumentaba la cantidad de información y aparecían más aplicaciones, comenzaron a surgir problemas.

Un ejemplo permite ilustrar la situación. Supóngase una institución que tiene un archivo de estudiantes para el área administrativa y otro archivo de estudiantes para el área académica. Ambos podrían contener información como nombre, matrícula, carrera y semestre. Si un estudiante cambia de carrera, el cambio tendría que realizarse en ambos archivos. Si uno de ellos no se actualiza, aparecen dos versiones diferentes de la misma realidad.

El problema no se limita a la duplicidad. También puede existir dificultad para consultar información que originalmente no fue prevista por el programa. Si una aplicación solamente fue diseñada para producir un reporte mensual, realizar una consulta diferente podría requerir modificar el código fuente.

Ramakrishnan y Gehrke (2003) explican que los sistemas de archivos presentan dificultades relacionadas con redundancia, inconsistencia, aislamiento de datos, problemas de acceso, integridad, atomicidad, concurrencia y seguridad. Estas dificultades constituyeron parte importante de la motivación para desarrollar sistemas gestores de bases de datos.

## 2.2 Redundancia de datos

La redundancia ocurre cuando una misma información se almacena más veces de las necesarias.

La redundancia no siempre es negativa. En determinadas arquitecturas puede utilizarse intencionalmente para mejorar el rendimiento o disponibilidad. Sin embargo, cuando aparece como consecuencia de una organización deficiente, aumenta el espacio utilizado y genera dificultades para mantener la consistencia.

Supóngase que una empresa almacena el nombre y dirección de un cliente en diez archivos diferentes. Si el cliente cambia de domicilio, los diez registros deberían actualizarse. Si solamente se actualizan nueve, el sistema queda con información contradictoria.

Los sistemas gestores de bases de datos permiten reducir este problema mediante modelos de datos y mecanismos de diseño. En el modelo relacional, por ejemplo, la normalización permite organizar los datos para disminuir determinadas formas de redundancia y dependencia innecesaria.

## 2.3 Inconsistencia

La inconsistencia aparece cuando existen diferentes versiones de un mismo dato y no contienen el mismo valor.

Si una base de datos mantiene el saldo de una cuenta en un solo lugar, una modificación afecta directamente a ese registro. En un sistema basado en múltiples archivos, el mismo saldo podría aparecer en varios lugares.

La inconsistencia es especialmente grave cuando los datos se utilizan para tomar decisiones. Un sistema financiero no puede permitir que una aplicación muestre un saldo diferente al que utiliza otra aplicación para autorizar una operación.

La consistencia de los datos también está relacionada con las reglas de integridad. Un DBMS puede establecer restricciones que impidan introducir valores inválidos o relaciones que no correspondan con el modelo definido.

## 2.4 Dificultad para compartir datos

En un sistema basado en archivos, cada aplicación puede mantener sus propios datos. Esto dificulta que diferentes programas trabajen sobre una fuente común.

Un sistema de bases de datos busca precisamente proporcionar un repositorio compartido. Una aplicación de ventas, una aplicación de inventario y una aplicación administrativa pueden utilizar información relacionada con los mismos productos y clientes.

El concepto de compartir datos también implica controlar el acceso. No todos los usuarios deben tener necesariamente los mismos permisos. Un empleado puede consultar información mientras otro tiene autorización para modificarla. Un administrador puede tener permisos adicionales.

## 2.5 Aislamiento de datos

Los archivos independientes pueden encontrarse en formatos diferentes. Una aplicación puede almacenar información en archivos de texto, otra en archivos binarios y otra en estructuras diseñadas específicamente para su funcionamiento.

Cuando surge la necesidad de combinar la información, la integración se vuelve más compleja.

Un DBMS proporciona una representación estructurada de los datos que facilita su consulta y relación. En el caso de los sistemas relacionales, SQL proporciona una interfaz estandarizada para trabajar con tablas y relaciones. PostgreSQL, por ejemplo, incluye soporte amplio para SQL y diferentes mecanismos de consulta y manipulación de datos (PostgreSQL Global Development Group, 2026).

## 2.6 Integridad

La integridad se refiere a que los datos cumplan determinadas reglas de validez.

Una tabla de estudiantes podría establecer que la matrícula debe ser única. Una tabla de calificaciones podría restringir los valores a un rango específico. Una relación entre estudiantes y grupos podría requerir que el grupo exista antes de asignarlo a un estudiante.

Estas restricciones ayudan a evitar errores producidos por aplicaciones o usuarios. El DBMS puede actuar como una capa adicional de protección.

En una base de datos relacional, las restricciones pueden incluir claves primarias, claves foráneas, restricciones `UNIQUE`, `NOT NULL`, `CHECK` y otras reglas. Su función no consiste únicamente en organizar la información, sino también en proteger las condiciones que deben cumplirse para que los datos sean válidos.

## 2.7 Atomicidad

Las operaciones sobre bases de datos pueden involucrar varios cambios que deben considerarse como una sola unidad lógica.

Una transferencia bancaria constituye un ejemplo clásico. Si se transfieren 500 pesos de una cuenta a otra, deben ocurrir dos acciones: disminuir 500 pesos de una cuenta y aumentar 500 pesos en la otra.

Si el primer cambio ocurre y el segundo falla, el sistema queda en un estado incorrecto. La atomicidad permite tratar ambas operaciones como una transacción: o se completan todas, o ninguna queda aplicada.

Este concepto forma parte de las propiedades ACID: atomicidad, consistencia, aislamiento y durabilidad.

## 2.8 Concurrencia

En un sistema real, diferentes usuarios pueden acceder simultáneamente a los mismos datos.

Por ejemplo, dos personas podrían intentar comprar al mismo tiempo el último producto disponible. Si ambas operaciones leen que existe una unidad antes de realizar la actualización, podrían terminar registrándose dos ventas para un solo producto.

El DBMS utiliza mecanismos de control de concurrencia para evitar determinados conflictos. Dependiendo del sistema, pueden utilizarse bloqueos, control multiversión y otros mecanismos.

La concurrencia es una de las razones por las que administrar datos compartidos resulta considerablemente más complejo que simplemente guardar información en archivos.

## 2.9 Seguridad

Los datos pueden tener diferentes niveles de sensibilidad. Una base de datos académica puede contener información que solamente determinados empleados deben consultar. Un sistema empresarial puede almacenar información financiera. Una aplicación médica puede contener datos especialmente sensibles.

Los sistemas gestores proporcionan mecanismos de autenticación y autorización. Estos mecanismos permiten determinar quién puede acceder al sistema y qué operaciones puede realizar.

La seguridad no consiste únicamente en colocar una contraseña. Incluye privilegios, roles, auditoría, cifrado, control de conexiones y medidas destinadas a reducir el impacto de accesos no autorizados.

## 2.10 ¿Por qué surgieron los DBMS?

La aparición de los sistemas gestores de bases de datos respondió a la necesidad de resolver problemas que se volvían difíciles de administrar mediante archivos independientes.

Un DBMS permite centralizar la administración de los datos y proporcionar una interfaz entre las aplicaciones y el almacenamiento. Esto hace posible separar, hasta cierto punto, el programa que utiliza los datos de la manera física en que los datos se almacenan.

Codd (1970) señaló precisamente la importancia de evitar que los usuarios y programas tuvieran que conocer la representación interna de los datos. Esta idea fue fundamental para la evolución de los sistemas de bases de datos.

La finalidad del DBMS, por tanto, no consiste solamente en almacenar información. También administra consultas, actualizaciones, transacciones, concurrencia, recuperación, seguridad y metadatos.

---

# 3. Arquitectura ANSI-SPARC

## 3.1 Antecedentes

Uno de los problemas fundamentales de los sistemas de bases de datos consiste en mantener una separación adecuada entre la forma en que los datos son almacenados y la forma en que diferentes usuarios necesitan verlos.

Para abordar esta problemática se desarrolló la arquitectura de tres esquemas conocida como ANSI-SPARC. Esta arquitectura fue asociada con el trabajo del comité ANSI/SPARC y se convirtió en un modelo de referencia para explicar la separación entre diferentes niveles de descripción de una base de datos (Tsichritzis & Klug, 1978).

El objetivo principal consiste en separar las aplicaciones de los detalles físicos del almacenamiento y, al mismo tiempo, permitir diferentes vistas de una misma base de datos.

La arquitectura se divide en tres niveles principales:

1. Nivel externo.
2. Nivel conceptual.
3. Nivel interno.

## 3.2 Nivel externo

El nivel externo representa las vistas que diferentes usuarios o aplicaciones tienen de la base de datos.

Una misma base de datos puede contener cientos de atributos y miles o millones de registros, pero cada usuario puede necesitar solamente una parte de esa información.

En una universidad, por ejemplo, el personal administrativo puede necesitar consultar información relacionada con datos personales y trámites. Un profesor puede necesitar consultar estudiantes inscritos y calificaciones. Un área financiera puede necesitar información de pagos. No existe necesidad de presentar toda la base de datos a todos los usuarios.

Las vistas externas permiten establecer qué información resulta relevante para cada grupo.

Este nivel también contribuye a la seguridad porque puede limitar la información que aparece en una determinada vista.

## 3.3 Nivel conceptual

El nivel conceptual representa la estructura lógica global de la base de datos.

En este nivel se describen entidades, atributos, relaciones y restricciones, sin entrar en detalles específicos sobre dónde se encuentran físicamente los datos.

En una base de datos universitaria podrían existir entidades como:

* Estudiante.
* Profesor.
* Materia.
* Grupo.
* Inscripción.
* Calificación.

También se establecen relaciones entre ellas. Un estudiante puede estar inscrito en varios grupos; un grupo pertenece a una materia; un profesor puede impartir varios grupos.

El esquema conceptual funciona como una descripción global que conecta las diferentes necesidades de los usuarios.

## 3.4 Nivel interno

El nivel interno describe la forma en que los datos son almacenados físicamente.

Aquí aparecen aspectos como archivos, páginas, índices, estructuras de almacenamiento y métodos de acceso. Los detalles dependen del sistema gestor y de la tecnología utilizada.

Una aplicación normalmente no necesita saber si una tabla está distribuida en determinadas páginas de disco o qué estructura interna utiliza un índice. El DBMS administra estos detalles.

La separación entre el nivel conceptual y el nivel interno permite realizar cambios de almacenamiento sin tener que modificar necesariamente las aplicaciones.

## 3.5 Mapeos entre niveles

Los tres niveles no están aislados. Existen correspondencias entre ellos.

Entre el nivel externo y el conceptual se establece una correspondencia que permite relacionar las vistas de los usuarios con la estructura lógica general.

Entre el nivel conceptual y el interno existe otra correspondencia que relaciona la estructura lógica con la forma física de almacenamiento.

Esta organización puede representarse de manera simplificada:

```text
Usuarios y aplicaciones
        |
        v
Nivel externo
(vistas de usuarios)
        |
        v
Nivel conceptual
(esquema lógico global)
        |
        v
Nivel interno
(almacenamiento físico)
        |
        v
Datos almacenados
```

El valor principal de esta arquitectura se encuentra en la separación de responsabilidades. La aplicación trabaja con una representación lógica; el sistema gestor se ocupa de traducir las operaciones hacia las estructuras internas.

## 3.6 Importancia de ANSI-SPARC

La arquitectura de tres esquemas proporciona una forma clara de entender por qué una aplicación no debería depender directamente de la estructura física de los archivos.

Si una organización cambia un índice, mueve una tabla a otro dispositivo de almacenamiento o modifica la forma en que administra determinados archivos, no necesariamente debería cambiar el código de todas las aplicaciones.

Esta separación contribuyó a establecer el concepto de independencia de datos, que representa uno de los objetivos fundamentales de la arquitectura de bases de datos.

---

# 4. Independencia de datos, lenguajes y módulos del DBMS

## 4.1 Independencia de datos

La independencia de datos consiste en la capacidad de modificar un nivel de la arquitectura sin obligar a realizar cambios equivalentes en los niveles superiores.

Existen dos formas principales:

* Independencia física.
* Independencia lógica.

## 4.2 Independencia física

La independencia física permite modificar aspectos del almacenamiento interno sin modificar el esquema conceptual ni las aplicaciones que trabajan con él.

Por ejemplo, un administrador puede crear un índice para acelerar una consulta. La consulta utilizada por una aplicación puede permanecer exactamente igual.

También pueden cambiarse métodos de almacenamiento, organización de archivos o determinadas estructuras internas.

El usuario de la aplicación no necesita conocer estos detalles.

Codd (1970) destacó la importancia de proteger a los usuarios de tener que conocer la representación interna de los datos. Esta idea se encuentra estrechamente relacionada con la independencia física.

## 4.3 Independencia lógica

La independencia lógica se relaciona con la capacidad de modificar el esquema conceptual sin afectar las vistas externas o aplicaciones más de lo necesario.

Esta forma de independencia es más difícil de conseguir porque los cambios lógicos pueden afectar directamente a las estructuras que utilizan las aplicaciones.

Por ejemplo, una base de datos puede agregar un nuevo atributo a una tabla sin afectar una aplicación que solamente utiliza los atributos anteriores. Sin embargo, eliminar o modificar el significado de una columna utilizada directamente por una aplicación sí puede requerir cambios.

La arquitectura ANSI-SPARC busca facilitar esta separación mediante los diferentes niveles y mapeos.

## 4.4 Lenguajes de bases de datos

Los sistemas gestores utilizan diferentes lenguajes y mecanismos para definir, manipular, consultar y controlar los datos.

Tradicionalmente se distinguen categorías como:

* DDL: Data Definition Language.
* DML: Data Manipulation Language.
* DQL: Data Query Language, aunque en algunas clasificaciones las consultas se incluyen dentro del DML.
* DCL: Data Control Language.
* TCL: Transaction Control Language.

Estas categorías no siempre se presentan de manera idéntica en todos los libros o sistemas, pero ayudan a organizar las funciones del lenguaje.

## 4.5 DDL

El lenguaje de definición de datos permite definir estructuras de la base de datos.

Ejemplos:

```sql
CREATE TABLE estudiantes (
    matricula INTEGER PRIMARY KEY,
    nombre VARCHAR(100),
    semestre INTEGER
);
```

La instrucción `CREATE TABLE` define una estructura.

También existen operaciones como:

```sql
ALTER TABLE
DROP TABLE
CREATE INDEX
```

Estas operaciones modifican o crean elementos relacionados con la estructura de la base de datos.

## 4.6 DML

El lenguaje de manipulación de datos permite insertar, modificar y eliminar información.

Ejemplos:

```sql
INSERT INTO estudiantes
VALUES (1001, 'Ana', 3);
```

```sql
UPDATE estudiantes
SET semestre = 4
WHERE matricula = 1001;
```

```sql
DELETE FROM estudiantes
WHERE matricula = 1001;
```

Estas instrucciones modifican los datos almacenados.

## 4.7 Consultas

Las consultas permiten recuperar información de acuerdo con determinados criterios.

Un ejemplo sencillo:

```sql
SELECT nombre, semestre
FROM estudiantes
WHERE semestre >= 3;
```

SQL no se limita a recuperar registros individuales. También permite combinar tablas, realizar agregaciones, ordenar resultados, agrupar información y ejecutar consultas complejas.

PostgreSQL, por ejemplo, proporciona una implementación amplia del lenguaje SQL junto con funciones, tipos de datos, operadores y mecanismos de optimización (PostgreSQL Global Development Group, 2026).

## 4.8 DCL

El lenguaje de control de datos permite gestionar permisos y privilegios.

Entre las operaciones habituales se encuentran:

```sql
GRANT
REVOKE
```

Estas instrucciones permiten definir qué operaciones puede realizar un usuario o rol sobre determinados objetos.

El control de privilegios resulta fundamental cuando la base de datos es utilizada por diferentes personas o aplicaciones.

## 4.9 TCL

El control de transacciones permite gestionar operaciones que deben tratarse como unidades lógicas.

Entre las instrucciones más conocidas se encuentran:

```sql
BEGIN;
COMMIT;
ROLLBACK;
```

`COMMIT` confirma una transacción y `ROLLBACK` permite revertir los cambios que todavía no han sido confirmados.

El uso de transacciones es fundamental para conservar la consistencia cuando una operación involucra varios cambios relacionados.

## 4.10 Módulos principales de un DBMS

Un sistema gestor de bases de datos está compuesto por diferentes componentes. La organización exacta depende del producto, pero existen funciones comunes.

Entre los componentes más importantes se encuentran:

* Procesador de consultas.
* Optimizador de consultas.
* Administrador de almacenamiento.
* Administrador de transacciones.
* Administrador de concurrencia.
* Sistema de recuperación.
* Administrador de autorización y seguridad.
* Catálogo o diccionario de datos.
* Gestor de memoria intermedia.

## 4.11 Procesador de consultas

El procesador de consultas interpreta las instrucciones realizadas por los usuarios o aplicaciones.

Una consulta SQL debe transformarse en operaciones que el sistema pueda ejecutar.

Por ejemplo:

```sql
SELECT *
FROM estudiantes
WHERE semestre = 3;
```

El DBMS necesita interpretar la instrucción, verificar su sintaxis, revisar los objetos involucrados y construir una estrategia de ejecución.

## 4.12 Optimizador

Una misma consulta puede ejecutarse mediante diferentes estrategias.

Supóngase una tabla con millones de registros. Una opción consiste en revisar todos los registros. Otra puede consistir en utilizar un índice.

El optimizador analiza diferentes posibilidades y selecciona una estrategia de ejecución de acuerdo con la información disponible.

Esta función es importante porque el rendimiento no depende únicamente de escribir consultas correctas. También depende de la forma en que el sistema ejecuta esas consultas.

## 4.13 Administrador de almacenamiento

El administrador de almacenamiento se encarga de las operaciones relacionadas con la conservación física de los datos.

Entre sus responsabilidades se encuentran la interacción con archivos, páginas, índices y estructuras internas.

El objetivo consiste en proporcionar una capa entre las operaciones lógicas de la base de datos y los dispositivos de almacenamiento.

## 4.14 Administrador de transacciones y concurrencia

El administrador de transacciones controla las operaciones que deben ejecutarse de manera consistente.

El control de concurrencia evita que operaciones simultáneas produzcan resultados incorrectos.

Este componente adquiere especial importancia en sistemas con muchos usuarios, donde múltiples operaciones pueden ocurrir al mismo tiempo.

## 4.15 Recuperación

Los sistemas de bases de datos deben considerar la posibilidad de fallos.

Puede ocurrir una interrupción eléctrica, una falla de hardware, un error de software o una terminación inesperada del proceso.

El sistema de recuperación utiliza mecanismos como registros de transacciones, puntos de control y copias de seguridad para restaurar la base de datos a un estado consistente.

La durabilidad, una de las propiedades ACID, implica que una transacción confirmada debe conservar sus efectos incluso ante determinados tipos de fallos.

---

# 5. Tipos de bases de datos

La diversidad de aplicaciones actuales ha producido una diversidad de modelos de bases de datos. No existe un modelo universalmente adecuado para todos los problemas.

La selección depende de factores como:

* Tipo de datos.
* Relaciones existentes.
* Patrón de consultas.
* Escala.
* Consistencia requerida.
* Frecuencia de escritura.
* Frecuencia de lectura.
* Distribución geográfica.
* Necesidades de rendimiento.
* Características de la aplicación.

Kleppmann (2017) explica que los sistemas de almacenamiento presentan diferentes ventajas y compromisos, por lo que la selección de una tecnología debe relacionarse con las necesidades concretas de la aplicación.

## 5.1 Bases de datos relacionales

Las bases de datos relacionales organizan la información principalmente mediante relaciones, que normalmente se representan como tablas.

Cada tabla contiene filas y columnas.

Ejemplo:

```text
ESTUDIANTES

+-----------+----------+----------+
| matricula | nombre   | semestre |
+-----------+----------+----------+
| 1001      | Ana      | 3        |
| 1002      | Luis     | 2        |
| 1003      | Carlos   | 4        |
+-----------+----------+----------+
```

El modelo relacional fue propuesto formalmente por Codd (1970). Su importancia se debe, entre otros aspectos, a que permitió representar los datos de una forma basada en relaciones matemáticas y reducir la dependencia respecto de estructuras de almacenamiento específicas.

Los sistemas relacionales suelen utilizar SQL para definir y consultar los datos.

### Ventajas

Entre sus características se encuentran:

* Estructuras bien definidas.
* Restricciones de integridad.
* Relaciones entre tablas.
* Consultas complejas.
* Soporte para transacciones.
* Herramientas maduras.
* Amplio uso empresarial.

### Caso de uso real

Un sistema bancario constituye un caso representativo. Las cuentas, clientes, movimientos, sucursales y operaciones presentan relaciones claramente definidas.

Otro caso corresponde a sistemas escolares. Las relaciones entre estudiantes, materias, profesores, grupos e inscripciones pueden representarse de manera estructurada mediante tablas y claves.

### Ejemplos

Entre los sistemas gestores relacionales se encuentran:

* PostgreSQL.
* MySQL.
* MariaDB.
* Oracle Database.
* Microsoft SQL Server.
* SQLite.

PostgreSQL es un ejemplo particularmente completo porque combina el modelo relacional con capacidades adicionales para diferentes tipos de datos y extensiones (PostgreSQL Global Development Group, 2026).

---

## 5.2 Bases de datos orientadas a documentos

Las bases de datos de documentos almacenan registros como documentos estructurados. MongoDB, por ejemplo, utiliza documentos BSON, una representación binaria relacionada con JSON (MongoDB, 2026).

Un documento podría tener una estructura como:

```json
{
  "nombre": "Ana",
  "carrera": "Inteligencia Artificial",
  "semestre": 3,
  "materias": [
    "Bases de Datos",
    "Álgebra Lineal",
    "Algoritmos"
  ]
}
```

La estructura permite representar objetos que contienen información anidada.

Este modelo resulta útil cuando los datos no tienen exactamente la misma estructura o cuando la representación de una entidad puede contener conjuntos de elementos relacionados.

MongoDB señala que su modelo de documentos permite representar estructuras similares a los objetos utilizados por muchas aplicaciones modernas (MongoDB, 2026).

### Ventajas

* Estructuras flexibles.
* Facilidad para representar datos jerárquicos.
* Adecuación para aplicaciones web.
* Escalamiento horizontal.
* Posibilidad de almacenar documentos con estructuras diferentes.

### Caso de uso real

Una plataforma de comercio electrónico puede utilizar documentos para representar productos. Un teléfono puede tener atributos diferentes de los de una computadora portátil o una prenda de ropa.

En lugar de obligar a todos los productos a compartir exactamente las mismas columnas, un documento puede contener los atributos específicos de cada producto.

Otro caso es el almacenamiento de perfiles de usuarios, donde algunos usuarios pueden tener preferencias, configuraciones o datos adicionales que no necesariamente existen para todos.

---

## 5.3 Bases de datos clave-valor

Las bases de datos clave-valor utilizan una estructura conceptual sencilla: una clave identifica un valor.

Ejemplo:

```text
"usuario:1001" -> "Ana"
"sesion:AB123" -> "usuario1001"
"contador:visitas" -> 15820
```

La clave funciona como identificador y el valor puede ser una cadena, número, estructura serializada u otro tipo dependiendo del sistema.

Este modelo es especialmente útil cuando las operaciones principales consisten en recuperar información mediante una clave conocida.

### Ventajas

* Operaciones simples.
* Alto rendimiento para determinadas consultas.
* Estructura sencilla.
* Facilidad para escalar en algunos sistemas.
* Adecuación para datos temporales o de acceso frecuente.

### Caso de uso real

Los sistemas de caché constituyen un caso clásico. Una aplicación puede almacenar temporalmente el resultado de una consulta costosa:

```text
producto:458 -> información del producto
```

Cuando otra solicitud necesita el mismo producto, el sistema puede recuperar rápidamente el valor sin consultar nuevamente todas las fuentes originales.

También pueden utilizarse para sesiones de usuarios, contadores, colas y configuraciones.

Redis es uno de los ejemplos más conocidos dentro de este espacio, aunque sus capacidades actuales abarcan estructuras más complejas que un modelo clave-valor extremadamente simple.

---

## 5.4 Bases de datos de familias de columnas

Las bases de datos de familias de columnas, también conocidas como wide-column databases, organizan los datos en estructuras diseñadas para manejar grandes cantidades de información distribuida.

Apache Cassandra es un ejemplo importante. Su documentación describe a Cassandra como una base de datos NoSQL distribuida de código abierto que implementa un modelo de almacenamiento de columnas anchas y está diseñada para sistemas distribuidos a gran escala (Apache Cassandra, 2026).

Este modelo no debe confundirse directamente con el almacenamiento columnar utilizado en algunos sistemas analíticos. Aunque ambos utilizan el concepto de columnas, responden a problemas diferentes.

Las bases de datos de familias de columnas suelen diseñarse alrededor de los patrones de consulta que tendrá la aplicación.

### Ventajas

* Distribución.
* Escalamiento horizontal.
* Alta disponibilidad.
* Manejo de grandes volúmenes.
* Adecuación para determinadas cargas de escritura.

### Caso de uso real

Un sistema global que recibe eventos constantemente puede utilizar una arquitectura de este tipo para almacenar grandes cantidades de registros distribuidos geográficamente.

Por ejemplo, una plataforma podría registrar eventos de actividad:

```text
usuario
fecha
tipo_evento
contenido
```

Cuando el volumen alcanza miles de millones de registros, distribuir la carga entre múltiples nodos puede ser más importante que mantener un modelo relacional tradicional.

Cassandra fue concebida precisamente dentro del contexto de problemas de almacenamiento distribuido a gran escala y combina ideas provenientes de sistemas como Dynamo y Bigtable (Apache Cassandra, 2026).

---

## 5.5 Bases de datos de grafos

Las bases de datos de grafos están diseñadas para representar entidades y las relaciones que existen entre ellas.

Un grafo está formado principalmente por nodos y relaciones. Los nodos representan entidades y las relaciones representan conexiones.

Por ejemplo:

```text
(Ana) ----AMIGA_DE----> (Laura)
  |
  | ESTUDIA
  v
(Inteligencia Artificial)
```

En una base de datos relacional, este tipo de estructura puede representarse mediante tablas y claves foráneas. Sin embargo, cuando las consultas dependen principalmente de recorrer muchas relaciones, un modelo de grafos puede resultar más natural.

Neo4j utiliza un modelo de grafos de propiedades en el que los nodos y relaciones pueden contener propiedades (Neo4j, 2026).

### Ventajas

* Representación natural de relaciones.
* Consultas sobre conexiones.
* Recorridos de grafos.
* Adecuación para redes complejas.
* Modelado flexible de relaciones.

### Caso de uso real

Las redes sociales constituyen un ejemplo evidente.

Una persona puede seguir a otras personas, pertenecer a grupos, interactuar con publicaciones y compartir intereses.

Una consulta como:

> ¿Qué usuarios están conectados con Ana mediante amigos de amigos?

puede convertirse en un problema de recorrido de relaciones.

Otro caso es la detección de fraude. Una red de transacciones puede representarse como un grafo en el que las cuentas, tarjetas, dispositivos y comercios son nodos y las transacciones son relaciones.

---

# 5.6 Bases de datos de series temporales

Las bases de datos de series temporales están especializadas en datos asociados con el tiempo.

Una serie temporal puede representarse como una secuencia de mediciones:

```text
10:00 -> 25.4
10:01 -> 25.6
10:02 -> 25.7
10:03 -> 25.9
```

El tiempo forma parte fundamental del significado del dato.

InfluxDB, por ejemplo, está orientado al almacenamiento y procesamiento de series temporales. Su documentación identifica como ejemplos datos de sensores industriales, métricas de servidores, frecuencia cardiaca, lluvia y precios financieros (InfluxData, 2026).

### Ventajas

* Consultas por intervalos de tiempo.
* Agregaciones temporales.
* Alta frecuencia de escritura.
* Compresión y organización especializada.
* Adecuación para monitoreo.

### Caso de uso real

Un centro de datos puede registrar cada pocos segundos:

* Uso de CPU.
* Memoria.
* Temperatura.
* Tráfico de red.
* Latencia.
* Errores.

Con esos registros pueden generarse gráficas y detectar cambios anormales.

En IoT también puede utilizarse para registrar mediciones de sensores.

---

# 5.7 Bases de datos espaciales

Las bases de datos espaciales están diseñadas para manejar información relacionada con ubicaciones y geometrías.

Los datos pueden representar:

* Puntos.
* Líneas.
* Polígonos.
* Rutas.
* Regiones.
* Coordenadas.

Una aplicación de mapas necesita responder preguntas como:

* ¿Qué restaurantes se encuentran cerca de determinada ubicación?
* ¿Qué carreteras intersectan una región?
* ¿Qué objetos se encuentran dentro de un área?
* ¿Cuál es la distancia entre dos puntos?

Una base de datos relacional tradicional puede almacenar coordenadas, pero una extensión espacial permite realizar operaciones especializadas sobre geometrías.

PostGIS es un ejemplo de tecnología espacial asociada con PostgreSQL.

### Caso de uso real

Una aplicación de transporte puede almacenar las ubicaciones de vehículos y calcular cuáles se encuentran cerca de una solicitud.

Otro ejemplo corresponde a sistemas de información geográfica utilizados para analizar terrenos, infraestructura, rutas y regiones.

La información espacial también aparece en logística, agricultura, navegación y planificación urbana.

---

# 5.8 Bases de datos vectoriales

Las bases de datos vectoriales están relacionadas con el almacenamiento y búsqueda de representaciones numéricas llamadas vectores.

En inteligencia artificial, un texto, imagen, audio u otro objeto puede transformarse mediante un modelo en una representación vectorial llamada embedding.

Por ejemplo:

```text
"gato"
    ↓
[0.21, -0.15, 0.73, 0.08, ...]
```

El vector no debe interpretarse como una lista de palabras. Representa características aprendidas por un modelo.

La búsqueda vectorial intenta encontrar vectores cercanos dentro de un espacio matemático.

Si dos documentos tienen representaciones similares, una búsqueda por similitud puede identificar que están relacionados semánticamente aunque no compartan exactamente las mismas palabras.

### Caso de uso real

Un sistema de recuperación documental puede convertir miles de documentos en vectores y posteriormente buscar aquellos cuyo contenido sea semánticamente similar a una consulta.

Este mecanismo resulta especialmente importante en aplicaciones de inteligencia artificial generativa.

Lewis et al. (2020) mostraron la relevancia de combinar modelos generativos con mecanismos de recuperación de información en sistemas de Retrieval-Augmented Generation (RAG). En estos sistemas, un componente de recuperación proporciona información externa que puede incorporarse al proceso de generación.

Las bases de datos vectoriales pueden formar parte de esta arquitectura al permitir localizar documentos o fragmentos similares a una consulta.

---

# 6. Clasificación de los sistemas gestores de bases de datos

Los DBMS pueden clasificarse desde diferentes perspectivas. No existe una única clasificación porque una misma tecnología puede pertenecer simultáneamente a varias categorías.

## 6.1 Clasificación por modelo de datos

Según el modelo de datos, pueden distinguirse:

### Relacionales

Utilizan tablas y relaciones.

Ejemplos:

* PostgreSQL.
* MySQL.
* Oracle Database.
* SQL Server.

### Documentales

Utilizan documentos estructurados.

Ejemplo:

* MongoDB.

### Clave-valor

Utilizan asociaciones entre claves y valores.

Ejemplos:

* Redis.
* Amazon DynamoDB.

### Familias de columnas

Ejemplos:

* Cassandra.
* HBase.

### Grafos

Ejemplos:

* Neo4j.
* Amazon Neptune.

### Especializados

Incluyen sistemas orientados a:

* Series temporales.
* Datos espaciales.
* Vectores.
* Otros dominios concretos.

## 6.2 Clasificación por número de usuarios

También pueden clasificarse de acuerdo con la cantidad de usuarios que pueden utilizar el sistema.

### Monousuario

Un sistema monousuario está diseñado para que una sola persona utilice la base de datos en un momento determinado.

Este tipo de organización puede aparecer en aplicaciones pequeñas o locales.

### Multiusuario

Los sistemas multiusuario permiten que diferentes usuarios accedan simultáneamente.

Los DBMS empresariales son normalmente multiusuario.

La administración de concurrencia, permisos y transacciones adquiere especial importancia en este escenario.

## 6.3 Clasificación por número de sitios

Otra clasificación distingue entre sistemas centralizados y distribuidos.

### Centralizados

Los datos se administran principalmente en un solo sitio o servidor.

Una aplicación puede conectarse a un servidor que concentra la base de datos.

### Distribuidos

Los datos pueden encontrarse en diferentes nodos o ubicaciones.

Un DBMS distribuido debe resolver problemas adicionales relacionados con:

* Comunicación.
* Replicación.
* Consistencia.
* Particionamiento.
* Recuperación.
* Disponibilidad.

Las bases de datos distribuidas son especialmente importantes cuando la escala o la ubicación geográfica de los usuarios hace conveniente distribuir la infraestructura.

## 6.4 Clasificación por propósito

Los sistemas también pueden clasificarse según el tipo de carga de trabajo.

### OLTP

OLTP significa Online Transaction Processing.

Se enfoca en operaciones transaccionales frecuentes y relativamente pequeñas.

Ejemplos:

* Registrar una compra.
* Realizar un depósito.
* Actualizar una dirección.
* Registrar una inscripción.

### OLAP

OLAP significa Online Analytical Processing.

Está orientado al análisis de grandes cantidades de información.

Ejemplos:

* Analizar ventas de varios años.
* Comparar resultados por regiones.
* Identificar tendencias.
* Generar indicadores.

Un sistema puede utilizar diferentes tecnologías para las operaciones transaccionales y para el análisis.

## 6.5 Clasificación por licencia

Los DBMS también pueden clasificarse según su modelo de licencia.

### Código abierto

El código fuente se encuentra disponible bajo una licencia que permite determinadas formas de uso, modificación y distribución.

Ejemplos:

* PostgreSQL.
* MariaDB.
* MySQL Community Edition.
* Apache Cassandra.

### Propietarios

Son desarrollados y distribuidos bajo condiciones definidas por una empresa u organización.

Ejemplos:

* Oracle Database.
* Microsoft SQL Server en determinadas ediciones.
* IBM Db2.

### Servicios administrados

También existen servicios en la nube en los que la infraestructura del DBMS es administrada por un proveedor.

En este caso, el usuario puede consumir la base de datos sin encargarse directamente de tareas como instalación, mantenimiento del servidor físico o determinados procedimientos de actualización.

La clasificación por licencia no determina por sí misma las capacidades técnicas de una base de datos. Una tecnología de código abierto puede ser utilizada en sistemas extremadamente grandes, mientras que una tecnología propietaria puede utilizarse en aplicaciones pequeñas.

---

# 7. Bases de datos en flujos de trabajo de inteligencia artificial

## 7.1 Relación entre datos e inteligencia artificial

La inteligencia artificial moderna depende fuertemente de los datos.

Un modelo de aprendizaje automático necesita ejemplos para aprender patrones. Un sistema de clasificación necesita datos etiquetados. Un modelo de lenguaje necesita grandes cantidades de texto durante su entrenamiento. Un sistema de recomendación necesita información sobre usuarios, productos e interacciones.

La base de datos puede aparecer en diferentes etapas del flujo.

Un flujo simplificado puede representarse así:

```text
Fuentes de datos
      |
      v
Almacenamiento
      |
      v
Limpieza y transformación
      |
      v
Conjunto de entrenamiento
      |
      v
Entrenamiento del modelo
      |
      v
Evaluación
      |
      v
Aplicación
      |
      v
Nuevos datos
      |
      +----------> almacenamiento y monitoreo
```

La base de datos puede intervenir en prácticamente todas estas etapas.

## 7.2 Bases de datos como fuente de datos para entrenamiento

Los conjuntos de entrenamiento pueden almacenarse en diferentes formatos y sistemas.

Una organización puede tener:

* Imágenes.
* Texto.
* Audio.
* Registros de sensores.
* Datos de clientes.
* Historiales de transacciones.
* Eventos de aplicaciones.

Una base de datos relacional puede conservar metadatos sobre esos elementos.

Por ejemplo:

```text
imagen_id
ruta
categoría
fecha
fuente
etiqueta
```

La imagen podría encontrarse físicamente en un sistema de almacenamiento de archivos u objetos, mientras que la base de datos conserva la información que permite localizarla y describirla.

Esta separación puede ser útil cuando los archivos son grandes.

## 7.3 Calidad de los datos

Un modelo de aprendizaje automático puede producir resultados deficientes si los datos utilizados para entrenarlo presentan problemas.

Algunos problemas frecuentes son:

* Datos faltantes.
* Valores duplicados.
* Etiquetas incorrectas.
* Formatos inconsistentes.
* Datos desactualizados.
* Sesgos en la muestra.
* Errores de captura.

La base de datos puede ayudar a detectar algunos de estos problemas mediante restricciones, consultas y procesos de validación.

Por ejemplo, una consulta puede identificar registros con valores nulos inesperados:

```sql
SELECT *
FROM estudiantes
WHERE semestre IS NULL;
```

Otra puede localizar duplicados:

```sql
SELECT correo, COUNT(*)
FROM usuarios
GROUP BY correo
HAVING COUNT(*) > 1;
```

Estos mecanismos no solucionan automáticamente todos los problemas de calidad, pero proporcionan herramientas para detectarlos y controlarlos.

## 7.4 Bases de datos y recuperación de información

La recuperación de información consiste en localizar documentos o elementos relevantes frente a una consulta.

Un buscador tradicional puede trabajar con coincidencias de palabras.

Por ejemplo:

```text
Consulta:
"base de datos relacional"

Documentos encontrados:
1. Fundamentos de bases de datos
2. Introducción al modelo relacional
3. SQL y bases de datos
```

Los sistemas modernos pueden utilizar también representaciones vectoriales para recuperar información semánticamente relacionada.

En lugar de buscar únicamente palabras idénticas, una consulta puede transformarse en un vector y compararse con los vectores de documentos almacenados.

## 7.5 Similaridad vectorial

Supóngase que dos textos son:

```text
"El perro está corriendo en el parque."

"Un can corre al aire libre."
```

Aunque utilizan palabras diferentes, un modelo de representación puede producir vectores relativamente cercanos porque los conceptos son similares.

Una medida común es la similitud coseno.

Dados dos vectores:

$$
A=(a_1,a_2,\ldots,a_n)
$$

y

$$
B=(b_1,b_2,\ldots,b_n)
$$

la similitud coseno puede expresarse como:

$$
\cos(\theta)=
\frac{A\cdot B}{\|A\|\|B\|}
$$

Un valor cercano a 1 indica una orientación similar entre los vectores.

Las bases de datos y motores especializados pueden utilizar estructuras de índices para realizar búsquedas aproximadas de vecinos cercanos cuando existen millones de vectores.

Malkov y Yashunin (2018) propusieron el método HNSW, una estructura ampliamente estudiada para la búsqueda aproximada de vecinos cercanos.

## 7.6 Bases de datos vectoriales

Una base de datos vectorial está especializada en almacenar embeddings y realizar consultas de similitud.

Una estructura conceptual podría ser:

```text
id_documento
texto
embedding
metadatos
```

Ejemplo:

```text
ID: 125
Texto: "Introducción al modelo relacional"
Vector: [0.13, -0.44, 0.72, ...]
Categoría: bases_de_datos
```

Cuando llega una consulta, se genera su embedding y se busca cuáles son los vectores más cercanos.

El resultado puede ser utilizado posteriormente por otra parte del sistema.

## 7.7 Retrieval-Augmented Generation

Los sistemas de generación aumentada por recuperación, conocidos como RAG, combinan un modelo generativo con una etapa de recuperación.

El proceso puede resumirse así:

```text
Pregunta del usuario
        |
        v
Generación del embedding
        |
        v
Búsqueda de documentos similares
        |
        v
Documentos relevantes
        |
        v
Construcción del contexto
        |
        v
Modelo generativo
        |
        v
Respuesta
```

Lewis et al. (2020) describieron una arquitectura que combina memoria paramétrica de un modelo generativo con memoria no paramétrica proporcionada por un índice externo.

Esta idea tiene una consecuencia importante: la información utilizada por un sistema de IA no tiene que encontrarse exclusivamente dentro de los parámetros del modelo.

Una base de datos puede funcionar como fuente externa de conocimiento.

## 7.8 Ejemplo de un sistema RAG universitario

Una universidad podría disponer de miles de documentos:

* Reglamentos.
* Planes de estudio.
* Manuales.
* Horarios.
* Procedimientos.
* Preguntas frecuentes.

Cada documento puede dividirse en fragmentos.

Cada fragmento se transforma en un embedding y se almacena junto con metadatos.

Ejemplo:

```text
id: 874
documento: reglamento_escolar.pdf
sección: reinscripciones
texto: "El periodo de reinscripción..."
vector: [...]
```

Cuando se realiza una consulta como:

```text
"¿Qué requisitos existen para reinscribirse?"
```

el sistema puede buscar fragmentos similares y entregar los resultados al modelo generativo.

La base de datos cumple entonces una función distinta de la que tendría en un sistema administrativo tradicional. Ya no solamente conserva registros estructurados, sino que participa en la recuperación semántica del conocimiento.

## 7.9 Bases de datos y sistemas de recomendación

Los sistemas de recomendación también dependen de bases de datos.

Una plataforma puede almacenar:

```text
usuario
producto
calificación
fecha
tiempo_de_visualización
interacción
```

Estos datos permiten identificar patrones.

Por ejemplo, si un usuario ha interactuado con determinados productos, un modelo puede calcular recomendaciones.

La base de datos puede conservar tanto los datos originales como los resultados generados por el sistema.

## 7.10 Bases de datos para características de modelos

En algunos sistemas de aprendizaje automático se utilizan almacenes de características, conocidos como feature stores.

Una característica puede ser:

* Edad del usuario.
* Número de compras en los últimos 30 días.
* Promedio de transacciones.
* Frecuencia de acceso.
* Tiempo desde la última actividad.

Estas características pueden utilizarse para alimentar modelos.

El almacenamiento centralizado ayuda a evitar que diferentes sistemas calculen las mismas características de formas inconsistentes.

## 7.11 Datos en tiempo real

Algunas aplicaciones de inteligencia artificial necesitan procesar datos que llegan continuamente.

Un sistema de detección de anomalías puede recibir:

```text
temperatura
presión
vibración
corriente
```

cada segundo.

Una base de datos de series temporales puede almacenar estas mediciones y facilitar consultas por ventanas de tiempo.

Un modelo de IA puede entonces utilizar los datos recientes para identificar comportamientos anormales.

## 7.12 Bases de datos de grafos en inteligencia artificial

Los grafos también tienen aplicaciones importantes en IA.

Un grafo puede representar:

* Personas.
* Empresas.
* Productos.
* Documentos.
* Relaciones.
* Transacciones.

Los algoritmos de aprendizaje sobre grafos pueden aprovechar esta estructura para detectar comunidades, relaciones relevantes o patrones.

Por ejemplo, en detección de fraude, una red de transacciones puede revelar relaciones que no serían evidentes al analizar cada transacción de manera aislada.

La combinación de bases de datos de grafos y aprendizaje automático permite trabajar con información donde las relaciones son tan importantes como las características individuales de las entidades.

---

# 8. Integración de los conceptos

Los conceptos anteriores no funcionan como temas aislados. Existe una relación histórica y técnica entre ellos.

Los problemas de los archivos independientes motivaron la creación de sistemas gestores de bases de datos. Posteriormente, la necesidad de representar datos de manera independiente de su almacenamiento físico impulsó modelos y arquitecturas que separaran diferentes niveles de descripción.

El modelo relacional proporcionó una forma estructurada de representar información mediante relaciones. SQL se convirtió en una interfaz fundamental para trabajar con datos relacionales.

La arquitectura ANSI-SPARC permitió explicar cómo separar las vistas externas, el esquema conceptual y la representación interna.

La independencia de datos buscó reducir el impacto que tienen los cambios físicos y lógicos sobre las aplicaciones.

Con el crecimiento de los sistemas distribuidos y de Internet aparecieron nuevas necesidades. Las bases de datos NoSQL surgieron en distintos contextos para atender problemas relacionados con escalabilidad, distribución, flexibilidad de esquema y determinados patrones de acceso.

Posteriormente, la expansión de aplicaciones de inteligencia artificial introdujo necesidades adicionales. Los datos comenzaron a incluir grandes colecciones de documentos, embeddings, series temporales, relaciones complejas y otros formatos.

Por esta razón, los diferentes tipos de bases de datos no deben considerarse necesariamente como tecnologías que compiten por reemplazar unas a otras. En muchos sistemas modernos se utilizan varias tecnologías simultáneamente.

Una arquitectura podría utilizar:

```text
PostgreSQL
    |
    +-- datos transaccionales

MongoDB
    |
    +-- documentos flexibles

Redis
    |
    +-- caché

InfluxDB
    |
    +-- métricas temporales

Neo4j
    |
    +-- relaciones complejas

Base vectorial
    |
    +-- búsqueda semántica
```

La selección depende de las necesidades de cada componente.

Kleppmann (2017) destaca que los sistemas de datos presentan diferentes compromisos en aspectos como consistencia, escalabilidad, disponibilidad y modelo de consulta. La arquitectura adecuada surge de relacionar esos compromisos con las necesidades reales del sistema.

---

# 9. Importancia de las bases de datos en la ingeniería de inteligencia artificial

En una carrera relacionada con inteligencia artificial, el estudio de bases de datos tiene una importancia que va más allá de la construcción de sistemas administrativos.

Los modelos de IA requieren datos. Pero los datos no aparecen automáticamente en una forma adecuada para entrenar modelos.

Primero deben recopilarse. Después necesitan almacenamiento. Posteriormente pueden requerir limpieza, transformación, etiquetado, validación y selección.

Una base de datos puede actuar como una pieza central dentro de ese flujo.

Un proyecto de visión artificial, por ejemplo, podría utilizar una base de datos para almacenar metadatos de imágenes:

```text
imagen_id
nombre_archivo
clase
fecha
fuente
resolución
etiqueta
```

Los archivos de imagen podrían encontrarse en almacenamiento de objetos, mientras que la base de datos administra la información relacionada.

En un proyecto de procesamiento de lenguaje natural, la base de datos podría almacenar:

```text
documento_id
texto
idioma
autor
fecha
categoría
embedding
```

Esto permite combinar búsquedas tradicionales con búsquedas semánticas.

En un proyecto de aprendizaje supervisado, podría conservarse:

```text
id
caracteristica_1
caracteristica_2
caracteristica_3
etiqueta
```

para generar posteriormente conjuntos de entrenamiento y prueba.

La calidad de la base de datos influye directamente en la calidad de los procesos posteriores.

## 9.1 Reproducibilidad

Otro aspecto importante es la reproducibilidad.

Si un modelo fue entrenado con un conjunto de datos determinado, resulta conveniente conservar información sobre:

* Versión de los datos.
* Fecha de extracción.
* Transformaciones aplicadas.
* Etiquetas utilizadas.
* Parámetros relevantes.
* Fuente original.

Una base de datos puede contribuir a mantener esta trazabilidad.

Esto adquiere importancia cuando un modelo debe volver a entrenarse o cuando es necesario explicar cómo se obtuvo un resultado.

## 9.2 Auditoría

Los sistemas de IA también pueden necesitar registros sobre las operaciones realizadas.

Una base de datos puede conservar:

```text
fecha
usuario
modelo
entrada
resultado
versión_modelo
```

Estos registros pueden ayudar a analizar errores y evaluar el comportamiento de un sistema.

## 9.3 Escalabilidad

Los proyectos de IA pueden producir grandes cantidades de información.

Un sistema experimental puede comenzar con unos cuantos miles de registros. Posteriormente puede crecer hasta millones o miles de millones.

La arquitectura de datos debe anticipar este crecimiento.

No siempre significa que una sola tecnología deba manejarlo todo. En arquitecturas modernas es común combinar almacenamiento de objetos, bases de datos, sistemas de procesamiento distribuido y motores especializados.

---

# 10. Diferencia entre una base de datos y un sistema gestor de bases de datos

Una distinción fundamental consiste en separar los conceptos de base de datos y DBMS.

La **base de datos** corresponde a los datos organizados y relacionados.

El **DBMS** es el software encargado de administrar esos datos.

Puede utilizarse una analogía con una biblioteca.

Los libros representarían los datos. El sistema de organización, catálogo, préstamos, permisos y control representaría los mecanismos de administración.

La biblioteca física no es lo mismo que el sistema que administra los préstamos.

De manera similar:

```text
Base de datos
=
datos almacenados

DBMS
=
software que administra esos datos
```

PostgreSQL, por ejemplo, es un sistema gestor de bases de datos. Las tablas creadas dentro de una instancia de PostgreSQL constituyen parte de las bases de datos administradas por el sistema.

Esta diferencia parece sencilla, pero resulta importante porque muchas veces los términos se utilizan como si fueran equivalentes.

---

# 11. Ejemplo integral

Una plataforma universitaria permite mostrar cómo se relacionan varios de los conceptos estudiados.

La plataforma necesita almacenar estudiantes, materias, profesores, grupos y calificaciones.

Una base de datos relacional puede representar:

```text
ESTUDIANTE
    |
    | se inscribe
    v
INSCRIPCIÓN
    |
    v
GRUPO
    |
    v
MATERIA
```

Las calificaciones pueden almacenarse mediante relaciones estructuradas.

El DBMS administra:

* Integridad.
* Transacciones.
* Concurrencia.
* Seguridad.
* Consultas.
* Recuperación.

Una vista externa podría mostrar solamente:

```text
Nombre
Materia
Calificación
```

mientras que el esquema conceptual contiene muchas más entidades.

El almacenamiento interno puede utilizar índices para acelerar consultas.

Si posteriormente se crea un índice sobre matrícula, la consulta de un estudiante puede acelerarse sin que cambie la consulta SQL utilizada por la aplicación. Esto constituye un ejemplo sencillo de independencia física.

Si la universidad también almacena documentos académicos, podría utilizarse una base documental.

Si necesita almacenar métricas de servidores, una base de series temporales podría resultar adecuada.

Si desarrolla un buscador semántico para reglamentos, una base vectorial podría almacenar embeddings.

Si se analiza la relación entre estudiantes, materias, profesores y proyectos, una base de grafos podría complementar la infraestructura.

La arquitectura final podría combinar diferentes modelos.

Esto demuestra que el concepto de base de datos debe estudiarse como una disciplina amplia y no únicamente como el aprendizaje de una herramienta específica.

---

# 12. Conclusión

Las bases de datos constituyen una de las estructuras fundamentales de los sistemas informáticos porque permiten organizar, conservar, consultar y proteger información de manera sistemática. Su desarrollo respondió a problemas concretos que aparecieron cuando los archivos independientes dejaron de ser suficientes para manejar grandes cantidades de información compartida.

La diferencia entre dato e información permite comprender que almacenar valores no es suficiente. Los datos adquieren utilidad cuando poseen significado y contexto. Una base de datos organiza esos datos dentro de un dominio determinado y establece relaciones que permiten utilizarlos de manera consistente.

Las definiciones propuestas por autores como Elmasri y Navathe, Silberschatz et al. y Date coinciden en varios elementos fundamentales, aunque cada aproximación resalta aspectos diferentes. En conjunto, permiten entender una base de datos como una colección organizada y relacionada de datos que puede ser administrada mediante mecanismos especializados.

Los sistemas gestores de bases de datos surgieron para resolver problemas asociados con los sistemas basados en archivos. La redundancia, inconsistencia, aislamiento, dificultad de acceso, falta de integridad, problemas de concurrencia y seguridad fueron factores importantes en la evolución del área.

La arquitectura ANSI-SPARC proporcionó un modelo para separar tres niveles de descripción: externo, conceptual e interno. Esta separación permitió explicar la independencia de datos y establecer una diferencia entre la forma en que los usuarios observan la información, la estructura lógica global y la forma física en que los datos son almacenados.

La independencia física y lógica continúa siendo un concepto importante porque permite reducir el impacto de determinados cambios sobre las aplicaciones. De esta manera, una modificación en el almacenamiento no necesariamente obliga a modificar todos los programas que utilizan la base de datos.

Los lenguajes de bases de datos también cumplen diferentes funciones. DDL permite definir estructuras, DML permite modificar datos, las instrucciones de consulta permiten recuperar información, DCL administra permisos y TCL controla transacciones. En conjunto, estos mecanismos permiten interactuar con el sistema de una manera estructurada.

La aparición de diferentes modelos de bases de datos responde a diferentes necesidades. Las bases relacionales resultan adecuadas para información estructurada y relaciones claramente definidas. Las bases documentales proporcionan flexibilidad para representar documentos. Las bases clave-valor ofrecen operaciones simples y rápidas para determinados escenarios. Las bases de familias de columnas se utilizan en sistemas distribuidos de gran escala. Las bases de grafos se especializan en relaciones complejas. Las bases de series temporales se orientan a datos asociados con el tiempo. Las bases espaciales trabajan con información geográfica y geométrica. Las bases vectoriales permiten almacenar representaciones numéricas y realizar búsquedas por similitud.

La inteligencia artificial ha ampliado todavía más el campo de aplicación de las bases de datos. Los modelos necesitan conjuntos de entrenamiento, metadatos, información de validación y mecanismos para recuperar conocimiento. Las búsquedas vectoriales permiten localizar información semánticamente relacionada y forman parte de arquitecturas modernas como RAG.

En este contexto, una base de datos puede desempeñar funciones muy diferentes dependiendo de la aplicación. Puede conservar transacciones, documentos, métricas, relaciones, coordenadas geográficas o embeddings. También puede funcionar como parte de una infraestructura de datos utilizada para entrenar y operar modelos de inteligencia artificial.

El desarrollo histórico de las bases de datos muestra que no existe una única solución válida para todos los problemas. Cada modelo surge para responder a determinadas necesidades y presenta ventajas y limitaciones. Por esta razón, la selección de un sistema gestor debe basarse en las características de los datos, los patrones de acceso, los requisitos de consistencia, el volumen de información, la distribución del sistema y los objetivos de la aplicación.

El conocimiento de estos fundamentos permite comprender mejor tecnologías concretas como PostgreSQL, MongoDB, Cassandra, Neo4j, InfluxDB y los sistemas de almacenamiento vectorial. Más importante aún, permite analizar qué problema intenta resolver cada tecnología y por qué una arquitectura puede requerir más de un tipo de base de datos.

En ingeniería de inteligencia artificial, esta comprensión adquiere una importancia particular. Los modelos pueden ser sofisticados, pero necesitan información organizada, accesible y confiable. La calidad del sistema de datos condiciona las posibilidades del sistema de inteligencia artificial que se construye sobre él.

Por ello, el estudio de las bases de datos no constituye únicamente una introducción al almacenamiento de información. Representa una parte fundamental de la ingeniería de software, la ciencia de datos y la inteligencia artificial. Comprender cómo se representan, almacenan, consultan, protegen y recuperan los datos permite construir sistemas más organizados, escalables y confiables.

---

# Referencias

Apache Cassandra. (2026). *Apache Cassandra documentation*. Apache Software Foundation. https://cassandra.apache.org/doc/stable/

Codd, E. F. (1970). A relational model of data for large shared data banks. *Communications of the ACM, 13*(6), 377–387. https://doi.org/10.1145/362384.362685

Date, C. J. (2004). *An introduction to database systems* (8th ed.). Addison-Wesley.

Elmasri, R., & Navathe, S. B. (2016). *Fundamentals of database systems* (7th ed.). Pearson.

InfluxData. (2026). *InfluxDB documentation*. https://docs.influxdata.com/

Kleppmann, M. (2017). *Designing data-intensive applications: The big ideas behind reliable, scalable, and maintainable systems*. O'Reilly Media.

Lewis, P., Perez, E., Piktus, A., Petroni, F., Karpukhin, V., Goyal, N., Küttler, H., Lewis, M., Yih, W.-t., Rocktäschel, T., Riedel, S., & Kiela, D. (2020). Retrieval-augmented generation for knowledge-intensive NLP tasks. *Advances in Neural Information Processing Systems, 33*, 9459–9474.

Malkov, Y. A., & Yashunin, D. A. (2018). Efficient and robust approximate nearest neighbor search using hierarchical navigable small world graphs. *IEEE Transactions on Pattern Analysis and Machine Intelligence*. https://doi.org/10.1109/TPAMI.2018.2889473

MongoDB. (2026). *MongoDB documentation*. https://www.mongodb.com/docs/

Neo4j. (2026). *Neo4j documentation*. https://neo4j.com/docs/

PostgreSQL Global Development Group. (2026). *PostgreSQL documentation*. https://www.postgresql.org/docs/

Ramakrishnan, R., & Gehrke, J. (2003). *Database management systems* (3rd ed.). McGraw-Hill.

Silberschatz, A., Korth, H. F., & Sudarshan, S. (2019). *Database system concepts* (7th ed.). McGraw-Hill.

Tsichritzis, D. C., & Klug, A. (Eds.). (1978). *The ANSI/X3/SPARC DBMS framework: Report of the study group on database management systems*. ACM.
