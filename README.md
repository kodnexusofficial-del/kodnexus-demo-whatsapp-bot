# Kodnexus WhatsApp Bot — Demo

WhatsApp-style multi-business AI chatbot simulation. It is **not** a WhatsApp Business API integration: messages, bookings, payments, and human handoffs are simulated.

## Setup

1. Install Node.js 18 or later.
2. Run `npm install`.
3. Copy `.env.example` to `.env` and set:

```env
GEMINI_API_KEY=your_key_here
GEMINI_MODEL=gemini-2.5-flash
PORT=3000
```

4. Run `npm run dev`.
5. Open http://localhost:3000.

## Editing business context

Edit [context.json](context.json) to change names, services, plans, doctors, menu, pricing, timings, FAQs, tone, and rules. The backend reads it for every request, so updated context is used without frontend edits.

## Architecture and limits

Each demo chat keeps its own recent history in the browser and sends it to `POST /api/chat`. The server reads the selected context and invokes Gemini, keeping `GEMINI_API_KEY` server-only. Attachments and voice notes are visual simulations and are not processed by Gemini. Gemini quality and availability depend on your configured key/model.
