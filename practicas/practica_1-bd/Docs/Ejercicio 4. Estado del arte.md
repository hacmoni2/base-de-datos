# Ejercicio 4. Estado del arte: tres artículos científicos

## Introducción

Para este ejercicio se seleccionaron tres artículos científicos relacionados con el uso y desarrollo de las bases de datos. La intención no fue solamente buscar artículos que mencionaran el término "bases de datos", sino encontrar investigaciones que trataran problemas reales relacionados con su funcionamiento, administración, seguridad y rendimiento.

Los tres artículos seleccionados fueron publicados entre 2020 y 2021 y cuentan con DOI. Además, fueron publicados en revistas o congresos académicos relacionados con el área de bases de datos. Uno de ellos tiene una relación directa con la inteligencia artificial, lo cual resulta especialmente interesante considerando que la carrera que estudio es Ingeniería en Inteligencia Artificial.

Los artículos tratan problemas diferentes. El primero estudia cómo utilizar modelos de comportamiento para desarrollar sistemas gestores de bases de datos que puedan automatizar algunas tareas de administración. El segundo se enfoca en la integridad de los datos y en cómo detectar modificaciones no autorizadas en un sistema de almacenamiento. Finalmente, el tercero analiza la optimización del procesamiento de consultas y la manera de agruparlas para reducir el tiempo necesario para ejecutarlas.

---

# 1. MB2: Decomposed Behavior Modeling for Self-Driving Database Management Systems

## 1.1. Cita en formato APA 7

Ma, L., Zhang, W., Jiao, J., Wang, W., Butrovich, M., Lim, W. S., Menon, P., & Pavlo, A. (2021). MB2: Decomposed behavior modeling for self-driving database management systems. *Proceedings of the 2021 International Conference on Management of Data*, 1248–1261.

DOI: https://doi.org/10.1145/3448016.3457276

Artículo: https://db.cs.cmu.edu/papers/2021/ma-sigmod2021.pdf

ACM Digital Library: https://doi.org/10.1145/3448016.3457276

## 1.2. Problema que aborda

Administrar una base de datos puede requerir tomar muchas decisiones dependiendo de la carga de trabajo, los recursos disponibles y la forma en que se están realizando las operaciones. Tradicionalmente, muchas de estas decisiones dependen de administradores que deben analizar el comportamiento del sistema y modificar su configuración.

El artículo estudia el problema de construir sistemas gestores de bases de datos que puedan tomar algunas de estas decisiones de manera automática. En particular, los autores trabajan con el concepto de sistemas gestores de bases de datos autónomos, también conocidos como *self-driving database management systems*.

## 1.3. Método o propuesta de los autores

Los autores presentan MB2, una propuesta basada en el modelado descompuesto del comportamiento de un sistema gestor de bases de datos.

La idea principal es que, en lugar de intentar representar todo el comportamiento del sistema mediante un único modelo, se puede dividir el problema en diferentes componentes. De esta manera, es posible estudiar y modelar diferentes aspectos del funcionamiento del sistema por separado.

Esta propuesta tiene una relación importante con la inteligencia artificial y el aprendizaje automático, porque los modelos de comportamiento pueden utilizarse para analizar información obtenida durante la ejecución de una base de datos y posteriormente utilizar ese conocimiento para tomar decisiones.

Uno de los aspectos que me parece más interesante es que el objetivo no es simplemente utilizar inteligencia artificial porque sí, sino utilizarla para resolver un problema específico de administración de bases de datos.

## 1.4. Resultado principal

La principal aportación del artículo es el desarrollo de una estrategia para modelar el comportamiento de los sistemas gestores de bases de datos de una forma descompuesta. Esto busca facilitar la creación de sistemas capaces de automatizar determinadas decisiones relacionadas con su administración.

El trabajo muestra que existe una posibilidad de combinar las técnicas de aprendizaje automático con los sistemas gestores de bases de datos para conseguir que estos puedan adaptarse mejor a diferentes situaciones.

## 1.5. Relación con la Unidad Temática I

**Tema relacionado: Sistemas gestores de bases de datos y administración de bases de datos.**

