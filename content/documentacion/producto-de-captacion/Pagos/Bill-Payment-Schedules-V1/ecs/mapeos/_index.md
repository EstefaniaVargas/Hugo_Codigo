---
title: "Mapeo de Datos"
date: 2021-05-20T10:31:03-05:00
layout: single
---

A continuación se especifican las transformaciones por operación:
- [delete-schedules](deleteSchedules.json)

## Excepciones de sistema
| Código respuesta proveedor | Código API | Status code HTTP | Title                 | Descripción                                                                 |
|----------------------------|------------|------------------|-----------------------|-----------------------------------------------------------------------------|
|                            | SP404      | 401              | Unauthorized          | El   consumidor no tiene acceso a la información solicitada.                |
|                            | SP500      | 500              | Internal Server Error | Ha ocurrido un error interno   controlado en el servidor.                   |
|                            | SP500      | 500              | Internal Server Error | Descripción   entregada por el proveedor                                    |
|                            | SP502      | 502              | Bad Gateway           | El   mensaje de respuesta recibido del servidor es inválido.                |
|                            | SP503      | 503              | Service Unavailable   | El   servicio no está disponible temporalmente. Intente de nuevo más tarde. |
|                            | SP504      | 504              | Gateway Timeout       | El proveedor no respondió en   tiempo esperado                              |
|                            | SA400      | 400              | Bad Request           | El parametro documentType es   requerido                                    |
|                            | SA401      | 401              | Unauthorized          | El JWT es invalido.                                                         |
|                            | SA500      | 500              | Internal Server Error | Error interno del servidor.   Intente de nuevo más tarde.                   |
|                            | SA504      | 504              | Gateway Timeout       | La API no respondió en tiempo   esperado                                    |

## Excepciones de negocio
| Código respuesta proveedor | Código API | Status code HTTP | Title       | Descripción                                                                                                               | Notas |
|----------------------------|------------|------------------|-------------|---------------------------------------------------------------------------------------------------------------------------|-------|
| 13000001                   | BP13000001 | 409              | Conflict    | El número del convenio no está   activo                                                                                   |       |
| 13000001                   | BP13000001 | 400              | Bad Request | El tipo de documento es   obligatorio.                                                                                    |       |
| 13000002                   | BP13000002 | 400              | Bad Request | El número de documento es   obligatorio.                                                                                  |       |
| 13000003                   | BP13000003 | 400              | Bad Request | Longitud invalida tipo de documento                                                                                       |       |
| 13000004                   | BP13000004 | 400              | Bad Request | Longitud invalida del documento                                                                                           |       |
| 13000005                   | BP13000005 | 400              | Bad Request | Longitud invalida del convenio                                                                                            |       |
| 13000006                   | BP13000006 | 400              | Bad Request | Longitud invalida de la refencia                                                                                          |       |
| 13000007                   | BP13000007 | 400              | Bad Request | Longitud invalida del nombre del convenio                                                                                 |       |
| 13000008                   | BP13000008 | 400              | Bad Request | Longitud invalida del canal                                                                                               |       |
| 13000009                   | BP13000009 | 400              | Bad Request | Longitud invalida descripción de la   factura                                                                             |       |
| 13000010                   | BP13000010 | 400              | Bad Request | Longitud invalida de la fecha                                                                                             |       |
| 13000011                   | BP13000011 | 400              | Bad Request | Fecha invalida                                                                                                            |       |
| 13000012                   | BP13000012 | 400              | Bad Request | Longitud invalida del valor de   la factura                                                                               |       |
| 13000013                   | BP13000013 | 400              | Bad Request | Valor de factura invalido                                                                                                 |       |
| 13000013                   | BP13000013 | 400              | Bad Request | Valor de factura invalido                                                                                                 |       |
| 13000014                   | BP13000014 | 400              | Bad Request | Por favor ingrese un número de   convenio válido                                                                          |       |
| 13000015                   | BP13000015 | 404              | Not Found   | Canal inválido                                                                                                            |       |
| 13000016                   | BP13000016 | 400              | Bad Request | El número del convenio es   obligatorio                                                                                   |       |
| 13000017                   | BP13000017 | 400              | Bad Request | La referencia es obligatoria                                                                                              |       |
| 13000018                   | BP13000018 | 400              | Bad Request | Los campos referencia, fecha de   inscripción, número de convenio, tipo y número de identificación deben ser   ingresados |       |
| 13000019                   | BP13000019 | 400              | Bad Request | La función es inválida.                                                                                                   |       |
| 13000020                   | BP13000020 | 400              | Bad Request | !El monto de la factura es   obligatorio, no puede ser un valor menor que cero y no puede estar en blanco.                |       |
| 13000021                   | BP13000021 | 400              | Bad Request | La bandera de eliminación no   existe para la función Eliminar                                                            |       |
| 13000022                   | BP13000022 | 404              | Not Found   | La factura no existe                                                                                                      |       |
| 13000023                   | BP13000023 | 400              | Bad Request | La bandera de eliminación es   obligatoria para la función Eliminar                                                       |       |
| 13000024                   | BP13000024 | 409              | Conflict    | La referencia tiene una   suscripción activa para el mismo pagador                                                        |       |
| 13000025                   | BP13000025 | 400              | Bad Request | El campo referencia principal es   obligatorio                                                                            |       |
| 13000026                   | BP13000026 | 409              | Conflict    | Modificación no permitida para   esta inscripción                                                                         |       |
| 13000027                   | BP13000027 | 409              | Conflict    | La combinación tipo de documento   y número de documento no existe                                                        |       |