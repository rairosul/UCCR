---

copyright:
 years: 2017
lastupdated: "2017-6-22"

  ---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Gestión de tareas
{: #tasks_overview}

Una tarea representa una actividad significativa para el negocio y que está asociada al despliegue de software. Las tareas se definen en planes de despliegue.

{:shortdesc}

La mayoría de las tareas tienen un punto de partida, un punto final y una duración que se puede medir. Una tarea puede ser de uno de los siguientes tipos:

<ul>
<li>Una tarea **manual** puede representar cualquier actividad que esté asociada con un despliegue de software, como por ejemplo colocar un servidor fuera de línea o actualizar una base de datos. </li>
<li>Una tarea de **UrbanCode Deploy** representa una aplicación de IBM UrbanCode Deploy. Puede ejecutar aplicaciones de UrbanCode Deploy con este tipo de tarea. </li>
<li>Una tarea de **Conducto de Continuous Delivery** representa un conducto de {{site.data.keyword.contdelivery_full}}. Puede gestionar sus conductos de {{site.data.keyword.contdelivery_short}} con este tipo de tarea. </li>
<li>Una tarea **Retrasada** representa un suceso crítico que ocurre en un momento específico. </li>
<li>Una tarea de **Cabecera** es un elemento organizativo. Por ejemplo, puede utilizar una tarea de cabecera para identificar un grupo de tareas.</li>
<li>Una tarea de **Correo electrónico** permite enviar un correo electrónico cuando se ejecuta. </li>
<li>Una tarea de **Ejecutar otro plan** ejecuta planes de despliegue de otros despliegues que forman parte del mismo suceso del release. Se trata de un tipo de tarea experimental. </li>
<l1>Una tarea de **Slack** envía una mensaje a un canal Slack cuando se ejecuta. </l1>
</ul>

Puede añadir tareas a los planes de despliegue creando tareas o importando tareas desde archivos CSV que IBM UrbanCode Release u otra aplicación hayan creado. También puede copiar tareas desde otros planes de despliegue. Consulte [Importación de tareas](/docs/services/UCCR/UCCR_deployPlan.html#plan_importTasks) para obtener información sobre el formato del archivo CSV. 

## Creación de tareas
{: #tasks_create}

Al crear una tarea, seleccione el plan de despliegue en el que desea añadir la tarea. De forma predeterminada, las nuevas tareas se insertan en la parte inferior del plan de despliegue. Después de se haya creado una tarea, puede moverla, copiarla y pegarla en otro plan de despliegue.
[También es posible crear dependencias con otras tareas](/docs/services/UCCR/UCCR_tasks.html#tasks_dependencies).

Después de guardar una tarea, se muestran iconos de acción para la tarea. Puede utilizar los iconos de acción para cambiar el estado de la tarea durante un despliegue. Todas las tareas tienen el icono de acción **Omitir**. Se muestran otros iconos, como por ejemplo **Iniciar**, cuando el contexto resulta adecuado.

![](images/deploy-plan-intro.png "Plan de despliegue típico")

Figura 1. Plan de despliegue simple con tareas y botones de acción

Cada tarea de un plan de despliegue está contenida en una fila distinta. La información que se muestra para cada tarea se describe en la tabla siguiente.

### Tabla 1. Propiedades de tareas

| Propiedad
| Descripción  |
| ------------------ | ------------------ |
| Nombre |Nombre de tarea
|
| Tipo|Tipo de tarea: manual, UrbanCode Deploy, Retrasada, Cabecera|             
| Estado |Estado de la tarea: No iniciada, completa, error, omitida, no aplicable |
| Propietario |Persona a la que se asigna la tarea |
| Hora de inicio |Hora de inicio y hora de inicio prevista en función del inicio planificado, o duración estimada de otras tareas              |
| Hora final |Hora en la que se ha resuelto la tarea |
| Duración|Periodo de tiempo transcurrido entre el inicio de la tarea y la resolución de la tarea (en minutos) |
| Dependencias |Indica el número de tareas que son requisitos previos para la tarea y de los que depende. |

---
Después de que las tareas se hayan añadido al plan de despliegue, podrá gestionarlas de varias maneras:
Para mover una tarea, pulse en cualquier lugar en la tarea y arrástrela a una nueva ubicación.

Para copiar una tarea o grupo, seleccione la tarea y pulse **Copiar** <img class="inline" src="images/copy-group.png"  alt="botón copiar"> y, a continuación, coloque el cursor donde desea insertar la tarea copiada y pulse **Pegar** <img class="inline" src="images/paste-group.png"  alt="botón pegar">. 

Para cortar una tarea o grupo de un plan de despliegue, seleccione la tarea y pulse **Cortar** <img class="inline" src="images/cut-group.png" alt="botón cortar">.

Para suprimir una tarea, seleccione la tarea y pulse **Suprimir** <img class="inline" src="images/trash-group.png" alt="botón suprimir">. La tarea se elimina del plan de despliegue.

## Creación de tareas de UrbanCode Deploy
{: #tasks_UDTasks}

Las tareas de UrbanCode Deploy gestionan aplicaciones de UrbanCode Deploy. Cuando se ejecuta una tarea de UrbanCode Deploy, se ejecuta la aplicación asociada de UrbanCode Deploy utilizando el proceso, la versión y el entorno que la tarea especifica. Puede establecer la versión y el entorno en el tiempo de diseño, o bien, esperar y seleccionarlos en el tiempo de ejecución. 

Durante los despliegues, las tareas de UrbanCode Deploy se indican de forma automática cuando son elegibles para ello.    

**Importante** Las aplicaciones pasan a estar disponibles después de que {{site.data.keyword.uccr_short}} se haya integrado con UrbanCode Deploy. 
Las aplicaciones que están disponibles para un plan de despliegue dependen del equipo al que se le ha asignado el plan. Las aplicaciones que gestiona el equipo en UrbanCode Deploy también están disponibles en {{site.data.keyword.uccr_short}}. 

Complete las tareas siguientes para crear una tarea de UrbanCode Deploy. 

1. En la página Detalles del plan de despliegue, pulse **Crear tarea**. Si desea insertar una tarea en una posición específica en el plan, seleccione la tarea anterior utilizando **Crear tarea**. La nueva tarea se inserta por encima de la tarea seleccionada.

1. En el recuadro de diálogo Crear Tarea, en la lista **Tipo**, seleccione **UrbanCode Deploy**. 

1. En el campo **Nombre**, escriba un nombre para la tarea.


3. En el campo **Duración (minutos)**, especifique el número de minutos que espera que durará la tarea hasta que se haya completado. La duración estimada se utiliza para calcular los tiempos de despliegue previstos.

3. En la lista **Etiquetas**, adjunte una etiqueta a la tarea. Puede seleccionar varios códigos. Para crear una etiqueta, escriba el nombre de la etiqueta en campo de texto de la lista.

3. En la lista **Nombre de aplicación**, seleccione una aplicación.

3. En la lista **Proceso**, seleccione un proceso de aplicación. Están disponibles los procesos que pertenecen a la aplicación UrbanCode Deploy. 

3. En la lista **Entorno**, seleccione un entorno de aplicación. Están disponibles los entornos que pertenecen a la aplicación UrbanCode Deploy. Para posponer la selección de un entorno hasta que esté listo para ejecutar el despliegue, seleccione **Utilizar el separador de versión**.

3. En la lista de **Versión**, seleccione una versión de aplicación. Las versiones hacen referencia a instantáneas de aplicación de IBM UrbanCode Deploy. Están disponibles versiones que pertenecen a la aplicación seleccionada. Para posponer la selección de una versión, seleccione **Utilizar separador de versión**. Si el proceso de la aplicación no requiere una versión, seleccione **Sin versión**. Podría seleccionar esta última opción si está ejecutando procesos de configuración que no requieren componentes.

3. En la lista **Grupos y usuarios asignados**, asigne la tarea a un usuario o grupo. El usuario asignado ejecuta la tarea durante el despliegue.

3. En la lista **Propietario**, seleccione el propietario de la tarea. El propietario predeterminado es el usuario que ha creado la tarea. La lista **Propietario** se muestra después de que la tarea se asigne a un usuario o grupo.    

5. Pulse **Guardar**. La tarea se inserta en el plan de despliegue.

Después de que se haya creado la tarea, el separador **Versión** del plan se actualiza con información sobre la aplicación asignada a la tarea. Si ha seleccionado **Utilizar separador de versión** para la versión y el entorno de la aplicación, utilice el separador Versión para establecer las opciones antes de ejecutar el despliegue. 

## Creación de tareas manuales
{: #tasks_manual}

Normalmente, las tareas manuales representan una actividad asociada con un release de software que tiene un punto de partida, un punto final y una duración que se puede medir.

Complete las tareas siguientes para crear una tarea manual:

1. En la página Detalles del plan de despliegue, pulse **Crear tarea**. Si desea insertar una tarea en una posición específica en el plan, seleccione la tarea anterior utilizando **Crear tarea**. La nueva tarea se inserta por encima de la tarea seleccionada. 

1. En el recuadro de diálogo Crear tarea, en la lista **Tipo**, seleccione **Manual**.

1. En el campo **Nombre**, escriba un nombre para la tarea.


3. En el campo **Duración (minutos)**, especifique el número de minutos que espera que durará la tarea hasta que se haya completado. La duración estimada se utiliza para calcular los tiempos de despliegue previstos.

3. En la lista **Etiquetas**, adjunte una etiqueta a la tarea. Puede seleccionar varios códigos. Para crear una etiqueta, escriba el nombre de la etiqueta en campo de texto de la lista.

3. En la lista **Grupos y usuarios asignados**, asigne la tarea a un usuario o grupo. El usuario asignado ejecuta la tarea durante el despliegue.

3. En la lista **Propietario**, seleccione el propietario de la tarea. El propietario predeterminado es el usuario que ha creado la tarea. La lista **Propietario** se muestra después de que la tarea se asigne a un usuario o grupo.    

5. Pulse **Guardar**. La tarea se inserta en el plan de despliegue.

## Creación de tareas retrasadas
{: #tasks_delayed}

Las tareas de tipo retrasadas representan hitos o sucesos críticos durante un despliegue. Con las tareas retrasadas, puede asegurarse de que las tareas importantes se inician a la hora prevista. Normalmente, las tareas retrasadas constituyen requisitos previos para otras tareas importantes.

Una tarea retrasada se inicia cuando resulta adecuada su ejecución y finaliza a una hora especificada por el usuario. Una tarea retrasada tiene un estado de `En curso` hasta que alcanza su tiempo para el que fue planificada, cuando cambia su estado a `Completada`.  Cuando se completa una tarea retrasada, las tareas automáticas que dependen de ella, se empiezan a ejecutar. 

Complete las tareas siguientes para crear una tarea retrasada: 

1. En la página Detalles del plan de despliegue, pulse **Crear tarea**. Si desea insertar una tarea en una posición específica en el plan, seleccione la tarea anterior utilizando **Crear tarea**. La nueva tarea se inserta por encima de la tarea seleccionada.

1. En el recuadro de diálogo Crear tarea, en la lista **Tipo**, seleccione **Retrasada**.

1. En el campo **Nombre**, escriba un nombre para la tarea.


3. En el campo **Hora**, escriba o seleccione la hora a la que se completará la tarea.

3. En el campo **Huso horario**, seleccione el huso horario para el valor que se especifica en el campo **Hora**.    

5. Pulse **Guardar**. La tarea se inserta en el plan de despliegue.

## Creación de tareas de cabecera
{: #tasks_header}

Las tareas de cabecera representan elementos de la organización que puede añadir a los planes de despliegue. Si crea un grupo de tareas, puede identificar el grupo con una tarea de cabecera. Las tareas de cabecera pueden tener dependencias, como cualquier otra tarea.

Cuando se importa un plan de despliegue desde IBM UrbanCode Release, las tareas de segmentos se delimitan mediante tareas de Iniciar de segmento y Finalizar de segmento de tipo nota. Las dependencias de los segmentos se representan mediante dependencias para las tareas Finalizar segmento. 

Para crear una tarea de cabecera, siga los pasos siguientes:

1. En la página Detalles del plan de despliegue, pulse **Crear tarea**. Si desea insertar una tarea en una posición específica en el plan, seleccione la tarea anterior utilizando **Crear tarea**. La nueva tarea se inserta por encima de la tarea seleccionada. 

1. En el recuadro de diálogo Crear tarea, en la lista **Tipo**, seleccione **Cabecera**.

1. En el campo **Nombre**, escriba un nombre para la tarea.
El nombre puede representar un nombre de grupo de tareas.

3. En el campo **Descripción**, especifique o pegue una descripción. Especifique en el campo una nota, un recordatorio o cualquier otra instrucción. 

5. Pulse **Guardar**. La tarea se inserta en el plan de despliegue.

## Creación de tareas de conducto de Continuous Delivery
{: #tasks_pipelineCD}

Los conductos de {{site.data.keyword.contdelivery_full}} automatizan los flujos de trabajo de DevOps. Un conducto representa una secuencia de etapas que recuperan entradas y ejecutan trabajos. 
Los conductos de {{site.data.keyword.contdelivery_short}} se gestionan con tareas de conducto. Las tareas de conducto de Continuous Delivery son tareas automáticas que se ejecutan tan pronto como son elegibles para ello. 

Para crear una tarea de Continuous Delivery, siga los pasos siguientes:

1. En la página Detalles del plan de despliegue, pulse **Crear tarea**. Si desea insertar una tarea en una posición específica en el plan, seleccione la tarea antes de utilizar la acción **Crear tarea**. La nueva tarea se inserta después de la tarea seleccionada.

1. En el recuadro de diálogo Crear tarea, en la lista **Tipo**, seleccione **Conducto de Continuous Delivery**.

1. En el campo **Nombre**, escriba un nombre para la tarea.


3. En el campo **Descripción**, especifique o pegue una descripción. Especifique en el campo una nota, un recordatorio o cualquier otra instrucción. 

3. En el campo **Conducto**, especifique o seleccione el conducto. 

3. En el campo **Nombre de etapa**, especifique o seleccione el nombre de la etapa. Estarán disponibles las etapas definidas para el conducto seleccionado. 

3. En la lista **Etiquetas**, adjunte una etiqueta a la tarea. Puede seleccionar varios códigos. Para crear una etiqueta, escriba el nombre de la etiqueta en campo de texto de la lista.

3. En la lista **Grupos y usuarios asignados**, asigne la tarea a un usuario o grupo. El usuario asignado ejecuta la tarea durante el despliegue.

3. En la lista **Propietario**, seleccione el propietario de la tarea. El propietario predeterminado es el usuario que ha creado la tarea. La lista **Propietario** se muestra después de que la tarea se asigne a un usuario o grupo.    

5. Pulse **Guardar**. La tarea se inserta en el plan de despliegue.

Cuando una tarea de conducto de Continuous Delivery se ejecuta, ejecuta los trabajos en la etapa especificada del conducto seleccionado. 

## Creación de tareas de correo electrónico
{: #tasks_email}

Cuando se ejecuta una tarea de correo electrónico, se envía un mensaje de correo electrónico. Cuando cree la tarea, especifique el mensaje y los destinatarios del correo electrónico. 
Las tareas de correo electrónico son automáticas y se ejecutan tan pronto como son elegibles para ello. 

Para crear una tarea de correo electrónico, siga los pasos siguientes:

1. En la página Detalles del plan de despliegue, pulse **Crear tarea**. Si desea insertar una tarea en una posición específica en el plan, seleccione la tarea antes de utilizar la acción **Crear tarea**. La nueva tarea se inserta después de la tarea seleccionada.

1. En el recuadro de diálogo Crear tarea, en la lista **Tipo**, seleccione **Correo electrónico**.

1. En el campo **Nombre**, escriba un nombre para la tarea.


3. En el campo **Destinatarios**, especifique o seleccione el destinatario del correo electrónico. La lista de destinatarios disponibles incluye usuarios y grupos que pertenecen a su equipo. También puede escribir las direcciones de correo electrónico otros destinatarios que no pertenecen a su equipo. Puede
especificar varios destinatarios.

3. En el campo **Asunto de correo electrónico**, especifique el tema del correo electrónico. 

3. En el campo **Mensaje de correo electrónico**, especifique o pegue el mensaje de correo electrónico. 

5. Pulse **Guardar**. La tarea se inserta en el plan de despliegue.

Cuando la tarea se ejecuta, los destinatarios recibirán un correo de **IBM Continuous Release** con el asunto que especificó al crear la tarea. 

## Creación de tareas de ejecución de otro plan
{: #tasks_runAnother}

Una tarea de ejecución de otro plan ejecuta un despliegue de otro plan de despliegue. El plan de destino se debe crear a partir de una plantilla. Tanto la plantilla como el plan de destino deben estar en el mismo suceso del release que el plan con la tarea de ejecutar otro plan. 

Tenga en cuenta que se trata de un tipo de tarea experimental.

Para crear una tarea de ejecutar otro plan, siga los pasos siguientes:

1. En la página Detalles del plan de despliegue, pulse **Crear tarea**. Si desea insertar una tarea en una posición específica en el plan, seleccione la tarea antes de utilizar la acción **Crear tarea**. La nueva tarea se inserta después de la tarea seleccionada.

1. En el recuadro de diálogo Crear tarea, en la lista **Tipo**, seleccione **Ejecutar otro plan**.

1. En el campo **Nombre**, escriba un nombre para la tarea.


3. En la lista **Nombre de plantilla de plan**, seleccione una plantilla de plan de despliegue. La plantilla se debe encontrar en el mismo suceso del release que el plan padre de la tarea. 

3. En la lista **Etiquetas**, adjunte una etiqueta a la tarea. Puede seleccionar varios códigos. Para crear una etiqueta, escriba el nombre de la etiqueta en el recuadro de texto. 

5. Pulse **Guardar**. La tarea se inserta en el plan de despliegue.

Cuando la tarea se ejecuta, se inicia un despliegue del plan que se ha creado a partir de la plantilla seleccionada y en el mismo suceso del release. Si a partir de la plantilla se han creado varios planes en el suceso del release, se empezarán los despliegues de todos ellos. Mientras se ejecutan los otros despliegues, la tarea de ejecución de otro plan proporciona la información de estado. Amplíe la tarea para ver la información de estado. Puede abrir otros despliegues utilizando los enlaces en la tarea. Mientras se ejecutan los otros despliegues, la tarea de ejecutar otro plan tiene un estado de **En curso**.

## Creación de tareas de Slack
{: #tasks_slack}

Una tarea de Slack envía una mensaje un canal Slack cuando se ejecuta. El mensaje puede contener texto e hiperenlaces. Una tarea de Slack empieza tan pronto como es elegible para ello. 

Para crear una tarea de Slack, siga los pasos siguientes:

1. En la página Detalles del plan de despliegue, pulse **Crear tarea**. Si desea insertar una tarea en una posición específica en el plan, seleccione la tarea antes de utilizar la acción **Crear tarea**. La nueva tarea se inserta después de la tarea seleccionada.

1. En el recuadro de diálogo Crear tarea, en la lista **Tipo**, seleccione **Slack**.

1. En el campo **Nombre**, escriba un nombre para la tarea.


3. En el campo **URL de webhook**, especifique el URL del canal Slack donde desea entregar el mensaje como, por ejemplo, `https://hooks.slack.com/services/my_webhook`.

3. En el recuadro **Mensaje**, especifique el cuerpo del mensaje. El mensaje puede contener texto e hiperenlaces. 

3. En el campo **Duración (minutos)**, especifique el número de minutos que espera que durará la tarea hasta que se haya completado. La duración estimada se utiliza para calcular los tiempos de despliegue previstos.

3. En la lista **Etiquetas**, adjunte una etiqueta a la tarea. Puede seleccionar varios códigos. Para crear una etiqueta, escriba el nombre de la etiqueta en el recuadro de texto. 

3. En la lista **Grupos y usuarios asignados**, asigne la tarea a un usuario o grupo. El usuario asignado ejecuta la tarea durante el despliegue.

5. Pulse **Guardar**. La tarea se inserta en el plan de despliegue.

Cuando la tarea se ejecuta, se envía el mensaje definido en el campo Mensaje al canal Slack especificado en el campo URL de webhook. 

## Gestión de grupos de tareas
{: #tasks_groups}

Puede combinar dos o más tareas en un grupo de tareas. Cuando se crea un grupo, se define el patrón de ejecución del grupo, secuencial o en paralelo. Las tareas en un grupo con un patrón de ejecución en paralelo se pueden ejecutar en cualquier orden, a no ser que haya dependencias, y de forma simultánea. Las tareas en los grupos de ejecución secuencial se llevan a cabo de forma ordenada en la lista, empezando por la tarea que está primera o al principio. 

Puede insertar grupos dentro de otros grupos. Puede insertar un grupo de patrón secuencial dentro de un grupo de patrón en paralelo y viceversa. Sin embargo, no es posible incluir un grupo con un patrón de ejecución secuencial con otro grupo con un patrón de ejecución secuencial, o un grupo con un patrón de ejecución en paralelo con otro grupo con un patrón de ejecución en paralelo.     

Complete los pasos siguientes para crear un grupo de tareas.

1. En la página Detalle del plan de despliegue, seleccione dos o más tareas.

1. Dependiendo del tipo de grupo que desee crear, realice uno de los pasos siguientes:

  <ul>
  <li>Para crear un grupo de ejecución en paralelo, pulse el botón **Paralelo** <img class="inline" src="images/para-icon.png"  alt="botón de grupo de ejecución en paralelo">. Si no se puede crear un grupo de ejecución en paralelo con las tareas seleccionadas, el botón aparece inhabilitado. Por ejemplo, no podría crear un grupo de ejecución en paralelo si todas las tareas seleccionadas ya se encontrasen en un grupo de ejecución en paralelo.   </li>
  <li>Para crear un grupo de ejecución secuencial, pulse el botón **Secuencial** <img class="inline" src="images/seq-icon.png"  alt="botón de grupo secuencial">.
  </li>
  </ul>

Se forma el grupo y se añade una **barra de selección de grupo** al plan de despliegue. Si selecciona tareas que no son contiguas, las tareas formarán una lista empezando por la tarea seleccionada que esté al principio de todo. 

En la figura siguiente se muestra un grupo de ejecución en paralelo. La **barra de selección de grupo** identifica al tipo de grupo: paralelo <img class="inline" src="images/para-select.png"  alt="seleccionar grupo de ejecución en paralelo"> o secuencial <img class="inline" src="images/seq-select.png"  alt="botón de grupo de ejecución secuencial">. 

![](images/group-select.png "Plan de despliegue típico")

Figura 2. Grupo de ejecución en paralelo

Para mover un grupo, seleccione la **barra de selección de grupo** o pulse en cualquier parte en el grupo y, a continuación, arrástrelo a una nueva ubicación. 

Para copiar un grupo, seleccione el grupo y pulse **Copiar** <img class="inline" src="images/copy-group.png"  alt="botón copiar"> y, a continuación, coloque el cursor donde desea insertar el grupo copiado y pulse **Pegar** <img class="inline" src="images/paste-group.png"  alt="botón pegar">. 

Para cortar un grupo, seleccione el grupo y pulse **Cortar** <img class="inline" src="images/cut-group.png" alt="botón cortar">.

Para desagrupar un grupo, seleccione el grupo y pulse el icono **Desagrupar** <img class="inline" src="images/ungroup-icon.png"  alt="icono desagrupar"> en la **barra de selección de grupo**. 

Para suprimir tareas en un grupo, seleccione el grupo y pulse **Suprimir** <img class="inline" src="images/trash-group.png"  alt="botón suprimir">. Las tareas se eliminan del plan de despliegue.

## Gestión de etiquetas de tareas
{: #tasks_tags}

Las etiquetas son elementos organizativos que puede añadir a las tareas. Puede filtrar planes de despliegue por etiqueta. Por ejemplo, durante un despliegue a un entorno de producción, es posible que inhabilitar tareas con la etiqueta `DEV_only`, pensada para ser utilizada únicamente en entornos de desarrollo.

Para añadir una etiqueta a una tarea, siga los pasos siguientes: 

1. En la página Detalles de plan de despliegue, seleccione una tarea o un grupo de tareas y, a continuación, pulse **Gestionar etiquetas**  <img class="inline" src="images/task-tag.png"  alt="gestionar etiquetas">. Puede seleccionar varias tareas y grupos.

1. En el recuadro de diálogo Gestionar etiquetas para tareas seleccionadas, en la lista **Etiquetas comunes**, seleccione etiquetas. Puede crear una nueva etiqueta escribiendo un nombre en el recuadro de texto de la lista. 

1. Pulse **Guardar**. 

Las etiquetas se muestran en las filas de las tareas en la página Detalle de plan de despliegue. En la siguiente figura, la tarea **Deploy WAR** tiene asignadas dos etiquetas, `Deployment` y `Critical`.

Las tareas que un plan de despliegue utiliza se visualizan en el separador **Versiones** de la página Detalle de plan de despliegue. Para representar tareas con una etiqueta específica de `No aplicable` para un despliegue, borre la etiqueta. No es posible iniciar tareas con un estado de `No aplicable`.   

![](images/task-tag-labels.png "Plan de despliegue típico")

Figura 3. Dependencias de tarea

## Creación de dependencias de tarea
{: #tasks_dependencies}

Puede hacer que una tarea sea un requisito previo para otras tareas. Si una tarea es un requisito previo, las tareas dependientes no se pueden iniciar, aunque sean aptas de no ser por las dependencias, hasta que se resuelva el requisito previo.

Una tarea puede tener varias tareas dependientes y varias
tareas de requisito previo. Puede definir dependencias para una tarea con cualquier
otra tarea del plan de despliegue. Si embargo, no se pueden crear dependencias circulares. No puede, por ejemplo, hacer que una tarea dependa de otra tarea que su vez depende de la primera tarea. 

Mediante el control de dependencias de tareas puede asegurarse de que los sucesos se producen en el orden previsto.

Siga los siguientes pasos para hacer que una tarea sea un requisito previo de otras tareas: 

1. En la página Detalles de plan de despliegue, seleccione una tarea o grupo de tareas y, a continuación, pulse **Gestionar requisitos previos** <img class="inline" src="images/task-depend.png"  alt="requisito previo de tarea">. Puede seleccionar varias tareas y grupos.

1. En el recuadro de diálogo Gestionar requisitos previos de tareas seleccionadas, en la lista **Tareas de requisito previo para tareas seleccionadas**, seleccione la tarea de requisito previo. 

1. Pulse **Guardar**. 

Las dependencias de las tareas se muestran en la columna **Dependencias** en la página Detalle de plan de despliegue. Las flechas hacia arriba indican requisitos previos; las flechas hacia abajo indican dependencias de tareas.

En la siguiente figura, la primera tarea no tiene requisitos previos y tiene dos tareas que dependen de ella. La segunda tarea tiene una tarea de requisito previo y no tiene tareas que dependen de ella. 

(![](images/plan-w-depend.png "Plan de despliegue típico"))

Figura 4. Dependencias de tareas

Para revisar o modificar dependencias, seleccione la tarea y, a continuación, pulse **Gestionar requisitos previos** <img class="inline" src="images/task-depend.png" alt="requisito previo de tarea">. Utilice el recuadro de diálogo Gestionar requisitos previos de tareas seleccionadas para modificar o eliminar dependencias. 
