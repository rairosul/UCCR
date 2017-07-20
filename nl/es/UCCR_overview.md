---

copyright:
 years: 2017
lastupdated: "2017-6-22"

  ---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}


# Acerca de {{site.data.keyword.uccr_short}}
{: #about_UCCR}


## ¿Qué es {{site.data.keyword.uccr_short}}?
{: #what}

{{site.data.keyword.uccr_full}} es una herramienta de gestión de releases empresarial escalable. {{site.data.keyword.uccr_short}} ofrece la posibilidad de trabajar transparentemente con otros servicios de Bluemix y con sus productos UrbanCode instalados localmente. 

{{site.data.keyword.uccr_short}} permite: 

<ul>
<li>Orquestar despliegues de varias aplicaciones
</li>
<li>Visualizar proyectos y dependencias de aplicaciones
</li>
<li>Automatizar la promoción de código en base a su calidad
</li>
<li>Realizar una planificación optimizada de los sucesos más importantes de los releases
</li>
</ul>


## Términos clave
{: #keyterms}

Los siguientes términos se utilizan con frecuencia en {{site.data.keyword.uccr_short}}:

**Actividades**: Las actividades hacen referencia a los elementos que se pueden visualizar en la lista **Actividades** en la página Releases. Las actividades incluyen releases, sucesos y planes de despliegue. Puede filtrar la lista de **Actividades** por estado, fecha y etiqueta.   

**Aplicación**: Aplicación hace referencia a las aplicaciones de IBM UrbanCode Deploy que {{site.data.keyword.uccr_short}} gestiona. En {{site.data.keyword.uccr_short}}, las aplicaciones integradas se asignan a tareas de UrbanCode Deploy. Se seleccionan procesos, versiones y entornos de aplicación. Cuando se ejecuta una tarea de UrbanCode Deploy, también se ejecuta la aplicación asociada en IBM UrbanCode Deploy.

**Tarea automática**: Durante los despliegues, las tareas automáticas se inician tan pronto como son elegibles para ser ejecutadas. Entre las tareas automáticas se incluyen los siguientes tipos de tarea: UrbanCode Deploy, conducto de Continuous Delivery, correo electrónico, Slack, ejecutar otro plan y retrasadas. 

**Tareas dependientes**: La capacidad de iniciar una tarea puede depender de la finalización de otras tareas. Una tarea que espera a que se completen otras tareas se denomina tareas dependiente. La tarea que la tarea dependiente espera, es denominada tarea de requisito previo. Las tareas dependientes no se puede iniciar hasta que no se hayan resuelto todas sus tareas de requisito previo. Normalmente, las dependencias sirven para asegurarse de que las tareas se ejecutan en el orden esperado.

**Duración**: El tiempo que las tareas necesitan para ejecutarse. La duración se mide desde el momento en que se inicia la tarea hasta que se resuelve.  Cuando se crean algunos tipos de tarea, se estima su duración esperada. Se informa de la duración es minutos. 

**Entorno**: Representa los entornos de aplicación de IBM UrbanCode Deploy. En UrbanCode Deploy, los entornos definen destinos de despliegue. En {{site.data.keyword.uccr_short}}, al ejecutar tareas de UrbanCode Deploy, se selecciona el entorno. Se puede especificar el entorno al crear la tarea o en tiempo de ejecución. 

**Patrón de ejecución**: Hace referencia al orden en el que las tareas pasan a ser elegibles para su ejecución. De forma predeterminada, el patrón de ejecución del plan es secuencial. Las tareas secuenciales se ejecutan ordenadamente, empezando por la primera tareas en el plan de despliegue. Las tareas se pueden combinar en grupos. A los grupos se les asigna el patrón de ejecución en paralelo. Las tareas en paralelo se pueden ejecutar en cualquier orden y de forma simultánea. 

Cuando crea grupos les asigna el patrón de ejecución en paralelo. El patrón de ejecución esperado puede verse afectado por las dependencias de las tareas. 

**Integración**: Hace referencia a la comunicación estandarizada entre {{site.data.keyword.uccr_short}} y otros productos y servicios. La comunicación entre {{site.data.keyword.uccr_short}} y los productos integrados puede ser bidireccional. 
Por ejemplo, IBM UrbanCode Deploy puede enviar datos de aplicación a {{site.data.keyword.uccr_short}}, y {{site.data.keyword.uccr_short}} puede a continuación ejecutar las aplicaciones. 
Las integraciones se configuran con IBM Bluemix DevOps Connect.

**Proceso**: Hace referencia a los procesos de aplicación de UrbanCode Deploy. En UrbanCode Deploy, los procesos definen actividades de automatización como, por ejemplo, el despliegue de componentes. En {{site.data.keyword.uccr_short}}, cuando ejecuta tareas de UrbanCode Deploy, selecciona el proceso. Puede seleccionar el proceso cuando se crea la tarea o en tiempo de ejecución. 

**Etiqueta**: Una etiqueta es un texto que se puede aplicar a tareas o releases.  Cuando se aplican a las tareas, las etiquetas determinan la aplicabilidad de las tareas para un despliegue dado. Cuando se aplican a releases, las etiquetas permiten organizar y filtrar releases. 

**Grupo de tareas**: Puede combinar dos o más tareas en un grupo de tareas. Cuando crea un grupo, se define el patrón de ejecución del grupo, secuencial o en paralelo. 

**Equipo**: Un equipo es un conjunto de usuarios y grupos. En {{site.data.keyword.uccr_short}}, los equipos gestionan releases, sucesos y planes de despliegue. Los equipos se pueden importar desde IBM UrbanCode Deploy.

**Versión**: Representa una instantánea de una aplicación de IBM UrbanCode Deploy. Cuando se crea una tarea de UrbanCode Deploy, las versiones que pertenecen a la aplicación que se asigna a la tarea se almacenan en el plan de despliegue. Puede utilizar el separador Versión para seleccionar las versiones y los entornos de las aplicaciones que se utilizan cuando se ejecuta una tarea. 

## Conceptos clave
{: #keyconcepts}

**Despliegue**: El término despliegue hace referencia a las actividades que se realizan para entregar un proyecto de software a un destino de despliegue. Normalmente, se ejecutan despliegues en cada etapa del ciclo de vida de un release, finalizando en la etapa de producción. Las actividades que se realizan durante un despliegue, denominadas tareas, se definen en los planes de despliegue. Un despliegue se inicia iniciando una de las tareas elegibles del plan. Un despliegue se completa resolviendo todas las tareas en el plan de despliegue. 

**Plan de despliegue**: Un plan de despliegue es un plan repetible que se utiliza para generar releases de software. Los planes de despliegue contienen las tareas que se utilizan para ejecutar los despliegues. Cuando añade una tarea a un plan de despliegue, define su tipo y su duración.

Cuando está listo para ejecutar un despliegue, inicia una de las tareas elegibles del plan. La elegibilidad de una tarea para ser iniciada viene determinada por su patrón de ejecución. Las tareas automáticas se inician de forma automática tan pronto como son elegibles para ser ejecutadas. Las tareas manuales se inician manualmente.  

**Suceso**: Los sucesos son actividades relacionadas con el release que se aplican a dichos releases y que se siguen en el calendario. Los sucesos permiten organizar releases y otras actividades dependientes del tiempo como, por ejemplo, vacaciones y periodos de indisponibilidad. 

**Tarea**: Generalmente, una tarea representa una actividad empresarial significativa con puntos inicio y finalización y una duración medible. Las duraciones se utilizan para estimar los tiempos de despliegue. Las tareas se añaden a los planes de despliegue. Cuando ejecuta un despliegue, se deben completar las tareas en el plan. 

Es posible definir varios tipos de tareas.
<ul>
<li>Las tareas de UrbanCode Deploy ejecutan procesos de aplicaciones en IBM UrbanCode Deploy. Continuous Release realiza un seguimiento de las versiones (instantáneas) y los entornos que utilizan las aplicaciones. Estas tareas se inician de forma automática cuando son elegibles para ser ejecutadas. </li>
<li>Las tareas manuales representan cualquier actividad manual que está relacionada con un despliegue, por ejemplo, iniciar un servidor. Las tareas manuales, como el nombre implica, se inician manualmente. </li>
<li>Las tareas retrasadas representan hitos importantes. Una tarea retrasada es una tarea automática que empieza tan pronto como es elegible para ello, y finaliza en el instante especificado para la tarea. Normalmente, las tareas retrasadas constituyen requisitos previos para otras tareas. </li>
<li>Las tareas de cabecera proporcionan elementos organizativos a los planes de despliegue. Las tareas de cabecera sirven para identificar un grupo de tareas, o añadir notas o instrucciones a un grupo. Las tareas de cabecera son tareas automáticas y finalizan en el momento que se inician. No es posible definir duraciones para las tareas de cabecera.
</li>
<li>Las tareas de correo electrónico envían mensajes a cuentas de correo electrónico.
</li>
<li>Las tareas de Slack envían mensajes a un canal de Slack que especifica el usuario.
</li>
<li>Las tareas de conducto de Continuous Delivery automatizan los flujos de trabajo de DevOps. Las tareas de conducto sirven para gestionar sus conductos. </li>
</ul>

**Release**: Un release es un contenedor para planes de despliegue, sucesos y etiquetas. Generalmente, un release contiene varios planes de despliegue, aunque no hay ningún requisito que establezca que un release debe contener más de un plan. Hablando de nuevo de forma general, cada plan en un release representa una etapa en el ciclo de vida de desarrollo como, por ejemplo, una etapa de QA o una etapa de producción. Las etapas, o los planes de despliegue, se denominan colectivamente como el ciclo de vida de los releases. 
