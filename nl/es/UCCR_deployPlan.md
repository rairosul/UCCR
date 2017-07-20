---

copyright:
 years: 2017
lastupdated: "2017-6-22"

  ---


<!-- Common attributes used in the template are defined as follows: -->
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Gestión de planes de despliegue 
{: #plan_overview}

Un plan de despliegue es un contenedor de tareas. Las tareas definen las actividades que su equipo ejecuta para completar un despliegue de software.

{:shortdesc}

Puede crear un plan de despliegue asignando un equipo para gestionarlo y, a continuación, añadiendo tareas al mismo. Los miembros del equipo añaden tareas al plan y ejecutan tareas durante los despliegues. El equipo que se encarga de la gestión también determina las aplicaciones de IBM UrbanCode Deploy que estarán disponibles. Después de que se haya configurado una integración con DevOps Connect, todas las aplicaciones gestionadas por el equipo en IBM UrbanCode Deploy estarán disponibles en {{site.data.keyword.uccr_short}}.  

Las tareas definen las actividades que el equipo lleva a cabo para completar el despliegue. Puede crear tareas nuevas, copiar tareas de otros planes de despliegue o importar tareas desde archivos CSV. Cuando esté satisfecho con el plan, puede planificar un despliegue. También puede ejecutar un despliegue en cualquier momento iniciando una de las tareas del plan.

Las tareas se visualizan en filas individuales en los planes de despliegue. Cada fila contiene información que identifica la tarea y proporciona su estado. Cada fila también contiene iconos de acción que se utilizan durante los despliegues como, por ejemplo, la tarea **Iniciar** o la tarea **Omitir**. 

De forma predeterminada, las tareas se ejecutan secuencialmente empezando por la primera tarea, o superior, en el plan. Después de que termine la primer tarea, la segunda tarea es elegible para ser ejecutada y así sucesivamente. El orden en el que las tareas pasan a estar elegibles para ser ejecutadas se denomina el orden de ejecución.

El orden de ejecución se puede modificar combinando tareas en grupos. [Cuando se crea un grupo](/docs/services/UCCR/UCCR_tasks.html#tasks_groups), se establece el patrón de ejecución, que puede ser un patrón de ejecución secuencial o en paralelo. Si un grupo tiene un patrón de ejecución secuencial, sus tareas se ejecutan de forma secuencial, empezando por la primera tarea. El patrón de ejecución predeterminado de un plan de despliegue es el secuencial. Si un grupo tiene un patrón de ejecución en paralelo, las tareas en el grupo se pueden iniciar en cualquier orden y de forma simultánea. Si un plan consta por completo de tareas paralelas, puede iniciar cualquier tarea independientemente de su posición en la lista. 

La elegibilidad de las tareas puede verse afectada por las dependencias de las tareas. [Si una tarea tiene requisitos previos](/docs/services/UCCR/UCCR_tasks.html#tasks_dependencies), no puede iniciarse, incluso si por lo contrario fuese elegible, hasta que no se hayan resuelto todos sus requisitos previos.   

Algunas tareas se inician automáticamente tan pronto como son elegibles para se ejecutadas, mientras que otras tareas se deben iniciar de forma manual. El que una tarea se inicie de forma automática depende de su tipo. Las tareas manuales, como el nombre implica, se inician manualmente. Las tareas de UrbanCode Deploy y de tipo retrasadas se inician de forma automática tan pronto como son elegibles para ello. 

Las tareas elegibles visualizan un botón de **Iniciar tarea**. Para iniciar un despliegue, inicie una de las tareas elegibles del plan. Los despliegues planificados se inician automáticamente en la hora planificada si hay una tarea elegible de un tipo que sea posible iniciar de forma automática como, por ejemplo, una tarea de UrbanCode Deploy. 

## Creación de planes de despliegue 
{: #plan_create}
Tiene la posibilidad de empezar con un plan vacío, sin tareas definidas, o bien, copiar un plan existente. También puede empezar a partir de una plantilla de plan. Cuando se copia un plan o se utiliza una plantilla, muchas tareas ya están definidas.

Complete los pasos siguientes para crear un plan de despliegue:

1. En la página Releases o en la página Detalles de release, pulse **Crear plan de despliegue**.

2. En la ventana Crear plan de despliegue, en la lista de **Plantilla**, especifique la plantilla en la que desea basar el plan. El valor predeterminado es **None**. 

2. En el campo **Nombre de plan**, especifique el nombre del plan. 

3. En la lista **Equipo**, seleccione un equipo para gestionar el plan. Todos los equipos a los que pertenece estarán disponibles. Los miembros del equipo pueden modificar el plan y gestionar las tareas. Las aplicaciones de UrbanCode Deploy que el equipo gestiona en UrbanCode Deploy están disponibles para ser asignadas a tareas de tipo UrbanCode Deploy. 

4. Para planificar un despliegue para el plan, pulse **Hora de inicio** y, a continuación, seleccione una hora y fecha para el despliegue. Los despliegues planificados se inician de forma automática a la hora planificada si el plan contiene tareas automáticas elegibles. Puede planificar un despliegue en cualquier momento del futuro. 

5. En la lista **Release**, seleccione el release al que desee añadir el plan. Estarán disponibles los releases que pertenecen a uno de sus equipos. Si selecciona un release, el plan de despliegue se muestra en la página Detalles de release.

6. Pulse **Guardar**. Si ha creado el plan en la página Detalles de release, el plan es parte del release seleccionado.

Después de guardar el plan, pulse **Editar** para modificar los detalles del plan.

## Tareas de importación para planes de despliegue
{: #plan_importTasks}

Tiene la posibilidad de importar tareas definidas en archivos con valores separados por comas (CSV) en un plan de despliegue. Puede utilizar archivos CSV que se hayan exportado desde IBM UrbanCode Release u otra aplicación capaz de crear archivos CSV. 

**Importante:** Cuando se importan tareas, las tareas que ya estén definidas en el plan de despliegue se sobrescribirán y se sustituirán por las tareas en el archivo CSV.

Complete los pasos siguientes para importar las tareas en un plan de despliegue.

1. En la página Detalles del plan de despliegue, pulse **Importar tarea**. 

3. En el diálogo Importar tareas, pulse **Elegir archivo** y, a continuación, seleccione el archivo CSV. También puede arrastrar un archivo en el campo **Elegir archivo**. 

6. Pulse **Importar**. Estas tareas se añaden al plan de despliegue. Si el proceso de importación no es satisfactorio, pulse **Ver informe** para visualizar el registro de errores.

Al importar un plan de despliegue de IBM UrbanCode Release, los segmentos se convierten en grupos con el mismo patrón de ejecución que en los segmentos originales. Las tareas de segmentos se delimitan mediante tareas de Iniciar de segmento y Finalizar de segmento de tipo nota. Las dependencias de las tareas se conservan durante la importación. Las dependencias de los segmentos se representan mediante dependencias para las tareas Finalizar segmento. 

En la tabla siguiente se muestran los campos que definen una tarea en un plan de despliegue de IBM UrbanCode Release. La primera fila del archivo CSV contiene las cabeceras de las columnas, que corresponden a la columna **Campo** de la tabla. Las filas después de la primera fila contienen los datos de las tareas, una tarea por fila. El orden de las columnas no importa.

Para obtener más información acerca de los planes de despliegue exportados desde IBM UrbanCode Release, descargue el archivo `SamplePlan.csv` desde el diálogo Importar tareas. 

Si está creando tareas en un archivo CSV, debe incluir los campos necesarios que se identifican mediante el carácter de asterisco (*) en la tabla siguiente:


| Campo
| Descripción  |
| ------------------ |------------------|
|segmentName*                 |Nombre del segmento.
Campo
necesario. |                                                    
|name*|Nombre de la tarea de despliegue.
Campo
necesario. |                                                                
|type*|Tipo de tarea. Los valores posibles son `note`, `waitfortimetask`, `ucdtask` o `manual`. Durante la importación, si el campo contiene un valor no reconocido, a la tarea se asigna el tipo manual.|
|descripción
|Descripción del plan de despliegue.
|                                                                                                    
|property:processId|ID de proceso en IBM UrbanCode Deploy que corresponde a la tarea.|
|property:task-environments   |Entornos de aplicación disponibles para la tarea.|
|property:mailRecipients|Direcciones de correo electrónico de los usuarios que reciben mensajes de correo electrónico cuando se envían notificaciones.|
|taskTagNames|Nombres de las etiquetas que están asociadas a la tarea.|
|taskPrequisiteIds         |Lista separada por comas de ID de tareas que deben completarse antes de que se pueda iniciar esta tarea. |
|segmentPrerequisitelds|Lista separada por comas de ID de segmentos de los que depende el segmento actual. |
|taskPrequisiteNames|Lista separada por comas de nombres de tareas que deben completarse antes de que se pueda iniciar esta tarea. |
|segmentPrerequisiteNames|Lista separada por comas de nombres de segmentos de los que depende el segmento actual. |
|assignedUserEmail                |Dirección de correo electrónico del usuario al que se le asigna la tarea actual.|
|executorGroup                |Grupo de usuarios asignados a la tarea actual. |
|segmentPattern|Patrón de ejecución del segmento seleccionado. |

{: caption="Tabla 1. Campos de plan de despliegue de IBM UrbanCode Release" caption-side="top"}

## Copia y promoción de planes de despliegue
{: #plan_copyPromote}

Puede duplicar los planes de despliegue si los promociona o copia. El estado de un plan copiado o promocionado es de `borrador` incluso si el plan original tiene un estado de `hecho` o `en curso`.  

Para copiar un plan, utilice la acción **Copiar este plan** en la página Plan de despliegue. Cuando se copia un plan, en la página Plan de despliegue se inserta un plan nuevo con el nombre "Copia de `nombre_plan`".  El plan copiado contiene todas las tareas definidas en el plan original. Si en el plan hay tareas de UrbanCode Deploy, las aplicaciones, las versiones y los entornos seleccionados en el original también se seleccionan en el plan copiado. Las aplicaciones, las versiones, y los entornos se visualizan en el separador **Versiones** en la página Plan de despliegue. 

Para promocionar un plan, utilice la acción **Promocionar este plan** en la página Plan de despliegue. Cuando se promociona un plan, en la página Plan de despliegue se inserta un plan nuevo con el nombre "Promoción de `nombre_plan`". El plan promocionado contiene todas las tareas definidas en el plan original. Si en el plan hay tareas de UrbanCode Deploy, las aplicaciones y las versiones seleccionados en el original también se seleccionan en el plan promocionado. La diferencia entre los planes copiados y los promocionados es que las versiones de las aplicaciones no se establecen en los planes promocionados. 

## Gestión de plantilla de plan
{: #plan_templates}

Existe la posibilidad de convertir planes de despliegue en plantillas de planes de despliegue. 

Para crear una plantilla, utilice la acción **Crear plantilla de este plan** en la página Plan de despliegue. Cuando se crea una plantilla, en la página Plan de despliegue se inserta un plan nuevo con el nombre "Copia de nombre_plan". Es estado de una plantilla es `plantilla` incluso si el plan original tiene un estado de `hecho` o `en curso`.  La plantilla contiene todas las tareas definidas en el plan original. Si en el plan hay tareas de UrbanCode Deploy, las aplicaciones seleccionadas en el original también se seleccionan en la plantilla. 

No puede ejecutar despliegues con plantillas. Para utilizar una plantilla para un despliegue, primero copie o promocione un plan y, a continuación, utilice el plan copiado o promocionado. 

## Activación de planes de despliegue 
{: #plan_arch}

Cuando coloca un plan de despliegue en un archivador, el plan pasa a tener un estado de `Archivado` y deja de visualizarse en la página Plan de despliegue a no ser que utilice el filtro de **Archivo**. 

Los planes de despliegue que se encuentran en el archivador se pueden restaurar en el estado de `borrador`. Un plan de despliegue no puede suprimir de forma definitiva. 

## Revertir y restaurar
{: #plan_history}

Para cada plan de despliegue se mantiene un historial de cambios y revisiones. Puede visualizar las revisiones en el separador **Historial de cambios** en la página Detalle de plan de despliegue. 

Para volver a una versión del plan anterior, utilice la acción **Restaurar** <img class="inline" src="images/restore-icon.png"  alt="acción restaurar"> en la versión que desea restaurar. 
El plan se restaura a la versión seleccionada.   

## Estimación de tiempos de despliegue
{: #plan_durationEst}

Antes de iniciar un despliegue, puede efectuar una estimación su duración. Para calcular los tiempos de duración, utilice la acción **Calcular tiempo de tarea** en la página Detalle de plan de despliegue. El tiempo que se muestra representa el instante en el que finalizará el despliegue si lo empieza ahora mismo. 
