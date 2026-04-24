# GitHub – Übersicht und Projektmanagement

## GitHub Pages

GitHub Pages ermöglicht es, direkt aus einem Repository eine Website zu erstellen.

### Grundlagen

* Erstellung von Webseiten direkt aus einem Projekt oder einer Organisation
* Inhalte werden meist in Markdown (.md) geschrieben
* Aktivierung unter:
  Settings → Pages
* Auswahl von:

  * Branch (z. B. main)
  * Ordner (z. B. /docs)

### Eigenschaften

* Teil des Repositories
* Geeignet für:

  * Dokumentation
  * Projektbeschreibungen
  * Öffentliche Informationen

### Beispiel mit MkDocs

```bash
pip install mkdocs mkdocs-material
mkdocs new .
mkdocs serve        # lokale Vorschau auf localhost:8000
mkdocs build        # generiert /site Ordner
mkdocs gh-deploy    # Deployment auf GitHub Pages
```

Danach:

* Settings → Pages
* Branch: gh-pages
* Ordner: / (root)

---

## Wiki Pages

### Eigenschaften

* Keine Markdown-Kenntnisse notwendig
* Direkt in GitHub integriert
* Kein Setup erforderlich

### Geeignet für

* Interne Notizen
* Team-Dokumentation
* Anleitungen

### Nachteile

* Kein eigenes Design
* Kein Deployment über GitHub Actions

---

# Projektmanagement mit GitHub

## Issues und Labels

Dienen zur Aufgabenverwaltung.

### Funktionen

* Labels vergeben (z. B. bug, documentation)
* Meilensteine definieren
* Aufgaben Personen zuweisen

### Automatisches Schließen

Wenn in einem Commit steht:

```bash
Fixes #1
Closes #1
```

wird das Issue automatisch geschlossen.

### Referenz im Code

```cpp
// TODO: Workaround Bug #1
// FIXME: siehe Issue #1
```

---

## Release Management

* Releases direkt im Repository erstellen
* Versionen mit Labels kennzeichnen
* Überblick über Entwicklungsstand

---

## Reviews und Code Owners

### Automatische Reviewer

Datei .github/CODEOWNERS erstellen:

```txt
*       @global-owner        # gilt für alle Dateien
/docs/  @docs-team          # gilt für /docs
*.py    @python-dev         # gilt für Python-Dateien
```

---

## Discussions

* Muss unter Settings → General aktiviert werden
* Geeignet für:

  * Open Source Projekte
  * Austausch mit der Community

---

## Organizations

### Vorteile

* Gemeinsame Repositories
* Teams und Rollenverwaltung:

  * Lesen
  * Schreiben
  * Admin

### Zentrale Verwaltung

* Einstellungen
* Integrationen
* Secrets (z. B. API-Schlüssel)
* CI/CD Workflows

---

## Projects

GitHub Projects bietet klassische Projektmanagement-Funktionen.

### Funktionen

* Bugtracking
* Feature-Verwaltung
* Priorisierung
* Aufgaben-Zuordnung

### Vorteile

* Verknüpft mit:

  * Issues
  * Pull Requests
  * Repositories
* Integration mit GitHub Actions
* Alles an einem Ort

---

## Sicherheit und Compliance

### Dependabot

* Automatische Updates für Abhängigkeiten
* Erkennt Sicherheitslücken

Beispiel (.github/dependabot.yml):

```yaml
version: 2
updates:
  - package-ecosystem: "pip"
    directory: "/"
    schedule:
      interval: "weekly"
```

---

### CodeQL

* Semantische Codeanalyse
* Unterstützt viele Programmiersprachen

### Erkennt

* Sicherheitslücken (z. B. SQL Injection)
* Hardcoded Secrets (API-Keys, Passwörter)
* Probleme in der Codequalität:

  * Unreachable Code
  * Zyklische Abhängigkeiten

```

---

Wenn du willst, kann ich dir das auch direkt in:
- eine **perfekte Präsentation**
- oder ein **MkDocs-Projekt mit Navigation und Theme**

umwandeln.
```
