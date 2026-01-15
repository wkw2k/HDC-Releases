# HDC - Hapak-DocBox-Connector

[![.NET Version](https://img.shields.io/badge/.NET-8.0-blue.svg)](https://dotnet.microsoft.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![GitHub release](https://img.shields.io/github/release/wkw2k/HDC-Releases.svg)](https://github.com/wkw2k/HDC-Releases/releases/)

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
1. Laden Sie die neueste Version von [GitHub Releases](https://github.com/wkw2k/HDC-Releases/releases) herunter
2. Führen Sie `HDC-Setup-[Version].exe` als Administrator aus
3. Folgen Sie dem Installationsassistenten



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



## 📚 Dokumentation

Die vollständige Dokumentation finden Sie online: **[HDC Dokumentation](https://wkw2k.github.io/HDC-Releases/)**



## 🆘 Support

Bei Fragen oder Problemen:
- Überprüfen Sie die [vollständige Dokumentation](https://wkw2k.github.io/HDC-Releases/)
- Log-Dateien finden Sie unter `C:\ProgramData\Hapak-DocBox(R)-Connector\Logs\`
- Kontakt: [support@wkw2k.de](mailto:support@wkw2k.de)

## 📄 Lizenz

Dieses Projekt steht unter der **MIT License** - siehe die [LICENSE](LICENSE) Datei für Details.



---

**HDC** - Professionelle Dokumenten-Integration für moderne Unternehmen 🚀