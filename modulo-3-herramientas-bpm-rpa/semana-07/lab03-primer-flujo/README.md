# Laboratorio 3 — Primer Flujo No-Code Funcional

**Curso:** INF320 - Automatización de Procesos de Negocios   
**Estudiante:** Dalis Sanchez  
**Empresa / Caso:** Click & Go  

---

## Flujo: Notificación y Registro Automático de Solicitudes de Devolución

**Herramienta:** Zapier 

**Disparador (Trigger):**
- **Aplicación:** Gmail
- **Evento:** "Nuevo email recibido" con asunto que contiene `"Solicitud de Devolución"

**Pasos del flujo:**
1. **ACCIÓN: Google Sheets → Agregar fila**
   - **Hoja de cálculo:** Registro_Devoluciones_ClickAndGo
   - **Columna "Fecha":** `{{ step1.message.created_at }}`
   - **Columna "Cliente Email":** `{{ step1.message.from.email }}`
   - **Columna "Asunto":** `{{ step1.message.subject }}`
   - **Columna "Estado":** `Pendiente de revisión`

2. **ACCIÓN: Gmail → Enviar email**
   - **Para:** `{{ step1.message.from.email }}`
   - **Asunto:** `Confirmación de Recepción: {{ step1.message.subject }}`
   - **Cuerpo:** `Hola, hemos recibido tu solicitud de devolución para Click & Go. Nuestro equipo de soporte validará los datos en breve.`

---

## Capturas de Pantalla del Flujo

`![Flujo Zapier Configurado](./flujo-zapier-configurado.png)`

---

## Declaración de Uso de IA

| Campo | Detalle |
|---|---|
| **¿Se usó IA?** | Sí |
| **Herramienta(s)** | Gemini |
| **Para qué se usó** | Formateo técnico de la documentación en Markdown según la plantilla requerida. |
| **Qué hizo el estudiante por su cuenta** | Configuración de los nodos del flujo no-code, selección de campos en Google Sheets y redacción de las alertas de correo. |
