# WhatsApp Booking Agent — Peluquerías con IA

Agente conversacional que gestiona **reservas, cancelaciones y consultas de cita** por WhatsApp de forma completamente automática. Sin intervención humana.

Construido para peluquerías y negocios de servicios con citas recurrentes.

---

## El problema que resuelve

Una peluquería recibe decenas de mensajes de WhatsApp al día para gestionar citas. Responder manualmente interrumpe el trabajo, genera errores y cuesta tiempo. Este agente lo gestiona todo 24/7.

**Conversación real:**
> Cliente: "Hola, quiero cortarme el pelo el viernes por la tarde"
> Agente: "Tengo disponible el viernes a las 17:00 y 18:30. ¿Cuál prefieres?"
> Cliente: "A las 17"
> Agente: "Perfecto, cita confirmada el viernes 6 de junio a las 17:00. Te mando recordatorio el día antes."

---

## Qué hace

- Recibe mensajes de WhatsApp vía Meta API (webhook)
- GPT-4o interpreta la intención: reservar, cancelar, consultar o reprogramar
- Verifica disponibilidad en Google Calendar en tiempo real
- Crea, modifica o cancela eventos automáticamente
- Mantiene memoria por cliente (historial por número de teléfono)
- Responde en WhatsApp con confirmación o alternativas de horario

---

## Stack

| Herramienta | Uso |
|---|---|
| n8n | Orquestación del flujo |
| WhatsApp Business API (Meta) | Canal de mensajería |
| GPT-4o | Comprensión del lenguaje e intención |
| Google Calendar API | Gestión de disponibilidad y eventos |
| Buffer Memory | Historial de conversación por cliente |

---

## Flujo


