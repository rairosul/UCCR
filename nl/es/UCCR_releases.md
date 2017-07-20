---

copyright:
 years: 2017
lastupdated: "2017-6-22"

  ---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Acerca de los releases
{: #releases_overview}

Un release es un contenedor para planes de despliegue, sucesos y etiquetas.

{:shortdesc}

Normalmente, un release contiene planes de despliegue y los sucesos relacionados en un sentido empresarial.
Por ejemplo, los planes de despliegue podrían representar las fases de un ciclo de vida de desarrollo de software como, por ejemplo, el desarrollo, la fase de QA y la producción. Un suceso podría representar, por ejemplo, una indisponibilidad que afectase al release. 

Si añade sucesos a un release, puede utilizar el calendario para filtrar releases y planes de despliegue en la página Releases. 

## Creación de releases
{: #releases_create}

Para crear un release, siga los pasos siguientes:

1. En la página Releases, pulse **Crear release**.

1. En la ventana Crear release, en el campo **Nombre**, especifique un nombre para el release. Se necesita un nombre. 

3. En la lista **Equipo**, seleccione un equipo para gestionar el release. Puede añadir planes de despliegue de otros equipos al suceso de release, no sólo del equipo que gestiona el release. Están disponibles todos los equipos a los que pertenece. Se necesita un equipo. 

3. En el campo **Hora de inicio**, seleccione una fecha y hora de inicio. La fecha y hora de inicio se necesita para todos los releases. 

3. En el campo **Hora de finalización**, seleccione la hora y fecha de finalización. 

3. En la lista **Etiquetas**, seleccione un suceso o una etiqueta. Puede seleccionar varios elementos. Si desea que el suceso aparezca en el calendario, [seleccione un suceso que se cree en la página Configurar calendario](UCCR_events.html#events_tagCreate).

1. Opcionalmente, puede crear una etiqueta escribiendo el nombre de dicha etiqueta en el campo **Etiquetas**. Las etiquetas que crea en la ventana Crear release no se visualizan en el calendario, lo que evitará sobrecargarlo. 

5. Pulse **Guardar**. 

Para visualizar el release en la lista de Actividades, asegúrese de que el rango de fechas está dentro de la hora de inicio y finalización del release.  

Después de que se haya creado el release, añada al mismo planes de despliegue, sucesos y etiquetas. 

## Adición de planes de despliegue a un release
{: #releases_planAdd}

Puede añadir planes de despliegue existentes a un release o crear uno nuevo. 

Para añadir planes de despliegue existentes a un release, lleve a cabo los pasos siguientes:

1. En la página Releases, seleccione el release.

1. En la página Detalles de release, pulse **Crear plan de despliegue**.

1. En la ventana Añadir plan, seleccione los planes que desea añadir al release. En la lista aparecerán los planes planificados de su equipo. 

3. Pulse **Guardar**. 

[Para crear un plan](UCCR_deployPlan.html#plan_create), pulse **Crear plan de despliegue**. Los planes que se crean con la página Detalles de release se asignan al release de forma automática. Cuando se crea un plan de despliegue independiente de un release, puede seleccionar el release al que desea añadir el plan.


## Gestión de versiones
{: #releases_manage}

La página Detalles de release muestra los planes de despliegue que pertenecen al release. Para gestionar un release o los planes de despliegue que le pertenecen, abra la página Detalles de release, y, a continuación, realice una de las siguientes tareas: 
<ul>
<li>Pulse **Editar** para modificar la definición del release. Con esta opción, puede añadir sucesos y etiquetas al suceso de release.
</li>
<li>Seleccione **Editar este plan** para editar un plan de despliegue. Se visualiza la ventana Editar plan de despliegue.
</li>
<li>Seleccione **Replanificar este plan** para cambiar las horas de inicio y finalización planificadas.
</li>
<li>Seleccione **Copiar este plan** para copiar un plan de despliegue. Se añadirá al release una copia del plan seleccionado. </li>
<li>Seleccione **Eliminar del release** para eliminar el plan de despliegue de este release. Los planes que se eliminan de un release no son suprimidos y es posible añadirlos más tarde a otro release.
</li>
</li>
<li>Seleccione **Archivar este plan** para archivar el plan de despliegue. Los planes archivados se pueden restaurar. </li>
</ul>

[Consulte Ejecutar despliegues](UCCR_deployRun.html#deployment_run) para iniciar un despliegue. 

## Archivado y restauración de releases
{: #releases_archiveRelease}

Aunque no puede suprimir un release, puede almacenarlo en el archivo de archivado. Los releases archivados no se visualizan en la página Releases. 

Para archivar un release, siga los pasos siguientes:

1. En la página Releases, seleccione la acción **Archivar** para el release.

1. En la ventana Archivar suceso de release, determine los planes de despliegue que desea archivar seleccionando una de las siguientes opciones: 
<ul>
<li>Seleccione **Archivar todos los planes de despliegue** para archivar el release y todos los planes de despliegue independientemente de su estado.</li>
<li>Seleccione **Archivar planes de despliegue completados únicamente** para archivar el release y solo los planes de despliegue con el estado completado. Los planes de despliegue con otros estados no se archivarán y mantendrán su estado actual.</li>
</ul>

3. Pulse **Archivar**.

Para restaurar un release archivado, efectúe estos pasos:

1. En la página Releases, pulse **Archivado**.

2. En la lista de releases archivados, pulse la acción **Restaurar** para el release. 

Un release restaurado conserva todos sus planes de despliegue originales. 