El artículo se relaciona con la Unidad Temática I porque analiza el funcionamiento y la administración de un sistema gestor de bases de datos. Además, permite relacionar los conceptos tradicionales de bases de datos con nuevas aplicaciones de inteligencia artificial.

La investigación muestra que un SGBD no solamente se encarga de guardar información, sino que también puede analizar su propio comportamiento y utilizar esa información para mejorar su funcionamiento.

## 1.6. Aportación para mi proyecto del curso

Este artículo me ayuda a entender que trabajar con una base de datos no significa solamente crear tablas, insertar registros y realizar consultas. También es importante conocer cómo se comporta el sistema cuando aumenta la cantidad de información o cuando se realizan muchas operaciones.

Para mi proyecto del curso, esto puede ser útil porque me hace considerar aspectos como el rendimiento de PostgreSQL y la posibilidad de utilizar herramientas automáticas para analizar o mejorar el funcionamiento de una base de datos.

---

# 2. FastVer: Making Data Integrity a Commodity

## 2.1. Cita en formato APA 7

Arasu, A., Chandramouli, B., Gehrke, J., Ghosh, E., Kossmann, D., Protzenko, J., Ramamurthy, R., Ramananandro, T., Rastogi, A., Setty, S. T. V., Swamy, N., van Renen, A., & Xu, M. (2021). FastVer: Making data integrity a commodity. *Proceedings of the 2021 International Conference on Management of Data*, 89–101.

DOI: https://doi.org/10.1145/3448016.3457312

ACM Digital Library: https://doi.org/10.1145/3448016.3457312

Microsoft Research: https://www.microsoft.com/en-us/research/publication/fastver-making-data-integrity-a-commodity/

## 2.2. Problema que aborda

El segundo artículo se enfoca en un problema diferente: la integridad de los datos. En una base de datos no solamente es importante poder guardar y consultar información, sino también tener cierta seguridad de que los datos no hayan sido modificados de manera incorrecta o no autorizada.

Los autores estudian cómo detectar este tipo de modificaciones en un sistema de almacenamiento de datos. El problema resulta especialmente importante cuando la información almacenada es crítica y una modificación no autorizada podría producir resultados incorrectos.

## 2.3. Método o propuesta de los autores

Los autores presentan FastVer, un sistema de almacenamiento de tipo clave-valor diseñado para proporcionar mecanismos de verificación de la integridad de los datos.

Una parte importante de la propuesta consiste en utilizar estructuras criptográficas, particularmente árboles de Merkle. Estas estructuras permiten representar información mediante valores hash y posteriormente comprobar si los datos han sido modificados.

FastVer incorpora mecanismos para verificar los resultados obtenidos de las operaciones de lectura y detectar inconsistencias. De esta manera, el sistema puede identificar si existe una diferencia entre la información que debería estar almacenada y la información que realmente se encuentra en el sistema.

Otro aspecto importante es que los autores no se enfocan únicamente en demostrar que su sistema funciona, sino también en analizar formalmente las propiedades de su propuesta.

## 2.4. Resultado principal

Los autores reportan que FastVer puede proporcionar mecanismos de verificación de integridad manteniendo un rendimiento considerablemente superior al de algunos enfoques tradicionales utilizados para este tipo de comprobaciones.

El artículo también presenta una demostración formal relacionada con la corrección del sistema. En términos generales, la propuesta busca que una modificación de los datos pueda ser detectada mediante los mecanismos criptográficos utilizados.

Esto demuestra que la seguridad y la integridad de los datos no necesariamente tienen que considerarse como características completamente separadas del rendimiento de un sistema de almacenamiento.

## 2.5. Relación con la Unidad Temática I

**Tema relacionado: Integridad de los datos y sistemas gestores de bases de datos.**

Este artículo se relaciona con la importancia de mantener la información almacenada de manera correcta y confiable. La integridad es una característica importante de cualquier sistema de bases de datos, porque los datos almacenados deben conservar las condiciones establecidas por el sistema.

Aunque FastVer trabaja con un sistema de almacenamiento clave-valor y no únicamente con el modelo relacional tradicional, el problema que estudia es aplicable de manera general a los sistemas que almacenan información.

## 2.6. Aportación para mi proyecto del curso

