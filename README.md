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

WhatsApp Trigger
→ Extraer datos del mensaje
→ ¿Tiene texto?
→ Agente IA (GPT-4o)
├── Verificar disponibilidad en Calendar
├── Crear cita
├── Cancelar cita
└── Buscar citas del cliente
→ Respuesta por WhatsApp

---

## Setup

1. Importa `workflow.json` en tu instancia de n8n
2. Configura las credenciales:
   - WhatsApp Business API (Meta Developer Console)
   - OpenAI API Key
   - Google Calendar OAuth2
3. En Meta Developer Console: apunta el webhook a tu URL de n8n
4. En el workflow: reemplaza `YOUR_CALENDAR_ID` por tu email de Google
5. Activa el workflow

**Requisitos:** n8n self-hosted o cloud · Cuenta Meta Business verificada · API Key de OpenAI

---

## Adaptable a otros negocios

El mismo flujo funciona para clínicas, centros de estética, fisioterapeutas o cualquier negocio basado en citas. Solo cambia el prompt del agente.

---

Sergio Cebrián · [github.com/scebriii](https://github.com/scebriii)


