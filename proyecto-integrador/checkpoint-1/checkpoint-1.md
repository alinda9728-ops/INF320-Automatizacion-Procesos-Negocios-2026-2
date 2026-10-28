# Checkpoint 1 — BPMN AS-IS + Oportunidades de Automatización

---

## Datos 

| Campo | Información |
|---|---|
| Estudiante | Dalis Sanchez |
| Negocio | Click & Go |
| Proceso intervenido | Gestión Manual de Devoluciones y Reembolsos de Pedidos |
| Versión del entregable | v1.0 |

---

## 1. Diagrama BPMN AS-IS

### Descripción del proceso (en palabras, antes de ver el diagrama)

| Paso | Actor | Descripción | Tiempo aproximado |
|---|---|---|---|
| 1 | Cliente | Solicita la devolución o cancelación del pedido/cupón por correo o WhatsApp. | 5 minutos |
| 2 | Soporte Click & Go | Recibe la solicitud y verifica manualmente en la base de datos si el cupón ya fue canjeado. | 10 minutos |
| 3 | Soporte Click & Go | Contacta por WhatsApp al comercio aliado para confirmar la anulación de la orden. | 2 minutos |
| 4 | Comercio Aliado | Revisa su sistema interno y responde confirmando o rechazando la anulación. | 2 a 12 horas |
| 5 | Soporte Click & Go | Envía un correo interno a Finanzas con los datos de la transacción para proceder al reembolso. | 5 minutos |
| 6 | Finanzas | Valida fondos y ejecuta manualmente la devolución en la pasarela de pagos o por Yappy. | 1 a 24 horas |
| 7 | Soporte Click & Go | Envía el comprobante final y notifica al cliente que su devolución se ha completado. | 5 minutos |

### Archivo del diagrama
* **Imagen PNG:** `proyecto-integrador/kickoff/diagrama-as-is-practica.png`    


### Indicadores operativos actuales (medidos o estimados)

| Indicador | Valor actual |
|---|---|
| Frecuencia del proceso | 8 solicitudes diarias (aprox. 55 semanales) |
| Tiempo promedio por ejecución | 28 horas |
| Tasa de error aproximada | 12% de los casos (errores de transcripción y datos bancarios) |
| Número de actores involucrados | 4 actores (Cliente, Soporte, Comercio Aliado, Finanzas) |

---

## 2. Cuellos de botella identificados

| Cuello de botella | Paso afectado | Impacto estimado |
|---|---|---|
| Demora en respuesta del comercio aliado | Paso 4 | Incrementa el tiempo de espera del cliente hasta 12 horas innecesariamente. |
| Gestión manual de la pasarela y reembolsos | Paso 6 | Carga operativa alta para el departamento de Finanzas y riesgo de errores de digitación. |
| Verificación manual de cupones | Paso 2 | Centraliza el trabajo operativo en el agente de soporte sin validación automática en tiempo real. |

---

## 3. Oportunidades de automatización identificadas

| Oportunidad | Descripción | Pasos del proceso que afecta |
|---|---|---|
| 1. Notificación automática a comercios | Enviar un webhook o alerta automática al sistema del aliado al solicitar la devolución. | Paso 3 y 4 |
| 2. Validación automatizada de cupones | Validar de forma automática en la base de datos si el cupón está activo o canjeado mediante reglas de negocio. | Paso 2 |
| 3. Integración de pasarela de pagos | Emitir el reembolso de manera automática a través de la API de la pasarela o Yappy al aprobarse el caso. | Paso 6 |

---

## 4. Matriz de priorización

| Oportunidad | Volumen (1-5) | Repetitividad (1-5) | Reglas claras (1-5) | Valor (1-5) | Esfuerzo (Bajo/Medio/Alto) | Puntaje total |
|---|---|---|---|---|---|---|
| 1. Notificación automática a comercios | 4 | 5 | 4 | 4 | Medio | 17 |
| 2. Validación automatizada de cupones | 5 | 5 | 5 | 5 | Bajo | **20** |
| 3. Integración de pasarela de pagos | 4 | 4 | 3 | 5 | Alto | 16 |

---

## 5. Oportunidad seleccionada para el proyecto

* **Oportunidad elegida:** Validación automatizada de cupones y verificación de estados en el sistema.
* **Justificación (por qué esta sobre las otras):** Presenta reglas de negocio claras, un volumen alto de transacciones diarias y un esfuerzo de implementación bajo, lo que genera un impacto inmediato y reduce drásticamente la intervención manual de soporte[cite: 12].
* **Impacto esperado (qué mejorará cuando se automatice):** Reducirá el tiempo del Paso 2 de 10 minutos a segundos y eliminará por completo los errores humanos de transcripción en la verificación de canjes.

---

## 6. ¿Qué sigue? (plan hacia el Checkpoint 2)

¿Qué harán en las próximas 4 semanas?
* [x] Tarea 1: Modelado y documentación inicial del proceso AS-IS.
* [ ] Tarea 2: Diseño de la arquitectura de la solución TO-BE y definición de flujos automatizados.
* [ ] Tarea 3: Configuración de la automatización en la plataforma o herramientas seleccionadas (ej. Zoho/GoHighLevel/Apps Script).
* [ ] Tarea 4: Pruebas de integración y validación de indicadores de mejora.

---

## Declaración de uso de IA

| Campo | Detalle |
|---|---|
| ¿Se uso IA? | Sí |
| Herramienta(s) | Gemini |
| Para qué se usó | Estructuración de redacción técnica y formateo de tablas Markdown para el reporte. |
| Qué hizo el equipo por su cuenta | Levantamiento de información del negocio Click & Go, definición de la entrevista, diagramación BPMN y priorización estratégica. |
