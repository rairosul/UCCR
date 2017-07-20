---

copyright:
 years: 2017
lastupdated: "2017-6-22"

  ---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Ejecución de despliegues
{: #deployment_run}

{{site.data.keyword.uccr_short}} sirve para ejecutar despliegues de software. Complete despliegues resolviendo las tareas de un plan de despliegue.
{:shortdesc}

Un despliegue se inicia cuando se inicia una de las tareas elegibles del plan. Un despliegue planificado se inicia automáticamente en la hora planificada si una de sus tareas elegibles es una tarea automática como por ejemplo, las tareas de UrbanCode Deploy o de tipo retrasadas. De lo contrario, el despliegue se inicia iniciando una de las tareas elegibles del plan. Si el plan contiene varias tareas elegibles, puede iniciar cualquiera de ellas. Un despliegue se inicia de forma manual en cualquier momento. Un despliegue planificado se puede iniciar de forma manual antes de su hora planificada.   

El patrón de ejecución del plan desplegado determina cuándo las tareas serán elegibles para ser iniciadas. Si el plan sigue un patrón de ejecución secuencial, que es el patrón predeterminado, las tareas pasan a ser elegibles en el orden en el que se listan en el plan, empezando por la primera tarea. Después de que se haya resuelto la primera tarea, la segunda tarea pasa a ser elegible. Inicie las tareas manuales elegibles pulsando el botón **Iniciar** de la tarea. Las tareas automáticas como, por ejemplo, las tareas de UrbanCode Deploy, se inician de forma automática tan pronto como pasan a ser elegibles. 

Las tareas en un grupo con un patrón de ejecución en paralelo se convierten en elegibles simultáneamente. Las tareas en los grupos con tareas en paralelo se pueden iniciar en cualquier orden. Los grupos anidados y las tareas con dependencias específicas pueden afectar al patrón de ejecución. 

Un plan de despliegue se puede modificar después de haber iniciado el despliegue. Es posible añadir, suprimir y modificar tareas. 

Una vez resueltas todas las tareas, se considera que se ha completado el despliegue. Una tarea está resuelta si su estado es de `Completada`, `Error` u `Omitida`. Si vuelve a abrir una tarea o añade una tarea después de que se haya completado el despliegue, el estado del despliegue cambia a `En curso`.

## Cómo iniciar despliegues de forma manual
{: #deployment_start}

Un despliegue se puede iniciar de forma manual en cualquier momento, incluso cuando se hayan planificado despliegues para iniciarse más tarde. 

Es posible que algunas tareas en un plan de despliegue no se puedan aplicar para dicho despliegue. Por ejemplo, las tareas de UrbanCode Deploy no se pueden aplicar si no se ha especificado una versión o un entorno para las tareas. Cuando se crean tareas de UrbanCode Deploy, puede retrasarlas seleccionando el entorno y la versión aplicando la opción **Utilizar versión**. Antes de que empiece el despliegue, asegúrese de que todas las tareas de UrbanCode Deploy son aplicables al despliegue que va a poner en marcha.     

Puede excluir deliberadamente tareas de un despliegue. Puede hacer que tareas etiquetadas sean inaplicables excluyendo sus etiquetas del despliegue. Las tareas con etiquetas excluidas son inaplicables para el despliegue.  

Las tareas inaplicables tienen un estado de `No aplicable`. No es posible iniciar tareas con un estado de `No aplicable`. Si una tarea inaplicable es un requisito previo para una tarea activa, se omite la dependencia.   

Para iniciar un despliegue, siga los pasos siguientes:

1. En la página Planes de despliegue, pulse el plan de despliegue que desea utilizar para el despliegue. Se visualizará la página de detalles del despliegue. 

2. Para hacer que tareas etiquetadas sean inaplicables al despliegue actual, pulse **Versiones** y, a continuación, en el área **Etiquetas**, borre las etiquetas. Si una tarea tiene más de una etiqueta, borre todas ellas. 

2. Para seleccionar la versión o el entorno para las tareas inaplicables de UrbanCode Deploy, pulse **Versiones** y, a continuación, seleccione el entorno y la versión. También puede cambiar las opciones de las tareas cuyos entornos y versiones ya han sido seleccionados. 

1. Opcionalmente, pulse **Ocultar tareas no aplicables** para eliminar tareas inaplicables a la lista de tareas visualizadas. Las tareas ocultas no se eliminan del plan de despliegue. 

1. Pulse la acción **Iniciar** <img class="inline" src="images/task-start.png" alt="acción iniciar tarea"> sobre una de las tareas elegibles del plan. Si hay más de una tarea elegible, puede iniciar cualquiera de ellas. El botón de iniciar únicamente se muestra en las tareas elegibles. Una tarea iniciada tiene el estado de `En curso` hasta que se resuelve.

Después de que haya comenzado el despliegue, el estado del plan cambia a `En curso`. El estado permanece `En curso` hasta que se resuelvan todas las tareas. Una vez resueltas todas las tareas, el estado del plan cambia a `Hecho`.

## Resolución de tareas
{: #deployment_taskComplete}

Complete un despliegue resolviendo las tareas del plan de despliegue. Una tarea iniciada se resuelve cuando su estado cambia a `Completada`, `Error` u `Omitida`. 

Las tareas manuales se resuelven utilizando la acción de estado apropiada. Las tareas automáticas como, por ejemplo, las tareas de UrbanCode Deploy, cambian su estado de forma automática cuando cambian las condiciones. Sin embargo, puede resolver manualmente tareas automáticas. Por ejemplo, podrían marcar como errónea una tarea en UrbanCode Deploy que parece que está tomando demasiado tiempo en resolverse. 

Para resolver una tarea iniciada, aplique uno de los siguientes estados:

<ul>
<li>Pulse **Completar** <img class="inline" src="images/task-complete.png"  alt="acción completar tarea"> para finalizar una tarea. `Completar` significa que la tarea ha finalizado con los resultados esperados.
</li>
<li>Pulse **Omitir** <img class="inline" src="images/task-skip.png"  alt="acción omitir tarea"> para omitir una tarea en el despliegue actual.
</li>
<li>Pulse **Error** <img class="inline" src="images/task-fail.png"  alt="acción error en tarea"> para finalizar una tarea. `Error` significa que la tarea no ha finalizado o ha finalizado con resultados inesperados.
</li>
<li>Pulse **Reabrir tarea** <img class="inline" src="images/task-reopen.png" alt="acción reabrir tarea"> para abrir una tarea resuelta. Si todas las tareas están completadas, al reabrir una tarea reabre el despliegue.
</li>
</ul>

## Ejecución de despliegues planificados
{: #deployment_startSchedule}

Un despliegue planificado se inicia de forma automática en su hora planificada si alguna de sus tareas automáticas son elegibles de ser iniciadas. Si un plan de despliegue no contiene ninguna tarea automática elegible, inicie el despliegue de forma manual iniciando alguna de las tareas elegibles. 

Un despliegue planificado se puede iniciar de forma manual en cualquier momento, incluso si el plan tiene tareas automáticas elegibles. 
