# IBM-Cloud-Observability

## APROVISIONAMIENTO DE MONITORING WITH SYSDIG PARA UN HOST UBUNTU 

Monitoring with sysdig es una herramienta de vigilancia que brinda IBM y permite tener supervisión sobre diferentes servicios de IBM CLOUD. En esta guía se explicará el paso a paso para el aprovisionamiento de Monitoring With Sysdig en un Host ubuntu.

### Antes de empezar
1.	Debe contar con una cuenta de IBM Cloud que disponga con los permisos necesarios para el aprovisionamiento de Monitoring With Sysdig. Para más información se recomienda visitar el siguien link:
https://cloud.ibm.com/docs/Monitoring-with-Sysdig?topic=Sysdig-iam.
2.	Instale la CLI de IBM Cloud y el plugin de la CLI de Kubernetes. Para obtener más información, consulte Instalación de la CLI de IBM Cloud.
3.	Cree un servidor ubuntu.
4.	Asegúrese de que a su ID de usuario se le asignen las siguientes políticas de IBM® Cloud Identity and Access Management:
Para obtener más información sobre los roles de IAM de IBM Cloud™ Kubernetes Service, consulte Permisos de acceso de usuario.

### Paso 1: Suministrar una instancia de IBM Cloud Monitoring with Sysdig
En esta guía de aprendizaje de iniciación se ofrecen instrucciones para suministrar una instancia en IBM Cloud Monitoring with Sysdig en la región EE. UU. sur. Para obtener más información sobre las regiones soportadas, consulte el apartado Regiones.
Para suministrar una instancia de IBM Cloud Monitoring with Sysdig mediante la interfaz de usuario de IBM Cloud, siga los pasos siguientes:
1.	Inicie una sesión en su cuenta de IBM Cloud  .
Cuando inicia una sesión con su ID de usuario y su contraseña, se abre la interfaz de usuario de IBM Cloud.
2.	Pulse “Catálogo”. Se abrirá la lista de servicios disponibles en IBM Cloud.
3.	Para filtrar la lista de servicios que se visualiza, seleccione la categoría “Herramientas de desarrollador”.
4.	Pulse el mosaico “IBM Cloud Monitoring with Sysdig”. Se abre el panel de control Observabilidad.
5.	Seleccione “Crear instancia”.
6.	Especifique un nombre para la instancia de servicio.
7.	Seleccione el grupo de recursos “predeterminado”.
Puede suministrar la instancia en cualquier grupo de recursos en el que tenga permisos para crear recursos.
De forma predeterminada, está establecido el grupo de recursos predeterminado (default).
8.	Seleccione el plan de servicio “Prueba”.
De forma predeterminada, se selecciona el plan de Prueba.
Para obtener más información acerca de los otros planes de servicio, consulte Planes de servicio.
9.	Pulse Crear.
Después de suministrar una instancia, se abre el panel de control Observabilidad y se muestran detalles correspondientes a las instancias de Supervisión.
### Paso 2: Configurar el servidor Ubuntu para que envíe métricas a la instancia
Para configurar el servidor Ubuntu para que envíe métricas a la instancia de IBM Cloud Monitoring with Sysdig, debe instalar un agente de Sysdig.
Siga los pasos siguientes desde la línea de comando
Obtenga la clave de acceso de Sysdig.

1.	Obtenga la clave de acceso de Sysdig. 
En IBMCLOUD, haga click sobre el “menú de hamburguesa” y seleccione “observabilidad”.

<p align="center">
  <img width="auto" height="auto" src="https://github.com/javierjimenezm/IBM-Cloud-Observability/blob/master/Monitoring_with_Sysdig_HostUbuntu/Imagenes/Imagne001.PNG">
</p>

2.	Una vez se encuentre dentro de observabilidad, selecciones “Monitoring”, deberá aparecer la instancia que previamente ha sido creada. 
3.	Haga click en los tres puntos y seleccione “Obtain Key”.

![Reference](https://github.com/javierjimenezm/IBM-Cloud-Observability/blob/master/Monitoring_with_Sysdig_HostUbuntu/Imagenes/Imagen002.PNG)

4.	Copie la clave que aparece en pantalla.

5.	Obtenga la URL donde se encuentran los puntos finales de Sysdig, como esta guía está enfocada en el aprovisionamiento de Monitoring With Sysdig en la región de EE.UU sur, la URL dónde se encuentra el punto final de Sysdig es la siguiente: ingest.us-south.monitoring.cloud.ibm.com.
Para más información sobre los puntos finales disponibles por regiones, visite el siguiente enlace: https://cloud.ibm.com/docs/services/Monitoring-with-Sysdig?topic=Sysdig-endpoints&locale=es#endpoints_ingestion

6. Desde la CLI utilizando SSH, despliegue el agente Sysdig en su servidor; para ello habra PowerShell y utilice el siguiente comando para ingresar a IBMCLOUD.

` Ibmcloud login -sso  ` 

