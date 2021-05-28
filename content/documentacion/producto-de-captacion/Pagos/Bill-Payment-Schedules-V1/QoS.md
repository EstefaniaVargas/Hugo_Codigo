---
title: "QoS"
date: 2021-05-20T10:31:03-05:00
layout: "single"
---

Estos atributos se refieren a la API y hacen parte del SLD (Definición del nivel de servicio)

**Nota:** se definen los atributos de calidad de la API para el productor, no para el consumidor

## Operaciones


### **Controles de seguridad a nivel de mensaje**
|Nombre de la operación|Identificación y autenticación|Autorización|Confidencialidad|Integridad|Auditabilidad|
|-|:-:|:-:|:-:|:-:|:-:|
|/bills/schedules/automatic-debit (DELETE)|API-Key (Por medio de las credenciales asociadas en el portal de API de Bancolombia)|API-Key|SSL entre el cliente y el API Gateway|SSL entre el cliente y el API Gateway|Analítica en API Connect|
|

### **Desempeño y disponibilidad**
| Nombre de la operación|Transacciones soportadas por segundo|Tiempo de respuesta máximo en segundos|Tiempo de respuesta promedio en segundos|Horario disponible|
|-|-|-|-|-|
|/bills/schedules/automatic-debit (DELETE)|10|30|2|7 días - 24 horas|
|