Este artículo me hizo considerar que una base de datos no debe evaluarse solamente por si permite guardar y recuperar información. También es necesario pensar en qué tan confiable es la información que estamos almacenando.

En mi proyecto con PostgreSQL, esto puede relacionarse con aspectos como las restricciones de integridad, los permisos de usuarios, las copias de seguridad y las medidas necesarias para evitar modificaciones incorrectas de los datos.

---

# 3. Query Batching Optimization in Database Systems

## 3.1. Cita en formato APA 7

Eslami, M., Mahmoodian, V., Dayarian, I., & Charkhgard, H. (2020). Query batching optimization in database systems. *Computers & Operations Research, 121*, 104983.

DOI: https://doi.org/10.1016/j.cor.2020.104983

ScienceDirect: https://www.sciencedirect.com/science/article/pii/S0305054820301003

## 3.2. Problema que aborda

El tercer artículo estudia el problema del procesamiento de múltiples consultas en sistemas de bases de datos.

Cuando un sistema recibe una gran cantidad de consultas, ejecutarlas de manera individual puede requerir una cantidad importante de tiempo y recursos. Por esta razón, los autores investigan la posibilidad de agrupar diferentes consultas en lotes y determinar cuál es la mejor manera de realizar esta agrupación.

El objetivo es reducir el tiempo necesario para procesar las consultas sin tener que ejecutar cada una de ellas de manera completamente independiente.

## 3.3. Método o propuesta de los autores

Los autores desarrollan un modelo de optimización para determinar cómo deben dividirse las consultas en diferentes grupos o lotes.

Una de las partes de la propuesta consiste en construir una función capaz de predecir el tiempo necesario para procesar un determinado lote de consultas. Para esto se utilizan técnicas de regresión y posteriormente se construye un modelo de optimización.

Además del modelo matemático, los autores desarrollan heurísticas que permiten encontrar soluciones de manera más eficiente.

Para evaluar su propuesta utilizan diferentes conjuntos de consultas y benchmarks utilizados en el área de bases de datos, entre ellos TPC-H, TPC-DS y Join-Order Benchmark.

Me parece interesante que el artículo combine conceptos de bases de datos con técnicas de optimización matemática y predicción. Esto demuestra que el rendimiento de una base de datos puede estudiarse como un problema de optimización.

## 3.4. Resultado principal

Los autores reportan mejoras importantes en el tiempo necesario para procesar las consultas. En sus experimentos, las heurísticas propuestas consiguieron reducir el tiempo de recuperación hasta en un 61.8 % en comparación con el procesamiento de todas las consultas como un solo lote en el escenario utilizado.

También se reportan resultados favorables para el modelo utilizado para predecir los tiempos de procesamiento.

Estos resultados muestran que la forma en que se agrupan y procesan las consultas puede tener un impacto importante en el rendimiento de un sistema de bases de datos.

## 3.5. Relación con la Unidad Temática I

**Tema relacionado: Procesamiento y optimización de consultas en sistemas gestores de bases de datos.**

Este artículo se relaciona directamente con el funcionamiento de los sistemas gestores de bases de datos, específicamente con la manera en que procesan las consultas realizadas por los usuarios.

Una base de datos puede estar correctamente diseñada y contener información válida, pero eso no significa necesariamente que todas las consultas se ejecutarán de manera eficiente. Por esta razón, la optimización de consultas es un aspecto importante del trabajo con bases de datos.

## 3.6. Aportación para mi proyecto del curso

Este artículo me ayuda a comprender que una base de datos debe analizarse también desde el punto de vista del rendimiento. En un proyecto con PostgreSQL, por ejemplo, no solamente importa que una consulta entregue el resultado correcto, sino también cuánto tiempo tarda en hacerlo y qué recursos utiliza.

Esto me puede servir posteriormente para estudiar índices, planes de ejecución y diferentes formas de escribir consultas SQL que permitan obtener los resultados de manera más eficiente.

---

# Comparación de los tres artículos

Después de revisar los tres artículos, considero que una de las principales cosas que tienen en común es que ninguno se limita al almacenamiento básico de información. Los tres estudian problemas que aparecen cuando una base de datos se utiliza en situaciones más complejas y donde es necesario mejorar alguna de sus características.

