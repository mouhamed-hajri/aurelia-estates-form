# Aurelia Estates — inquiry form

A 3-step property inquiry form for *Aurelia Estates*, a fictional real-estate agency. It is the front door of my **Sophie** project: each submitted lead is sent to an n8n workflow, where an AI assistant follows up with the lead on Telegram.

## What it does

- **Step 1, contact details:** full name, email, phone, Telegram username (optional)
- **Step 2, search:** buy or rent, property type, budget range, location
- **Step 3, specifics:** bedrooms, timeline and a free-text message
- On submit, the form sends the lead as JSON (`POST`) to an n8n webhook, and shows an error if the webhook URL isn't configured or the request fails.

## Tech stack

A single `index.html` with plain HTML, CSS and JavaScript. No build step and no dependencies.

## Use it

1. Open `index.html` in a browser, or serve the folder with any static server.
2. To send leads somewhere, set `WEBHOOK_URL` in the script at the bottom of `index.html` to your n8n webhook (the path used is `/webhook/lead`). If n8n runs locally behind ngrok, the request includes the `ngrok-skip-browser-warning` header.
