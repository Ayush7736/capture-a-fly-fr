# FLYMIND — NEURAL GARDEN

A lightweight retro browser survival game where **you are the fly**.

## Deployment

### Frontend — Vercel
Deploy **this repository** (`capture-a-fly-fr`) as a static Vercel project.

Use the repository root as the Root Directory. There is no framework build step and no required install command.

### Backend — Render
Deploy `capture-a-fly-br` as a Render **Web Service** with:

- Build: `pip install -r requirements.txt`
- Start: `uvicorn backend.main:app --host 0.0.0.0 --port $PORT`

The frontend is already configured to use:

`https://capture-a-fly.onrender.com`

Keep `OPENROUTER_API_KEY` server-side on Render. Never put it in this repository or in browser code.

## Features

- Solo survival gameplay
- Compact LIF-style neural controller in a Web Worker
- Nectar/energy/health loop
- Human net hunter with local fallback + optional OpenRouter planning
- Hostile wasps
- Multiplayer rooms with lightweight state sync
- WebRTC voice signaling through Render
- Chat
- Desktop + touch controls
- Retro pixel/CRT presentation
- Optional ad/reward integration hook

## Multiplayer

Players connect to Render over `wss://capture-a-fly.onrender.com/ws`. The Vercel frontend is only the static client.

## Security

Do not commit API keys. The OpenRouter key belongs only in the Render service environment.

## Project split

`capture-a-fly-fr` = browser client / Vercel
`capture-a-fly-br` = API + WebSocket / Render