# workspace-cli-site

Statische Seite zum privaten Werkzeug "Workspace CLI" (lokaler Zugriff auf den eigenen
Google-Kalender über die Google-Calendar-API).

Diese Seite existiert, weil die Google-Auth-Plattform für den Status "Produktion" drei
öffentliche Links verlangt: Startseite, Datenschutzerklärung, Nutzungsbedingungen.

## Inhalt

| Datei | Zweck |
|---|---|
| `index.html` | Startseite (Homepage) |
| `datenschutz.html` | Datenschutzerklärung |
| `nutzungsbedingungen.html` | Nutzungsbedingungen |
| `.nojekyll` | verhindert Jekyll-Verarbeitung beim GitHub-Pages-Build |

Enthält bewusst keine personenbezogenen Daten, keine Cookies, keine externen Skripte
und keine Analyse.

## URLs (GitHub Pages)

- https://eugenschmalz.github.io/workspace-cli-site/
- https://eugenschmalz.github.io/workspace-cli-site/datenschutz.html
- https://eugenschmalz.github.io/workspace-cli-site/nutzungsbedingungen.html

## Lokal prüfen

```bash
python3 -m http.server 8781
# dann http://127.0.0.1:8781/ öffnen
```

## Rollback

Die Seite wird in der Google-Auth-Plattform nur als Verweis benötigt. Ein Rollback ist
jederzeit möglich und hat keine Auswirkung auf den lokalen Token:

1. Nur Links entfernen: in der Google-Auth-Plattform unter "Branding" die drei Felder
   leeren. Der Veröffentlichungsstatus kann wieder auf "Test" gesetzt werden.
2. Seite vollständig entfernen (Offline nehmen):

   ```bash
   gh repo delete eugenschmalz/workspace-cli-site --yes
   ```

Danach sind die drei URLs nicht mehr erreichbar, das OAuth-Setup bleibt davon unberührt.
