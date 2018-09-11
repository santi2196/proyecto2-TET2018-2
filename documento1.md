

#Documento 1

##1.Definicion del equipo, proyecto y aplicacion.
___

###a. Miembros del equipo y asignacion de QA a miembros del equipo.

**QA1:** Disponibilidad >> Estudiante: José O. Rengifo C.

**QA2:** Rendimiento >> Estudiante: Ivan S. Vargas


###b. Selección de la aplicación basada en Proyecto1

Para la realizion de este proyecto se decidio escoger la aplicacion que se encuentra en el siguiente repositiorio: [Proyecto1](https://github.com/santi2196/TopicosTelematicaP1 "Proyecto TET 1")

###c. Descripción de la aplicación
El programa usa un sistema de localizacion que permite por medio de una API de Google Maps posicionar a los usuarios que se registren en la aplicacion, esta ubicacion se representa en un mapa por medio de una etiquetas asi por medio de varias se ve una ruta que haya seguido un usuario por cierto tiempo.

###d. Requisitos Funcionales:

- El sistemas debe gestionar el registro e validacion de usuarios.
- El sistema debe permitir a cada usuario ingresar a una sesion propia.
- El sistema debe poder almacenar en BD la ubicacion geografica de un usuario 		      cuando usa una sesion en especifica.
- El sistema debe poder mostrar las ubicaciones de un usuario que fueron almacenadas en BD y poder dar un rango de tiempo para visualizar esta informacion.

##2. Detalles técnicos del diseño e implementación funcional para el proyecto 2.
---

La aplicacion se desarrollara con el popular frameworkweb Ruby On Rails. Dicha aplicacion estara encapsulada en un contenedor docker, el cual se encontrara contiguo a otros dos contenedores, quienes contendran la base de datos y nginx (Proxy inverso). La orquestacion de dichos contenedores sera dirigida por Kubernetes para permitir que la aplicacion sea escalable.

##3. Aplicación completa desplegada en el Data Center Académico.
---

DCA: [ivargas.dis.eafit.edu.co](ivargas1.dis.eafit.edu.co "Aplicacion desplegada en el DCA")

##4. Definición de Tecnología v1 – Infraestructura TI: Servidores, Software Base, Redes, etc.
---

Para la solucion del proyecto 1 la APP fue desplegada en el DCA y en una instancia de AWS. Para desplegarla en estos distintos servidores se configuraron las maquinas virtuales con el S.O. Centos 7 y fue ejecutada usando Docker y Docker-compose. Se desplegó con 3 contenedores conectados entre si, uno para la aplicacion(Ruby On Rails) otro para la base de datos (Postgres) y el ultimo para un servidor Web (Nginx). Las vistas de esta aplicacion estan contruidas utilizadon Bootstrap.

##5. Marco-referencia-v1


###Disponibilidad (Confiabilidad y Recuperación)

En general, el principal objetivo del QA de disponibilidad se resume a Permitir soportar las fallas del sistema de tal manera que el servicio entregado por dicho sistema siga siendo compatible con su especificación. Esto implica entender que una falla solo representa una amenaza cuando este fenómeno afecta tanto a los servicios del sistema, que las especificaciones del sistema ya no se cumplen. La literatura propone estrategias y tácticas que garantizan la disponibilidad desde los siguientes tres frentes:

- **Detección de fallas:** Para la detección de fallas existen varias tácticas, entre ellas se encuentran las estrategias de Ping o Echo (para verificar que un sistema responda), monitores tipo heatbeat o watchdog (para verificar que un sistema sigue ”con vida” de no ser así, lo reinicia), Sistemas de excepciones, y sistemas de Redundancia Modular Triple.

- **Recuperación de fallas:** En relación a la recuepración de fallas existen 2 grandes procesos:

	* **Reparation and repair:** En esta fase la idea es que el sistema reconozca la falla y la repare, pero que mientras eso ocurre desde la perspectiva del usuario el sistema debe seguir funcionando de manera correcta, para esto tecnologías como redundancia pasiva y redundancia activa, sparing, gestión de excepciones e incluso actualizaciones de software; permiten administrar este proceso.

	* **Reintroduction:** En esta frase el objetivo es dejar las funcionalidades del sistema corriendo en estado normal, cumpliendo con las especificaciones iniciales, esta reintroducción se habilita despues de la fase de reparación y las tecnologías que se usan para esto son Sombra, resincronización de estado, Rollback, Reinicio escalado, entre otras.

- Prevención de fallas Una de las mejores prácticas a la hora de garantizar disponibilidad y enfrentarse a las fallas, es preveer su aparición y/o realizar actividades preventivas que minimicen el impacto de las fallas, a este nivel las tecnologías que podemos usar son Retiro del servicio, Gestión de Transacciones atómicas, tener Monitores de Procesos o Prevención de Excepciones.
  
  
  
  
**[Ver más](https://www.semanticscholar.org/paper/Realizing-and-Refining-Architectural-Tactics-%3A-Scott/5840ae598740c6dbfb69dc3ce30f43efa23ef9b9) [Tácticas de arquitetura: Disponibilidad](https://profesores.virtual.uniandes.edu.co/~isis2503/dokuwiki/lib/exe/fetch.php?media=principal:modulo10-disponibilidad.pdf)**

###Rendimiento
El rendimiento puede ser definido como la efectividad total de un sistema. Puede ser medido de diferentes maneras pero las más comunes incluyen el throughput, definido como cuántas unidades de información puede procesar el sistema en un determinado tiempo, y el tiempo de respuesta. El rendimiento depende de muchas variables desde cómo está codificado el sistema hasta la infraestructura que lo soporta. Por lo general es un atributo muy importante y debe ser considerado desde las fases iniciales de diseño de una solución. Existen varias maneras de lograr un buen rendimiento:

- Entrega y carga optimizada de los assets estáticos.
- Seleccionar un framework adecuado.
- Monitoreo del sistema.
- Considerar el rendimiento desde tempranas etapas del diseño de la solución.
- Peticiones on-demand y asíncronas.
- Desarrollo y pruebas iterativas.

Implementar pruebas de rendimiento también es un aspecto muy importante en un sistema, se deben considerar pruebas de la carga del sistema y de la infraestructura.
