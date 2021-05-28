---
title: "Diseño Detallado"
date: 2021-05-20T10:31:03-05:00
layout: "single"
---

Corresponde al diseño del o los componentes de servicio, service component, que realiza el servicio a partir de la implementación de su interfaz. 

{{< prueba url="images/bill-payment-schedules-v1/flujo_apiconnect.png" >}}

### Componente de servicio Bill - Payment - Schedules operation delete
En el componente del servicio, se implementa la lógica del servicio a través de una API.

En la siguiente tabla se relaciona el mecanismo de acceso y la interfaz del componente: 
- **Protocolo**: https
- **Formato mensaje**: yaml
- **Estilo de interacción**: Request/Response
- **Estilo Técnico Comunicación**: Asíncrono
- **Especificación de la interfaz**: bill-payment-schedules.yaml 

### Bill - Payment - Schedules operation delete
En la siguiente tabla se hace la descripción flujo/subflujo: 

|Nodo/Acción/Componente|Descripción|
|:-:|:-|
|activity-log|Es un log de actividad, genera traza de mensajería del servicio antes de transformarla.|
|init-meta |Se crea la estructura de respuesta Meta y links, para cumplir con la definición de respuesta.|
|validate-request |Se validan los valores recibidos de la solicitud y se asignan a variables de contexto para ser usadas a través de los siguientes nodos que componen la API.|
|map|Ubica las cabeceras en la respuesta.|
|invoke|Se realiza el llamado al servicio del bus de integración GestionPagoProgramado.0.0
|procces-response|Este nodo permite validar que la respuesta del backend corresponda al formato json. Posteriormente se valida si la respuesta tiene la estructura relacionada a un error de sistema o de negocio; en el evento que se cumpla cualquiera de las dos, se lanza la excepción correspondiente.|
|map-sandbox |Ubica las cabeceras en la petición al EKS.|
|invoke-sandbox |Invoca el API mock desplegao en el EKS.|


### Catch
En la siguiente tabla se hace la descripción flujo/subflujo: 

|Nodo/Acción/Componente|Descripción|
|:-:|:-|
|Parameters-Exception |En este nodo se genera la estructura de error.|
|Map|Ubica las cabeceras en la respuesta.|
|default-exception|Este nodo permite generar un error por defecto para las excepciones no controladas durante la ejecución de la API.|
|business-exception|En este nodo se realiza el mapeo de los códigos de excepción generados por el backend a los códigos de estado http y asigna los títulos correspondientes.|