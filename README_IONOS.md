# IONOS Deployment

## Variante A: IONOS Deploy Now (empfohlen)
1. Code ins GitHub-Repo pushen.
2. In IONOS **Deploy Now** neues Projekt anlegen und Repo verbinden.
3. **Frontend**-Projekt:
   - Build Command: `npm run build`
   - Output: `dist`
   - Env: `VITE_API_BASE=https://<deine-api-domain>`
4. **Backend**-Projekt (separat anlegen, Node.js):
   - Start Command: `node server/index.mjs`
   - Root Directory: `server`
   - Env: SMTP_HOST, SMTP_PORT, SMTP_SECURE, SMTP_USER, SMTP_PASS, MAIL_FROM, MAIL_TO, CORS_ORIGIN
5. Frontend auf die API-URL zeigen lassen (`VITE_API_BASE`).

## Variante B: IONOS Webhosting (nur statisch)
- `npm run build` lokal → `/dist` per SFTP/FTP in `/htdocs` laden.
- Node/Express-API separat betreiben (z. B. IONOS VPS/Cloud oder Render) und `VITE_API_BASE` auf diese URL setzen.

## Variante C: IONOS vServer/Cloud
- Docker Compose oder Node direkt:
    - `cd server && node index.mjs`
- Reverse Proxy (Nginx) und TLS (Let's Encrypt) einrichten.


## SEO-Hinweise (www.vc24.berlin)
- Canonical auf `https://www.vc24.berlin/` gesetzt (in `index.html`).
- `robots.txt` & `sitemap.xml` vorhanden (Pfad: `public/`).
- Empfohlen: 301-Redirect auf **www**-Variante einrichten (IONOS -> Domain-Einstellungen).
- Strukturierte Daten (JSON-LD: Organization, WebSite) im `<head>`.
- Sinnvolle H1/H2, sprechende Seitentitel & Descriptions bereits gesetzt.
