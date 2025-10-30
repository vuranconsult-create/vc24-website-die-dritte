# VURAN Consulting – Deployment Guide

## Frontend (Vercel)
1. Repository auf GitHub hochladen (Ordner-Inhalt dieses Projekts).
2. Auf https://vercel.com ein neues Projekt anlegen, Repo verbinden.
3. Build Einstellungen:
   - Framework: Vite (automatisch)
   - Build Command: `npm run build`
   - Output Directory: `dist`
4. Deploy klicken → Domain merken, z. B. `https://vc24.vercel.app`.

## Backend (Render)
1. Repo mit Render verbinden: https://render.com → **New +** → **Blueprint** → das Repo wählen.
2. `render.yaml` wird erkannt und erzeugt den Web-Service **vuran-consulting-api**.
3. Environment-Variablen setzen:
   - `CORS_ORIGIN` = `https://<deine-vercel-domain>`
   - `SMTP_HOST`, `SMTP_USER`, `SMTP_PASS` (vom Mailprovider)
   - Optional: `MAIL_FROM`, `MAIL_TO`
4. Deploy starten. Nach dem Start: API-URL merken, z. B. `https://vuran-consulting-api.onrender.com`.

## Frontend → Backend URL (optional)
Standardmäßig nutzt das Frontend `http://localhost:4000` für die Entwicklung.
Für Produktion könntest du die Ziel-URL in `src/App.jsx` anpassen oder über eine ENV/Build-Variable injizieren.

## Test
- `GET /api/health` → `{ ok: true }`
- Kontaktformular und Jobformular ausfüllen → E-Mails sollten im Postfach `MAIL_TO` ankommen.

## Sicherheit / DSGVO
- Starke SMTP-Zugangsdaten
- TLS (Render liefert automatisch HTTPS)
- Impressum & Datenschutztexte regelmäßig prüfen/aktualisieren
