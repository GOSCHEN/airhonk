# ultraplanner

## Airhorn-App (`app/`)

Installierbare Web-App (PWA): ein Knopf, ein Sound. Jeder Druck startet den Sound von vorn,
dazu Partikel-Effekt und kurze Vibration. Funktioniert nach dem ersten Laden auch offline.

### Lokal starten

```sh
npx serve app        # oder: python3 -m http.server -d app 8080
```

Service Worker und Installation brauchen `localhost` oder HTTPS.

### Installieren

- **Android / Chrome / Edge:** Seite öffnen → Menü → „App installieren“.
- **iPhone / iPad (Safari):** Teilen → „Zum Home-Bildschirm“.

### Veröffentlichen

`.github/workflows/pages.yml` deployt `app/` bei jedem Push auf `main` nach GitHub Pages.
Einmalig nötig: im Repo unter *Settings → Pages → Source* „GitHub Actions“ auswählen.

### Dateien

| Datei | Zweck |
| --- | --- |
| `index.html` | Oberfläche, Audio (Web Audio API) und Partikel |
| `airhorn.wav` | Der Sound |
| `manifest.webmanifest` | App-Name, Icons, Standalone-Modus |
| `sw.js` | Offline-Cache; bei Änderungen `VERSION` erhöhen |
| `icons/` | App-Icons (SVG-Quelle + PNGs) |
