# HDC Documentation

Diese Dokumentation wird automatisch über GitHub Pages veröffentlicht.

## Lokale Entwicklung

Um die Dokumentation lokal zu testen:
```bash
# Im Projekt-Verzeichnis
cd docs
python -m http.server 8000
# Öffne http://localhost:8000
```

## GitHub Pages aktivieren

1. Gehe zu Repository Settings → Pages
2. Wähle "Deploy from a branch"
3. Branch: `develop` oder `main`
4. Folder: `/docs`
5. Save

Die Dokumentation ist dann verfügbar unter:
`https://[username].github.io/HDC-Hapak-Docbox-R--Connector/`

## Dokumentations-Struktur

- `index.html` - Startseite mit Übersicht
- `installation.html` - Installationsanleitung
- `configuration.html` - Konfigurationsreferenz
- `troubleshooting.html` - Problembehebung

## Style-Guide

- Deutsche Sprache
- Responsive Design
- Konsistente Navigation
- Klare Farbkodierung:
  - Blau (#667eea) für Hauptüberschriften
  - Grün für Lösungen
  - Rot für Probleme
  - Gelb für Warnungen

## Aktualisierung

Bei Änderungen an der Dokumentation:
1. HTML-Dateien im `docs/` Verzeichnis bearbeiten
2. Committen und pushen
3. GitHub Pages aktualisiert automatisch

## API-Dokumentation

Für zukünftige API-Dokumentation:
- `api.html` - REST-API Referenz
- Swagger/OpenAPI Integration möglich