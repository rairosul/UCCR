---

copyright:
 years: 2017
lastupdated: "2017-6-22"

  ---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


# Iniciación a Continuous Release (Beta)

{: #gettingstartedtemplate}

El servicio {{site.data.keyword.uccr_full}} en IBM {{site.data.keyword.Bluemix_short}} es una completa solución de gestión de releases. {{site.data.keyword.uccr_short}} permite crear releases y despliegues a todas sus aplicaciones de software en su ciclo de desarrollo.
{:shortdesc}

[Después de crear una instancia](https://console.ng.bluemix.net/catalog/services/continuous-release/){:new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") de {{site.data.keyword.uccr_short}}, elija cómo desea empezar. 

* Empiece **[creando un release y ejecutando un despliegue](#gs_create_plan)** para empezar ahora mismo a crear planes de despliegue. 

* Empiece **[instalando y configurando DevOps Connect](#gs_install_dc)** si desea integrar {{site.data.keyword.uccr_short}} con su instancia de IBM UrbanCode Deploy en su ubicación. Después de configurar una integración, puede utilizar las tareas de Continuous Release para gestionar las aplicaciones de UrbanCode Deploy. 


## Creación de un release y ejecución de un despliegue
{: #gs_create_plan}

1. [Cree un release](/docs/services/UCCR/UCCR_releases.html##releases_create) y asígnelo a uno de los equipos. Cualquier miembro del equipo puede crear planes de despliegue para el release y ejecutar despliegues.

1. Añada un plan de despliegue al release.

  * [Cree el plan](/docs/services/UCCR/UCCR_releases.html#releases_planAdd) y asígnelo al release. 

  * [Añada tareas al plan de despliegue](/docs/services/UCCR/UCCR_tasks.html#tasks_create). Cada tarea se lista en una fila distinta en el plan de despliegue. Intente añadir distintos tipos de tareas: manual, UrbanCode Deploy, conducto de Continuous Delivery, retrasar, correo electrónico y Slack. 

  * Puede modificar la lista de tareas en el plan de varias maneras. Tiene la posibilidad de reubicar tareas, copiarlas y suprimirlas.  

4. Cuando el plan de despliegue esté listo, ejecute el despliegue utilizando el plan de despliegue que ha creado en el paso anterior.

  * [Ejecutará el despliegue resolviendo las tareas en un plan de despliegue](/docs/services/UCCR/UCCR_deployRun.html). Las tareas se resuelven al iniciarlas y, a continuación, cambiando su estado a `Completada`, `Error` u `Omitida`. Después de todas las tareas en el plan de despliegue se hayan resuelto, el despliegue tendrá un estado de Terminado. 

  * Las tareas se pueden iniciar cuando son elegibles para ello. La elegibilidad viene determinada por el patrón de ejecución del plan. De forma predeterminada, el patrón de ejecución del plan es secuencial. Inicialmente, la primera, o que se encuentra en la parte superior, tarea es elegible para ser iniciada. El patrón de ejecución se puede modificar agrupando tareas. Un grupo de tareas puede tener un patrón de ejecución en paralelo, lo que significa que las tareas del grupo se pueden iniciar en cualquier orden y de forma simultánea. Un plan de despliegue puede tener varios grupos y grupos anidados dentro de otros grupos. 

  * Algunas tareas, denominadas tareas automáticas, se inician automáticamente tan pronto como son elegibles para ser ejecutadas. Las tareas de tipo de conducto de Continuous Delivery y UrbanCode Deploy se inician tan pronto como son elegibles, sin ninguna intervención manual. Las tareas automáticas también actualizan su estado sin una intervención manual.  

## Instalación y configuración de DevOps Connect
{: #gs_install_dc}

IBM Bluemix DevOps Connect coordina la comunicación entre su instalación local de IBM UrbanCode Deploy y {{site.data.keyword.uccr_short}}. Después de instalar DevOps Connect, puede crear integraciones que le permiten gestionar UrbanCode Deploy de aplicaciones con tareas de {{site.data.keyword.uccr_short}}. 

**Requisitos previos**

* Para registrar DevOps Connect, debe tener un IBMid. 

* Debe tener [Java Runtime Environment versión 7 o posterior](https://java.com/en/download/){:new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") en el sistema host y de establecer la variable de sistema PATH en su ubicación.

* Necesita una señal de autorización de UrbanCode Deploy.    


1. Instale DevOps Connect y utilícelo para integrar {{site.data.keyword.uccr_short}} con UrbanCode Deploy.

  1.  En {{site.data.keyword.uccr_short}} en la página de la Guía de inicio, pulse **Configuración**.

  1.  En el recuadro de diálogo de Configuración de integración de UrbanCode Deploy, pulse **Descargar** para descargar DevOps Connect. Coloque el archivo JAR en un sistema que tenga acceso a UrbanCode Deploy.

  1.  Con la ayuda del recuadro de diálogo, copie el script de instalación de DevOps Connect. El script contiene el mandato para iniciar DevOps Connect y las credenciales que son necesarias para identificar su servicio {{site.data.keyword.uccr_short}} Bluemix. 

  1.  En el sistema donde ha ubicado DevOps Connect, abra un shell de mandatos y pegue en el mismo el script que ha copiado 

  1.  Ejecute el script. DevOps Connect muestra mensajes de arranque.

2. Registre DevOps Connect.

  1.  Utilice un navegador web para abrir el panel de control de DevOps Connect. El URL predeterminado es `https://localhost:8443`. Para cambiar el URL y aprender sobre otras opciones de arranque, consulte la [Documentación de DevOps Connect](https://developer.ibm.com/urbancode/plugindoc/urbancode-sync/ibm-urbancode-sync-utility/1-2/){:new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")

  1.  En la página de registro, especifique un nombre para la instalación de DevOps Connect. 

  1.  Pulse **Registrar**. La primera vez que acceda a DevOps Connect, se le solicitará registrarse con su IBMid.

  1.  En la página **Iniciar sesión en IBM**, escriba su IBMid y su contraseña y luego pulse **Iniciar sesión**. Debe registrarse cada vez que inicie DevOps Connect.

3. Con DevOps Connect, utilice el plugin IBM UrbanCode Deploy for Cloud Reporting para crear una integración entre {{site.data.keyword.uccr_short}} y UrbanCode Deploy.

    1.  Desde el panel de control de DevOps Connect, pulse **Integraciones** y, a continuación, pulse **Añadir nueva**.

    1.  En el campo **Nombre**, escriba un nombre para la integración. 

    1.  En la lista **Tipo de integración**, seleccione **IBM UrbanCode Deploy for Cloud Reporting**. El plugin IBM UrbanCode Deploy for Cloud Reporting se incluye con DevOps Connect.

    1.  En el campo **URI de servidor**, especifique el URL público del servidor de UrbanCode Deploy. Por ejemplo, `https://my_UCD.example.com:8447`.

    1.  En el campo **Señal de autenticación**, especifique o pegue la señal de autenticación que UrbanCode Deploy generó. 

    1.  En el campo **Correo electrónico de usuario de administración**, especifique su dirección de correo electrónico.

    1.  Pulse **Guardar**. 

4.  Ejecute la integración para confirmar que funciona.

    1.  En la página de integración, pulse **Ejecutar**. DevOps Connect se conecta a la instancia UrbanCode Deploy especificada en el campo **URI de servidor**. DevOps Connect recibe autorización de la señal que se ha pegado en el campo **Señal de autenticación**.

    1.  En {{site.data.keyword.uccr_short}}, confirme que la integración es satisfactoria mediante la creación de una tarea de tipo UrbanCode Deploy. Si puede seleccionar una aplicación UrbanCode Deploy, quiere decir que la integración ha sido satisfactoria. La instancia de {{site.data.keyword.uccr_short}} utiliza los parámetros de arranque e inicio de sesión de DevOps Connect para identificar las aplicaciones de UrbanCode Deploy.   
