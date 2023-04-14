# ASV-BW Schul-Account-Manager Installer (asvsam/asvsam-installer)

[//]: # (```)

[//]: # (          d8888  .d8888b.  888     888  .d8888b.        d8888 888b     d888)

[//]: # (         d88888 d88P  Y88b 888     888 d88P  Y88b      d88888 8888b   d8888)

[//]: # (        d88P888 Y88b.      888     888 Y88b.          d88P888 88888b.d88888)

[//]: # (       d88P 888  "Y888b.   Y88b   d88P  "Y888b.      d88P 888 888Y88888P888)

[//]: # (      d88P  888     "Y88b.  Y88b d88P      "Y88b.   d88P  888 888 Y888P 888)

[//]: # (     d88P   888       "888   Y88o88P         "888  d88P   888 888  Y8P  888)

[//]: # (    d8888888888 Y88b  d88P    Y888P    Y88b  d88P d8888888888 888   "   888)

[//]: # (   d88P     888  "Y8888P"      Y8P      "Y8888P" d88P     888 888       888)

[//]: # ()
[//]: # ( :: ASV-BW Schul-Account-Manager &#40;Asvsam&#41; ::)

[//]: # (```)
![Logo.png](src/main/docu/assets/Logo.png)

Der ASV-SAM-Installer dient der Vereinfachung der Installation von ASV-SAM (ASV-BW Schul-Account-Manager) durch die System-Administratoren.
Alle erforderlich installationsvorbereitenden Schritte werden automatisch durchgeführt.
Für die Systemseite-Konfiguration steht eine Benutzeroberfläche zur Verfügung, wodurch auf tiefere technische 
Kenntnisse (Z.B. von Docker) weitgehend verzichtet werden kann.


[//]: [![Pulls](https://img.shields.io/docker/pulls/asvsam/asvsam?label=DockerHub%20Pulls&logo=Docker&style=plastic)]([gh_asvsam_asvsaminstaller_issues])

[![Issues](https://img.shields.io/github/issues/asvsam/asvsam?label=Issues&logo=GitHub&style=plastic)]([gh_asvsam_asvsaminstaller_issues])



[//]: # (## Inhalt)

[//]: # (***)

[//]: # (1. [Voraussetzungen / System Anforderungen]&#40;#Voraussetzungen-/-System-Anforderungen&#41;)

[//]: # (2. [Verwendung des ASV-SAM-Installers]&#40;#Verwendung-des-ASV-SAM-Installers&#41;)

[//]: # (3. [Installation]&#40;#installation&#41;)

[//]: # (4. [Hilfe]&#40;#hilfe&#41;)

[//]: # (4. [Links]&#40;#links&#41;)

[//]: # (5. [FAQs]&#40;#faqs&#41;)

## Voraussetzungen / System Anforderungen

### Unterstützte Betriebsysteme (Linux):
- [Debian 11 (bullseye)][debian_bullseye]
- [Ubuntu Server 22.04 LTS (Jammy Jellyfish)][ubuntu_jammy]

### Systemanforderungen:
- Linux-System basierend auf der 64-bit PC (amd64) Systemarchitektur
- moderne CPU mit min. 2 Cores
- min. 4 GB RAM
- ca. 1GB verfügbarer Speicher auf der Festplatte
- Internetverbindung (GitHub und DockerHub, sowie System-Repositories für Debian oder Ubuntu)

### Sonstige Anforderungen:
- Normaler Benutzer mit Sudo-Rechten (Kein root Benutzer) und Zugriff auf das System

### Optionale Anforderungen:
- SMTP-Mail-Server für den Versand von E-Mails aus dem System heraus.
- ASV-BW DB-Zugriff zur automatisierten Datenübernahme
- WebUntis-API-Zugriff für den automatisieren Datenexport nach WebUntis
- PaedMl-Zugriff für den automatisieren Datenexport nach PaedMl


## Verwendung des ASV-SAM-Installers

### Initiale Ausführung

Für die initiale Installation von ASV-SAM unter Verwendung des ASV-SAM-Installer führen sie einen der folgenden Befehle auf der Konsole aus:

| :exclamation: :exclamation: :exclamation:  **_Wichtiger Hinweis_**                                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dieses Vorgehen ist **_ausschließlich_** für die Erst-Installation (initiale) auf einem System vorgesehen. Andernfalls siehe [Verwendung im Betrieb oder nach Erstinstallation](#Verwendung-im-Betrieb-oder-nach-Erstinstallation) |


Installation mit curl (Empfohlen):
```shell
curl -fsSL https://raw.githubusercontent.com/asvsam/asvsam-installer/master/installer.sh \
    | sh -s -- --skip-signature-validation
```
Installation mit wget:
```shell
wget -nv -O - https://raw.githubusercontent.com/asvsam/asvsam-installer/installer.sh \
    | sh -s -- --skip-signature-validation
```

### Verwendung im Betrieb oder nach Erstinstallation

Für die Verwendung des Installers im Betrieb oder nach der Erstinstallation führen sie den folgenden Befehl auf der Konsole aus:

Setup-Tool (Aufruf des Setup-Tools. Eine Überprüfung, bzw. Aktualisierung der Installation kann über die GUI erfolgen):
```shell
/opt/asvsam/setup.sh
```

## Changelog & Releases

Dieses Repository trackt Änderungen unter Verwendung der [GitHub's releases][gh_asvsam_asvsaminstaller_releases] Funktionalität.

Releases basieren auf einer Versionierung im [Semantic Versioning][semver] Format, ala `MAJOR.MINOR.PATCH`.

Version werden unter Verwendung folgender Regeln fortgeschrieben:
* `MAJOR`: Inkompatibel oder große Änderungen
* `MINOR`: Abwärtskompatibilität gegeben und neue Funktionen und Verbesserungen
* `PATCH`: Abwärtskompatibilität gegeben und Fehlerbehebung, sowie kleinere Verbesserungen und neue Funktonen


## FAQs

1. **Ist es möglich die installation mit einem root-Benutzer durchzuführen:**

   Die installation mit dem root-Benutzer wird nicht empfohlen und, daher auch nicht unterstützt. 
Bitte legen Sie mit dem root-Benutzer einen anderen Benutzer an und berechtigen Sie diesen via sudo.
Dieser Benutzer kann dann für die Installation verwendet werden.

[//]: # (2. **ddd**)
[//]: # ()
[//]: # (   ddd)

## Links

### ASV-SAM-Installer
- [ASV-SAM-Installer GitHub-Seite][gh_asvsam_asvsaminstaller]
- [ASV-SAM-Installer Bug-Tracker][gh_asvsam_asvsaminstaller_issues]
- [ASV-SAM-Installer Wiki][gh_asvsam_asvsaminstaller_wiki]
- [ASV-SAM-Installer Releases][gh_asvsam_asvsaminstaller_releases]

### ASV-SAM
- [ASV-SAM GitHub][gh_asvsam_asvsam]
- [ASV-SAM Docker-Hub][dh_asvsam_asvsam]

[//]: # (## Lizenz)

[//]: # (***)

[//]: # ()
[//]: # ([![License]&#40;https://img.shields.io/badge/License-Apache%202.0-blue?style=for-the-badge&cacheSeconds=3600&#41;]&#40;opensource_license&#41;)

[//]: # ()
[//]: # (Licensed under the Apache License, Version 2.0.)

[//]: # (See [LICENSE]&#40;LICENSE&#41; file.)



<!-- Links definieren -->
[gh_asvsam_asvsaminstaller]: https://github.com/asvsam/asvsam-installer
[gh_asvsam_asvsaminstaller_issues]: https://github.com/asvsam/asvsam-installer/issues
[gh_asvsam_asvsaminstaller_wiki]: https://github.com/asvsam/asvsam-installer/wiki
[gh_asvsam_asvsaminstaller_releases]: https://github.com/asvsam/asvsam-installer/releases
[gh_asvsam_asvsam]: https://github.com/asvsam/asvsam
[gh_asvsam_asvsam_issues]: https://github.com/asvsam/asvsam/issues
[gh_asvsam_asvsam_wiki]: https://github.com/asvsam/asvsam/wiki
[gh_asvsam_asvsam_releases]: https://github.com/asvsam/asvsam/releases
[dh_asvsam_asvsam]: https://hub.docker.com/r/asvsam/asvsam

[//]: # ([opensource_license]: https://opensource.org/licenses/Apache-2.0)

[debian_bullseye]: https://www.debian.org/releases/bullseye/
[ubuntu_jammy]: https://releases.ubuntu.com/jammy

[semver]: https://semver.org/