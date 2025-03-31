# Experiencia personal

> Voy a hacer memoría año tras año y describir cuales fueron mis trabajos, metas, logros y avances. Con tanta experiencia, puedo compartir cosas que me llenaron mucho pero en esta sección trataré de resumir un poco los proyectos que participé y lo que aprendí de cada uno.

## Actualidad Profesional

Actualmente trabajo en **Mercado Libre** con el puesto de *Software Engineer*, trabajo para ellos desde noviembre de 2022. Mi tarea principal se basa en el análisis, diseño y programación en los sistemas de soporte al usuario de Mercado Libre. Usando tecnologías: MySQL, Git, Java,, Golang, NewRelic, Kibana.

Durante estos años me he encontrado distintos desafíos, muchísima gente con muchísimo conocimiento, y me vi involucrado en proyectos que realmente me llevaron a otro nivel como desarrollador, en una empresa como la que es Mercado Libre.

En la empresa entré como si fuera un desarrollador más, rápidamente me han visto muy participativo, coordinando proyectos, involucrándose activamente en soluciones de difícil resolución y capacitando a las personas nuevas o a las rotaciones del equipo. Esto me permitió ser miembro activo de tres equipos distintos y tener iniciativas propias que ayudaron a solucionar problemas de múltiples equipos. Como nota, estoy agradecido con estas oportunidades.

El área para la cual desarrollé cosas es Customer Experience, básicamente, trabajar en los sistemas de la gente que da soporte a los clientes de Mercado Libre. En un principio solo fue el desarrollo del backend de una herramienta que permitiera a los Team Leaders de los representantes de Mercado Libre gestionar estados, tiempos de atención y visualización de información vital para el negocio. Luego, me involucré en el sistema que permite el alta, baja, modificación y personalización de la información de los representantes, la combinación de ambos sistemas me permitió tener una visión del negocio tan amplio que podía opinar sobre decisiones y sugerir mejoras o incluso cuestionar los cambios que se planteaban.

Además, por fuera de mi trabajo normal y por decisión propia, trabajé automatizando procesos rutinarios en la empresa: migraciones de datos, alertas en aplicaciones, monitores de estado. Con la intención de eliminar o reducir los trabajos administrativos, las fallas en los sistemas y la detección de potenciales vulnerabilidades. Esto me dio reconocimiento en el área CX IT y me abrió las puertas a colaborar en un equipo core del área donde trabajan seniors y expertos especializados en sus respectivas tecnologías.

Este equipo core se enfoca en la asignación de casos: básicamente cuando un usuario de Mercado Libre solicita hablar con un representante el sistema del equipo toma el caso, busca un representante para este usuario y permite la comunicación entre ambas partes. ¿Por qué es core? Simplemente porque sin este sistema nadie podría entablar una comunicación por ningún canal. 

Mi colaboración con este equipo se basó en la optimización del tiempo de respuesta, la revisión de los pull request, la definición de modelos de datos, infraestructura y ayudar en la gestión de proyectos. Esta experiencia fue un crecimiento brutal para mi, no solo por la oportunidad, sino también por la naturaleza del problema: un sistema con cientos de miles de RPS incluso las soluciones sencillas pueden no lograr procesar todo coordinadamente. Y por sobre todo, por la capacidad que tiene cada uno de mis compañeros, algunos especializados en golang, otros en bases de datos, otros en infraestructura, otros con muchísimo conocimiento en asincronismo, otros en testeo, otros del negocio. De todos pude aprender cosas y ponerlas en práctica.

Hoy en día, abril del 2025, me encuentro trabajando para el equipo de CX Phone. Este equipo se encarga de la gestión de llamadas del área de CX, de modo que toda comunicación telefónica que se realiza sea entrante o saliente (es decir, llama el cliente o lo llamamos nosotros) es gestionada por mi equipo. 

## Mi pasado profesional

