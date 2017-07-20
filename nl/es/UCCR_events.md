---

copyright:
 years: 2017
lastupdated: "2017-6-22"

  ---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Gestión de sucesos y etiquetas
{: #events_overview}

Un suceso representa una actividad relacionada con el release que gestiona con el calendario. 

Una etiqueta es un texto que puede añadir a un release o a un suceso. Las etiquetas sirven para filtrar la lista de actividades en la página Releases. A diferencia de los sucesos, las etiquetas no aparecen en el calendario. 

{:shortdesc}

Los sucesos se organizan en categorías generales que incluyen releases, vacaciones y ventanas de mantenimiento. [Las etiquetas y los sucesos del calendario se asignan a los releases](UCCR_releases.html#releases_overview). Los sucesos se pueden añadir a los releases o utilizarse de forma independiente.   

Cuando se asigna un suceso, se representa en el calendario con el icono apropiado para la categoría de dicho suceso. Puede utilizar los iconos para filtrar y seleccionar releases en la página Releases en una fecha concreta o en un rango de fechas. 

Las etiquetas se asignan a los releases y se pueden utilizar para filtrar en la página Releases. Las etiquetas asignadas aparecen en la página Releases pero no en el calendario. Utilice las etiquetas para evitar sobrecargar el calendario. 

## Filtrado de sucesos de release y planes de despliegue
{: #events_findFilter}

En la página Releases se visualizan los releases, los sucesos y los planes de despliegue que ha creado usted o sus equipos. Desde la página Releases, podrá realizar la mayoría de las actividades relacionadas con un release como, por ejemplo, crear releases y planes de despliegue. 

De forma predeterminada, la página Releases muestra las actividades que se han planificado para los siguientes siete días. Puede filtrar la visualización por tiempo, suceso, etiqueta y estado. Por ejemplo, es posible restringir la visualización a releases que estén planificados para el día siguiente. El rango actual de fechas seleccionadas se visualiza en la barra de acciones.

Para filtrar la página Releases por suceso o etiqueta, seleccione el suceso o la etiqueta en la barra de búsqueda y, a continuación, pulse Intro.

Para filtrar las actividades planificadas por fecha, realice una de las siguientes tareas:
<ul>
<li>Seleccione un valor de la lista **Fechas** en la barra de acciones. Por ejemplo, para visualizar elementos que se han planificado para la próxima semana, seleccione **Próximos 7 días**.</li>
<li>Seleccione en el calendario una fecha o un rango de fechas. Cuando selecciona fechas en el calendario, el valor de **Fechas** en la barra de acciones se establece en **Personalizado**.</li>
</ul>

Se mostrarán las actividades planificadas para las fechas seleccionadas. 

Para filtrar los elementos por estado, seleccione uno de los siguientes filtros:
<ul>
<li>Seleccione **Todo** para visualizar todas las actividades. Muestra todos los releases, los sucesos y los planes de despliegue excepto aquellos que se han archivado. Utilice esta opción para visualizar planes de despliegue no planificados.
</li>
<li>Seleccione **Borrador** para visualizar los planes de despliegue que no tienen un estado de En curso, Completado o Error.
</li>
<li>Seleccione **Planificado** para visualizar los releases, los sucesos y los planes que se han planificado dentro del rango de fechas seleccionado.
</li>
<li>Seleccione **En curso** para visualizar los despliegues que están en curso y que no tienen el estado de Completado o Error.
</li>
<li>Seleccione **Error** parea visualizar los despliegues que tienen un estado de Error. </li>
<li>Seleccione **Completado** para visualizar los despliegues que tienen el estado de Completado.
</li>
</li>
<li>Seleccione **Archivado** para visualizar los releases, los sucesos y los planes de despliegue guardados en el archivo de archivado. Existe la posibilidad de restaurar los elementos archivados.
</li>
<li>Seleccione **Plantillas** para visualizar los planes de despliegue que se guardan como plantillas. Las plantillas sirven para crear planes. Las plantillas se pueden convertir en planes de despliegue.   
</li>
</ul>

## Utilización del calendario
{: #events_calendarManage}

Seleccione los iconos de sucesos del calendario para filtrar la lista de **Actividades**. El aspecto de los iconos varía según la categoría del suceso, lo que facilita su identificación. Las categorías de los sucesos se describen en la siguiente lista: 

<ul>
<li>Los sucesos de release se representan con círculos rellenos de color <img class="inline" src="images/event-icon-release.png"  alt="Icono de suceso de release">.</li>
<li>Los sucesos de mantenimiento e indisponibilidad se representan con círculos con bordes de colores <img class="inline" src="images/event-icon-window.png"  alt="Valores de calendario">.</li></li>
<li>Los sucesos de vacaciones se representan con semicírculos por encima de la fecha <img class="inline" src="images/event-icon-holiday.png"  alt="Valores de calendario">.</li>
</ul>

En la siguiente figura, el suceso de release indicado con el color verde está planificado desde el domingo al martes. El suceso de release indicado con el color azul está planificado para el miércoles. El suceso de mantenimiento está planificado desde el jueves al sábado. El suceso de vacaciones está planificado para el segundo domingo. 

![](images/event-icon-styles2.png "Estilos de icono de suceso predeterminados")

Figura 1. Estilos de icono de suceso predeterminados

Para filtrar la lista **Actividades**, complete una de las siguientes acciones:

<ul>
<li>Pulse una fecha. </li>
<li>Seleccione un rango de fechas. Puede seleccionar un rango de fechas pulsando en una fecha y, a continuación, pulsando otra fecha manteniendo pulsada la tecla de mayúsculas. </li>
</ul>

Se muestran los releases, los sucesos y los despliegues que se han planificado para las fechas seleccionadas. Si una fecha tiene planificada más de un suceso de calendario, la fecha aparece subrayada <img class="inline" src="images/event-icon-twoIcons.png"  alt="Valores de calendario">.

## Creación de tipos de suceso
{: #events_eventTypeCreate}

Además de los tipos de suceso predeterminados, puede crear tipos de suceso para cualquiera de las categorías de suceso. 

Cuando se crea un tipo de suceso, los estilos gráficos se aplican de forma automática al icono asociado. Puede cambiar el estilo del icono después de haber creado un suceso.

Para crear un suceso, siga los pasos siguientes:

1. En la página Releases, pulse **Valores de calendario** <img class="inline" src="images/cal-set.png"  alt="Valores de calendario">.

1. En la página Configurar calendario, pulse **Añadir tipo de suceso** <img class="inline" src="images/event-add.png"  alt="Añadir tipo de suceso"> de la categoría de suceso que desea crear. 

3. En el recuadro de texto, especifique un nombre para el suceso. 

3. Pulse **Guardar**. Tiene la posibilidad de editar y suprimir las distintas etiquetas de suceso. 

## Gestión de tipos de suceso
{: #events_eventEdit}

De forma predeterminada, los estilos de los iconos de suceso se aplican automáticamente y de forma aleatoria de acuerdo a su categoría. 

En la siguiente figura, los estilos de las dos filas superiores se aplican a sucesos en la categoría de sucesos de release, los estilos en la tercera fila se aplican a sucesos de mantenimiento e indisponibilidad y los estilos en la cuenta fila se aplican a las vacaciones. 

![](images/event-styles.png "Plan de despliegue típico")

Figura 2. Estilos de icono de suceso

Para editar un estilo de tipo de suceso, complete los siguientes pasos:

1. En la página Releases, pulse **Valores de calendario**. 

2. En la página Configurar calendario, pulse el icono **Editar** que se encuentra junto al icono de suceso que desea cambiar y, a continuación, pulse **Más**.

3. Seleccione un estilo. Puede seleccionar cualquier estilo independientemente de la categoría.

Para editar un nombre de tipo de suceso, pulse el icono **Editar** que se encuentra junto al nombre del tipo de suceso y, a continuación, edite el nombre.

Para suprimir un tipo de suceso, pulse el icono **Suprimir** situado junto al nombre.

## Importación de releases y sucesos
{: #events_importing}

Tiene la posibilidad de importar sus propios sucesos y releases. Si desea importar elementos, los debe definir en un archivo con valores separados entre comas (CSV). El formato de archivo CSV es un formato estándar que se utiliza en el intercambio de datos entre aplicaciones. En los archivos CSV, cada campo en un registro está separado por comas, y cada registro se encuentra en una fila distinta. Utilice el formato siguiente para definir sucesos y releases:  

`name*,description,start*,end,team*,tag`

Los siguientes campos son obligatorios:

`name,start,team`

Por ejemplo, `Holiday,New Years Day,1/1/18,1/1/18,my_team,National Holiday` 

Para importar sucesos y releases, siga estos pasos:

1. En la página Releases, pulse **Importar** <img class="inline" src="images/import-events.png" alt="Sucesos de importación">.

2. En el recuadro de diálogo Importar desde CSV, seleccione el archivo CSV que contiene los releases y los sucesos y, a continuación, pulse **Importar sucesos**. El recuadro de diálogo proporciona un enlace en el que puede descargar un archivo de sucesos CSV de ejemplo. 

Si la importación es correcta, los releases y los sucesos se muestran en la página Releases. Si el valor en el campo **tag** contiene un tipo de suceso definido con anterioridad, el suceso se visualiza en el calendario. De lo contrario, el valor en el **tag** se trata como una etiqueta.

## Creación de etiquetas
{: #events_tagManage}

[Es posible crear etiquetas en la página Crear release al crear o modificar un release. ](UCCR_releases.html#releases_create) Las etiquetas se muestran en la página Releases junto con el propietario del release. A pesar de que las etiquetas no aparecen en el calendario, puede utilizarlas para filtrar los elementos que se visualizan en la página Releases. 
