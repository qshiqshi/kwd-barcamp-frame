# KWD Barcamp 2026 – Frame Generator

Erstelle deinen persönlichen "Ich bin dabei!"-Frame fuer LinkedIn-Posts (1:1) und Stories/Reels (9:16).

## Features

- Foto hochladen per Button oder Drag & Drop
- Bild verschieben und zoomen
- Mehrere Frame-Designs waehlbar
- Download als PNG (1080x1080 und 1080x1920)
- Per E-Mail senden (Web Share API mit Fallback)
- Auf LinkedIn teilen (Web Share API mit Fallback)
- Komplett clientseitig – keine Daten werden uebertragen

## Deployment

### Lokal (Entwicklung)

```bash
npx serve public -l 3000
```

### Docker

```bash
docker build -t kwd-barcamp-frame .
docker run -p 8080:80 kwd-barcamp-frame
```

### Netlify

Repo verbinden, fertig. Build-Einstellungen sind in `netlify.toml` konfiguriert.

### Vercel

Repo verbinden, fertig. Build-Einstellungen sind in `vercel.json` konfiguriert.

### Beliebiger Webserver

Den Inhalt von `public/` als Document Root bereitstellen. Kein Build-Schritt noetig.

```bash
# Beispiel: Nginx
cp -r public/* /var/www/html/

# Beispiel: Apache
cp -r public/* /var/www/html/

# Beispiel: Caddy
caddy file-server --root public --listen :8080
```

## Projektstruktur

```
public/
  index.html          # Komplette App (HTML + CSS + JS + eingebettete Frames)
  fonts/              # Selbst gehostete Schriften (Poppins, Roboto)
Dockerfile            # Container-Deployment
netlify.toml          # Netlify-Konfiguration
vercel.json           # Vercel-Konfiguration
package.json          # npm-Scripts fuer lokale Entwicklung
```