El primer artículo, **MB2**, está enfocado en la administración automática de los sistemas gestores de bases de datos. Su relación con la inteligencia artificial es la más evidente de los tres artículos, ya que estudia modelos capaces de representar el comportamiento de una base de datos y utilizarlos para facilitar la toma de decisiones.

El segundo artículo, **FastVer**, se concentra en la integridad de la información. En este caso, la principal preocupación no es que las consultas sean más rápidas o que el sistema se administre automáticamente, sino que los datos puedan ser verificados y que las modificaciones no autorizadas puedan detectarse.

El tercer artículo, **Query Batching Optimization in Database Systems**, tiene como objetivo mejorar el rendimiento de las consultas. Su propuesta utiliza modelos matemáticos, regresión y heurísticas para determinar cómo agrupar las consultas y reducir el tiempo de procesamiento.

Por lo tanto, aunque los tres artículos pertenecen al área de bases de datos, cada uno analiza un problema diferente. El primero se puede relacionar principalmente con la **automatización y la inteligencia artificial**, el segundo con la **integridad y seguridad de los datos**, y el tercero con la **optimización y el rendimiento**.

Otra diferencia importante es la manera en que los autores buscan solucionar sus problemas. MB2 utiliza modelos de comportamiento; FastVer utiliza mecanismos criptográficos y verificación formal; mientras que el tercer artículo utiliza modelos matemáticos y técnicas de optimización.

A pesar de estas diferencias, los tres trabajos permiten observar algo importante: una base de datos moderna necesita resolver muchos problemas al mismo tiempo. No basta con que pueda almacenar información. También debe ser capaz de procesarla eficientemente, mantenerla confiable y, cada vez más, automatizar algunas de las tareas que anteriormente tenían que realizar los administradores.

A partir de la revisión de estos artículos, considero que un problema abierto interesante consiste en encontrar una forma de integrar estas características. Por ejemplo, sería interesante contar con un sistema gestor de bases de datos que pudiera analizar automáticamente las consultas que recibe, optimizar su ejecución, detectar posibles problemas de integridad y, al mismo tiempo, mantener un nivel adecuado de rendimiento.

Este problema resulta especialmente interesante desde el punto de vista de la Ingeniería en Inteligencia Artificial, porque los modelos de aprendizaje automático podrían utilizarse para analizar patrones de uso y ayudar al sistema a tomar determinadas decisiones. Sin embargo, también sería necesario considerar los riesgos de confiar demasiado en modelos automáticos, especialmente cuando las decisiones pueden afectar la integridad o disponibilidad de los datos.

En conclusión, la revisión de estos tres artículos permitió observar que el área de bases de datos continúa evolucionando y que actualmente existe una relación cada vez mayor entre las bases de datos, la inteligencia artificial, la seguridad y la optimización. Para mi formación, esto es importante porque permite entender que aprender SQL y diseñar tablas es solamente una parte del trabajo. También es necesario comprender qué sucede internamente cuando los datos son almacenados, consultados, protegidos y procesados.

---

# Referencias

* Arasu, A., Chandramouli, B., Gehrke, J., Ghosh, E., Kossmann, D., Protzenko, J., Ramamurthy, R., Ramananandro, T., Rastogi, A., Setty, S. T. V., Swamy, N., van Renen, A., & Xu, M. (2021). FastVer: Making data integrity a commodity. *Proceedings of the 2021 International Conference on Management of Data*, 89–101. https://doi.org/10.1145/3448016.3457312

* Eslami, M., Mahmoodian, V., Dayarian, I., & Charkhgard, H. (2020). Query batching optimization in database systems. *Computers & Operations Research, 121*, 104983. https://doi.org/10.1016/j.cor.2020.104983

* Ma, L., Zhang, W., Jiao, J., Wang, W., Butrovich, M., Lim, W. S., Menon, P., & Pavlo, A. (2021). MB2: Decomposed behavior modeling for self-driving database management systems. *Proceedings of the 2021 International Conference on Management of Data*, 1248–1261. https://doi.org/10.1145/3448016.3457276
