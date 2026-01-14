# HDC - Hapak-DocBox-Connector

[![.NET Version](https://img.shields.io/badge/.NET-8.0-blue.svg)](https://dotnet.microsoft.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![GitHub release](https://img.shields.io/github/release/wkw2k/HDC-Hapak-Docbox-R--Connector.svg)](https://github.com/wkw2k/HDC-Hapak-Docbox-R--Connector/releases/)
[![Build Status](https://img.shields.io/github/actions/workflow/status/wkw2k/HDC-Hapak-Docbox-R--Connector/release.yml)](https://github.com/wkw2k/HDC-Hapak-Docbox-R--Connector/actions)

Der **Hapak-DocBox-Connector (HDC)** ist eine professionelle Integrationslösung zur automatischen Übertragung von Dokumenten zwischen dem Hapak ERP-System und der DocBox Dokumentenmanagement-Plattform.

## 🚀 Features

### Kernfunktionalitäten
- ✅ **Automatische Dateiverarbeitung** - Überwachung von HotFoldern
- ✅ **Intelligente Dokumenten-Klassifizierung** - Automatische Typ-Erkennung
- ✅ **DocBox API Integration** - Nahtlose Dokumenten-Übertragung
- ✅ **PostgreSQL Anbindung** - Direkte Hapak-Datenbank-Integration
- ✅ **Background Services** - Zuverlässige Windows-Dienste
- ✅ **Lizenzverwaltung** - Sichere Authentifizierung und Validierung

### Zusätzliche Features
- 🔄 **Automatische Updates** - GitHub-basierte Update-Mechanismen
- 📊 **Monitoring & Logging** - Umfassende Diagnose-Möglichkeiten
- 🛡️ **Sicherheit** - Verschlüsselte Konfiguration und Kommunikation
- 🎛️ **Professionelle UI** - Moderne Windows Forms Anwendung
- 📱 **Responsive Design** - Optimierte Benutzeroberfläche

## 📋 Systemvoraussetzungen

- **Betriebssystem:** Windows 10/11 (64-bit)
- **.NET Runtime:** .NET 8.0 Desktop Runtime
- **Arbeitsspeicher:** Mindestens 4 GB RAM
- **Festplattenspeicher:** 500 MB freier Speicher
- **Netzwerk:** Internetzugang für Updates und DocBox-API

## 🛠️ Installation

### Automatische Installation
1. Laden Sie die neueste Version von [GitHub Releases](https://github.com/wkw2k/HDC-Hapak-Docbox-R--Connector/releases) herunter
2. Führen Sie `HDC-Setup-[Version].exe` als Administrator aus
3. Folgen Sie dem Installationsassistenten

### Manuelle Installation (Entwicklung)
```bash
# Repository klonen
git clone https://github.com/wkw2k/HDC-Hapak-Docbox-R--Connector.git
cd HDC-Hapak-Docbox-R--Connector

# Abhängigkeiten wiederherstellen
dotnet restore

# Projekt bauen
dotnet build --configuration Release

# Services installieren
sc create "HDC FileUploadWorker" binPath="path\to\FileUploadWorker.exe"
sc create "HDC ProjectCreationWorker" binPath="path\to\ProjectCreationWorker.exe"
```

## ⚙️ Konfiguration

Nach der Installation die Konfiguration unter `C:\ProgramData\Hapak-DocBox(R)-Connector\config.json` anpassen:

```json
{
  "HapakDatabase": {
    "ServerAddress": "hapak-server.company.local",
    "Port": 5432,
    "DatabaseName": "hapak_prod",
    "UserName": "hapak_user",
    "Password": "encrypted_password"
  },
  "DocBoxServer": {
    "Protocol": "https",
    "ServerAddress": "docbox.company.local",
    "Port": 8081,
    "ParentFolderId": "3078",
    "MandatorName": "COMPANY",
    "ApiKey": "encrypted_api_key"
  },
  "FileImport": {
    "HotFolder": "C:\\HDC\\HotFolder",
    "CompletedImportFolder": "C:\\HDC\\Processed",
    "FallbackFolderId": "12345",
    "IntervalOperation": true,
    "FileImportInterval": 30
  }
}
```

## 🎯 Verwendung

### Erste Schritte
1. **Anwendung starten** - HDC über das Startmenü öffnen
2. **Lizenz laden** - Über "Lizenz einlesen" eine gültige Lizenz importieren
3. **Konfiguration prüfen** - Unter "Datei → Einstellungen" alle Verbindungen testen
4. **Services starten** - Worker-Dienste über die UI oder `services.msc` starten

### Dateiverarbeitung
Dateien im HotFolder werden automatisch verarbeitet:
- **Dateiname-Format:** `{DocType}_{Projekt}_{Jahr}.pdf`
- **Beispiele:**
  - `RG_20250113_ABC123_Project.pdf` → Rechnung
  - `LS_20250113_ABC123_Project.pdf` → Lieferschein
  - `AN_20250113_ABC123_Project.pdf` → Angebot

### Monitoring
- **Dashboard** - Übersicht über alle Service-Status
- **Logs** - Detaillierte Diagnose unter `C:\ProgramData\Hapak-DocBox(R)-Connector\Logs\`
- **Event Viewer** - Windows System-Events für Service-Diagnose

## 🏗️ Architektur

```
HDC Solution
├── HDC.MainApp/           # Windows Forms UI
│   ├── Views/            # Dashboard, Settings, etc.
│   └── Forms/            # Dialoge und Formulare
├── HDC.Services/         # Business Logic
│   ├── ConfigService     # Konfigurations-Management
│   ├── DocBoxService     # DocBox API Client
│   ├── HapakService      # PostgreSQL Client
│   ├── LicenseService    # Lizenz-Validierung
│   └── UpdateService     # Auto-Updates
├── HDC.Models/           # Datenmodelle
├── HDC.Common/           # Gemeinsame Utilities
├── HDC.FileUploadWorker/ # Datei-Upload Service
├── HDC.ProjectCreationWorker/ # Projekt-Erstellung Service
└── HDC.LicenseGenerator/ # Lizenz-Tool
```

## 🔧 Entwicklung

### Voraussetzungen
- Visual Studio 2022 oder neuer
- .NET 8.0 SDK
- Git

### Setup
```bash
# Repository klonen
git clone https://github.com/wkw2k/HDC-Hapak-Docbox-R--Connector.git
cd HDC-Hapak-Docbox-R--Connector

# Abhängigkeiten installieren
dotnet restore

# Projekt öffnen
start HDC.slnx
```

### Build & Test
```bash
# Gesamtlösung bauen
dotnet build HDC.slnx

# Tests ausführen
dotnet test HDC.slnx

# Release bauen
.\build-release.ps1 -Version "1.0.0" -Beta
```

## 📚 Dokumentation

- **[Vollständige Dokumentation](https://wkw2k.github.io/HDC-Hapak-Docbox-R--Connector/)** - Online über GitHub Pages
- **Installation** - Schritt-für-Schritt Anleitungen
- **Konfiguration** - Detaillierte Parameter-Referenz
- **Problembehebung** - Häufige Fehler und Lösungen

## 🤝 Beitragen

Beiträge sind willkommen! Bitte:

1. Fork das Repository
2. Erstelle einen Feature-Branch (`git checkout -b feature/AmazingFeature`)
3. Commit deine Änderungen (`git commit -m 'Add some AmazingFeature'`)
4. Push zum Branch (`git push origin feature/AmazingFeature`)
5. Öffne einen Pull Request

### Entwicklungsrichtlinien
- Verwende beschreibende Commit-Nachrichten
- Füge Tests für neue Features hinzu
- Aktualisiere die Dokumentation bei API-Änderungen
- Folge dem bestehenden Code-Style

## 🐛 Fehlerberichte

Bei Fehlern oder Problemen:
1. Überprüfe die [Problembehebung](https://wkw2k.github.io/HDC-Hapak-Docbox-R--Connector/troubleshooting.html)
2. Schaue in die Log-Dateien unter `C:\ProgramData\Hapak-DocBox(R)-Connector\Logs\`
3. Erstelle ein [GitHub Issue](https://github.com/wkw2k/HDC-Hapak-Docbox-R--Connector/issues)

## 📄 Lizenz

Dieses Projekt steht unter der **MIT License** - siehe die [LICENSE](LICENSE) Datei für Details.

## 👨‍💻 Autor

**wkw2k**
- Website: [www.wkw2k.de](https://www.wkw2k.de)
- E-Mail: [support@wkw2k.de](mailto:support@wkw2k.de)

## 🙏 Danksagungen

- Microsoft für die .NET Plattform
- Die Open-Source Community für die vielen Libraries
- Alle Tester und Early Adopter für ihr Feedback

---

**HDC** - Professionelle Dokumenten-Integration für moderne Unternehmen 🚀