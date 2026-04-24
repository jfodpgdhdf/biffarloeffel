# biffarloeffel.webtak.de

Potenzialanalyse von WEBTAK für Biffar und Löffelfenster.
Single-Page, keine Build-Tools, deploy-ready.

## Dateien

- `index.html` – die komplette Präsentation (self-contained, Chart.js via CDN)
- `favicon.svg` – WEBTAK-Favicon
- `CNAME` – GitHub-Pages Custom Domain
- `.nojekyll` – deaktiviert Jekyll-Processing

## Go-Live (ca. 5 Min)

### 1. GitHub Repo anlegen

```bash
cd deploy
git init
git add .
git commit -m "Initial deployment – WEBTAK Pitch"
git branch -M main
git remote add origin git@github.com:<DEIN_USER>/biffarloeffel.git
git push -u origin main
```

### 2. GitHub Pages aktivieren

Repo → Settings → Pages → Source: **main / root** → Save.
Custom Domain: `biffarloeffel.webtak.de` (CNAME-Datei im Repo wird automatisch erkannt).

### 3. DNS in All-Inkl KAS

- Login: https://kas.all-inkl.com
- Tools → DNS-Einstellungen → Domain `webtak.de` → DNS-Records bearbeiten
- Neuen Record:
  - **Name:** `biffarloeffel`
  - **Typ:** `CNAME`
  - **Zielhost:** `<DEIN_USER>.github.io.` (mit Punkt am Ende!)
  - TTL: Standard
- Speichern

Alternativ (falls CNAME nicht möglich für Subdomain):
- 4× A-Records auf Name `biffarloeffel` zu:
  - `185.199.108.153`
  - `185.199.109.153`
  - `185.199.110.153`
  - `185.199.111.153`

### 4. HTTPS

In GitHub Pages Settings: **Enforce HTTPS** aktivieren (nach DNS-Propagation, ~10–60 Min).

Fertig. Öffne https://biffarloeffel.webtak.de
