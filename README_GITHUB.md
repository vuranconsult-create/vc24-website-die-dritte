# GitHub Import – VURAN Consulting

## Option A – Weboberfläche (einfach)
1. Öffne https://github.com/new (neues Repository anlegen).
2. Gib einen Namen ein, z. B. `vc24-website` (Public oder Private).
3. Repo erstellen → **Add file → Upload files** → gesamten Inhalt dieses Projekts hochladen (nicht den ZIP selbst, sondern alle Dateien/Ordner).
4. **Commit changes** (am Ende der Seite).

## Option B – Git CLI (schnell)
```bash
unzip vuran-consulting-site.zip
cd vuran-consulting-site

# Neues Repo auf GitHub anlegen (im Browser), dann:
git init
git branch -M main
git add .
git commit -m "Initial commit: vc24 website + API"
git remote add origin https://github.com/<DEIN_USERNAME>/<DEIN_REPO>.git
git push -u origin main
```

## Danach: IONOS Deploy Now
- Frontend-App (Root): Build `npm run build`, Output `dist`
- ENV Frontend: `VITE_API_BASE=https://api.vc24.berlin`
- Backend-App (Root: `server/`): Start `node index.mjs`
- ENV Backend: siehe `server/.env.example` (SMTP, MAIL_TO, CORS_ORIGIN=https://www.vc24.berlin)

## Optional: GitHub Actions
IONOS Deploy Now pullt das Repo automatisch. Actions sind hier nicht zwingend nötig.
