# Laboratorio 2: Documento de Análisis del Proceso AS-IS

**Empresa:** Click & Go  
**Proceso Analizado:** Gestión Manual de Devoluciones y Reembolsos de Pedidos  
**Estudiante:** Dalis Sanchez  

---

## 1. Guía de Entrevista de Análisis del Proceso

**Entrevistado:** Encargado de Operaciones y Atención al Cliente (Dueño del proceso en Click & Go)  
**Entrevistador:** Dalis Sanchez  

### Sobre el Proceso
1. **¿Puedes describir el proceso paso a paso desde que inicia hasta que termina?**
   > *Respuesta:* El cliente solicita la devolución o cancelación de un cupón enviando un correo o mensaje por WhatsApp. El agente de soporte revisa en la base de datos si el cupón fue usado. Si no ha sido usado, contactamos vía WhatsApp o correo al comercio aliado para confirmar la cancelación. Con la aprobación del comercio, el agente envía un correo a Finanzas para que procesen la devolución manualmente en la pasarela de pago o por Yappy. Finalmente, Soporte le envía un correo al cliente confirmando la devolución.

2. **¿Quiénes intervienen en el proceso? (roles, sistemas, departamentos)**
   > *Respuesta:* Intervienen el Cliente, Agente de Soporte (Click & Go), Comercio Aliado (tercero) y Analista de Finanzas (Click & Go). En sistemas usamos el correo electrónico (Gmail), WhatsApp Web, Excel para registro y el panel de la pasarela de pagos.

3. **¿Con qué frecuencia ocurre este proceso? (diario, semanal, por pedido)**
   > *Respuesta:* Ocurre diariamente, aproximadamente de 5 a 12 solicitudes de reembolso por día.

4. **¿Cuánto tiempo toma desde el inicio hasta el fin en promedio?**
   > *Respuesta:* Toma entre 24 y 48 horas en completarse debido a la espera de respuesta del comercio aliado y Finanzas.

### Sobre los Problemas
5. **¿Cuáles son los pasos que más tiempo consumen? ¿Por qué?**
   > *Respuesta:* Esperar la confirmación del comercio aliado de que el cliente no ha consumido el cupón en su local, ya que muchos comercios tardan horas o días en responder por WhatsApp.

6. **¿En qué pasos se cometen errores con más frecuencia?**
   > *Respuesta:* En el registro de los datos bancarios del cliente para la devolución manual y en la falta de actualización del estado del cupón en la hoja de cálculo.

7. **¿Hay pasos que se hacen manualmente que podrían automatizarse?**
   > *Respuesta:* La verificación del estado del cupón, la notificación automática al comercio aliado mediante un botón o API, y la confirmación automática al cliente.

8. **¿Alguna vez el proceso "se atasca"? ¿En qué punto?**
   > *Respuesta:* Sí, se atasca en la revisión por parte de Finanzas cuando hay volumen alto de liquidaciones de fin de semana.

### Sobre los Datos
9. **¿Qué información se genera en cada paso? (formularios, emails, hojas de cálculo)**
   > *Respuesta:* Correo inicial del cliente, registro de la solicitud en Google Sheets, mensajes de chat con el comercio, comprobante de transferencia/reembolso y correo final de notificación.

10. **¿Cómo se comunican los diferentes actores del proceso? (email, WhatsApp, sistema)**
    > *Respuesta:* Cliente con Soporte por Email/WhatsApp, Soporte con Comercio Aliado por WhatsApp, y Soporte con Finanzas por correo interno.

---

## 2. Registro de Observación Directa

## Registro de Observación – Gestión de Devoluciones y Reembolsos

  
**Observador:** Dalis Sanchez 
**Negocio / Proceso:** Click & Go / Devolución y Reembolso de Cupones  

| Paso | Actor | Tiempo aproximado | Sistema/Herramienta | Observaciones |
|------|-------|-------------------|----------------------|---------------|
| 1. | Cliente | 5 min | WhatsApp / Email | Solicita reembolso adjuntando número de pedido y cupón. |
| 2. | Soporte Click & Go | 10 min | Google Sheets / BD | Revisa manualmente que el cupón no esté registrado como "Canjeado". |
| 3. | Soporte Click & Go | 2 min | WhatsApp Web | Redacta y envía mensaje al comercio aliado pidiendo validación. |
| 4. | Comercio Aliado | 2 a 12 horas | WhatsApp | Revisa sus registros físicos/digitales y responde confirmando. |
| 5. | Soporte Click & Go | 5 min | Gmail | Envía correo interno a Finanzas con datos de la transacción para reembolso. |
| 6. | Finanzas | 1 a 24 horas | Pasarela / Yappy | Valida saldo, ejecuta la devolución y genera comprobante. |
| 7. | Soporte Click & Go | 5 min | Gmail | Notifica al cliente el cierre de la solicitud adjuntando comprobante. |

**Cuellos de botella identificados:**
- **Validación con el comercio aliado:** Dependencia total de la disponibilidad del comercio para responder mensajes en WhatsApp Web.
- **Procesamiento manual en Finanzas:** La falta de integración entre la base de datos de cupones y la pasarela de pago exige intervenciones humanas redundantes.
- **Fragmentación de canales de comunicación:** Se mezcla correo, WhatsApp y hojas de cálculo sin un repositorio centralizado de tickets.

**Datos operativos estimados:**
- **Frecuencia del proceso:** 8 solicitudes diarias (promedio semanal de 50 a 60 casos).
- **Tiempo total promedio:** 28 horas desde la recepción hasta la emisión del reembolso.
- **Tasa de error aproximada:** 12% (principalmente por digitación incorrecta de datos de cuenta o traspaso de información en Google Sheets).

