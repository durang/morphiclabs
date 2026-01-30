# Morphic Labs — Estado Real (Fuente de Verdad)

> Regla: este documento describe el sistema. No autoriza cambios ni ejecución.

## Runtime principal (Core)
- Vive en: Replit (BLOQUEADO para ejecución automática por Jarvis)
- Repl name: morphiclabs
- Frontend: React 18 + Vite
- Backend: Node.js + Express
- DB: Neon (Postgres)

- Auth (recomendación): Clerk (ideal para SaaS + roles + social login + magic links)
  - Nota: si hoy tu auth es “custom”, se mantiene; Clerk queda como ruta recomendada.

- AI Providers: Replicate + Anthropic/Claude + Google Gemini
- Payments: Stripe + Lemon Squeezy
- Storage (recomendación): Cloudflare R2 (o S3 si ya está montado)

## Deploy / dominios
- Dominio principal: morphiclabs.io
- Hosting del core: Replit (con dominio apuntado)
- Entornos: un solo entorno (prod) por ahora (recomendado). Staging opcional después.

## Landings (Marketing) — EJECUCIÓN PERMITIDA
- Repo: durang/morphic-landings
- Deploy: Vercel
- URL base: https://morphic-landings.vercel.app/landings/<slug>
- Generación: script `~/morphic-landings/scripts/make_landing.sh`
- Regla: “LANDING” => SOLO Vercel/Git (no Replit core)

## Automatizaciones / Bots
- Telegram bot: @Sergioduranbot
- Qué hace hoy: canal de control (inputs tipo “haz landing…”, requests, notas)
- Qué NO debe hacer:
  - NO tocar Replit (Morphic Core)
  - NO tocar DB
  - NO manejar keys en chat
  - NO ejecutar comandos destructivos

## Zonas rojas (NO TOCAR)
- Keys/tokens/cookies (solo GitHub Secrets o gestor de contraseñas)
- DB prod
- Billing (Stripe/LemonSqueezy)
- Infra del core en Replit sin orden explícita

## Mini-apps actuales (conocidas)
- Character Studio
- MyCast
- NanoBanana Pro
- Lucky Mode
- ArchViz Studio
- Real Actors
- Agency OS

## Backlog de mini-apps (ideas recurrentes)
- Portal/Client OS (white-label + agencies + bulk credits)
- First & Last Frame / Quick Cinema Studio (video pipeline)
- Webhook “transcribe/translate” (input URL → output)