Al principio de mi carrera profesional trabajé un año para un cliente que me contrató en forma de prácticas, esto me abrió las puertas a mis primeros sistemas profesionales. Luego trabajé 9 años en la consultora Softtek. De esto tengo poca documentación que me de exactamente el orden cronológico de las cosas, pero contaré todo lo más abarcativo posible.

Dentro de la consultora me asignaron al equipo de compras de OSDE, se puede decir que oficialmente fue mi primer encuentro con una empresa realmente grande. Las tareas que se me asignaron fueron de testing: preparar el ambiente, realizar tests, documentar todo lo que iba viendo. 

Al poco tiempo, y en mi inexperiencia con las tecnologías, pregunté en mi consultora si podría cambiar de cliente (debido a que sentía que en el equipo en el que me encontraba no estaba creciendo profesionalmente hablando).

Luego de un pequeño proceso de selección interna llegue al cliente Ternium Siderar, lugar donde realmente sentí mucho crecimiento profesional. Entré como DBA, mis tareas eran optimizar consultas, depurar las bases de datos, crear modelos de datos nuevos y mejores, realizar procesos de ETL de distintas fuentes y generar reportes o simplemente almacenarlo en bases de datos.

Con el tiempo, y al ver mi performance, un lider del cliente consultó si podría ayudar a desarrolloar en un sistema: SIASSO (Sistema Integrado de Ambiente, Seguridad y. Salud Ocupacional). En él empecé mis pasos con C#, SQL, Javascript, Html y CSS. Además de UI/UX para mobile.

Durante 8 años estuve en el sistema SIASSO, donde no solo pude aprender tecnologías nuevas, sino que también desarrollé muchísimo mis habilidades blandas: analisis de requerimientos, manejar comunicaciones con gerentes, directores y operarios, diseño de soluciones innovadoras, propuestas de soluciones mobile. 

Desglozando un poco más, con el analisís de requerimientos se basó en poder hablar con distintos roles para saber las problematicas en la planta, poder poner en palabras un poco más técnicas las necesidades y plantear a superiores soluciones y cómo impactaría cambios nuevos en los sistemas. Esto no solo me obligó a aprender a documentar, sino también a hablar con distintas personas responsables y generar propuestas de calidad basandome en fundamentos y no en suposiciones.

Una pequeña lista de cósas de impacto que logré en Ternium:
- Depuración de las bases de datos vía scripts (datos y su estructura, junto con stored procedures). Logrando que una tarea de más de 6 meses se realice en poco más de dos semanas ya que automaticé el proceso de detección de objetos inutilizados, marcandolos y generación de script para su eliminación.
- Creación de una migración en las bases de datos que permitía cambiar la estructura organizacional sin impactar en las consultas. Esto no solo permitió hacer el cambio sin grandes refactorizaciones, sino que también permitió que en una segunda reestructuración no tuviera afectacción alguna. Se realizó modificando algunas consultas, generando vistas y funciones que se encargaban de devolver siempre la misma información independientemente la tabla origen que contenia la estructura organizacional.
- El analisis de necesidad, el diseño del sistema, el desarrollo del mismo y la puesta en producción del módulo de Hora Segura Dirigida. Este fue mi proyecto más grande dentro de la empresa, con él los operarios tenían una forma de programar auditorias en la planta para prevenir accidentes en los operarios. Esto llevó las **muertes** de 4 anuales a ninguna, o simplemente lesiones. Además, en este proyecto se me encargó la capacitación de los operarios, supervisores, doctores, gerentes y directores de Ternium Brasil para el uso del sistema.
- Realicé el boceto inicial de SIASSO Mobile, mostré una primera demo y logré conseguir el proyecto el cual pude desarrollar para tablets iOS. Esto impulsó el uso de SIASSO dentro de las plantas, logrando auditorías con mejor información, menos el uso de papel y accionar más rápido de los técnicos de Seguridad e Higiene.