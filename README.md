# Agente IA Peluqueria — WhatsApp + Google Calendar

Agente conversacional para peluquerias que gestiona citas por WhatsApp usando GPT-4o y Google Calendar.

## Que hace

- Recibe mensajes de WhatsApp via Meta API (webhook)
- GPT-4o interpreta la intencion: reservar, cancelar, consultar o reprogramar
- Verifica disponibilidad en Google Calendar en tiempo real
- Crea, modifica o cancela eventos automaticamente
- Memoria por cliente (historial de conversacion por numero de telefono)
- Responde en WhatsApp con confirmacion o alternativas de horario

## Stack

n8n · WhatsApp Business API (Meta) · GPT-4o · Google Calendar API · Buffer Memory

## Flujo

`
WhatsApp Trigger → Extraer datos → ¿Tiene texto? → Agente IA
                                                     ├── Verificar disponibilidad Calendar
                                                     ├── Crear cita en Calendar
                                                     ├── Cancelar cita en Calendar
                                                     └── Buscar citas del cliente
                                    → Send WhatsApp Message
`

## Setup

1. Importa `workflow.json` en n8n
2. Credenciales: WhatsApp Business API, OpenAI API, Google Calendar OAuth2
3. Configura webhook en Meta Developer Console
4. Reemplaza `YOUR_CALENDAR_ID` con tu email de Google Calendar
5. Activa el workflow

## Autor

Sergio Cebrian · github.com/scebriii
