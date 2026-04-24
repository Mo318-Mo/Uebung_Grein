# GitHub – Übersicht & Projektmanagement

## 🌐 GitHub Pages

GitHub Pages ermöglicht es, direkt aus einem Repository eine Website zu erstellen.

### 🔧 Grundlagen

* Erstellung von Webseiten direkt aus einem Projekt oder einer Organisation
* Inhalte werden meist in **Markdown (.md)** geschrieben
* Aktivierung unter:
  `Settings → Pages`
* Auswahl von:

  * Branch (z. B. `main`)
  * Ordner (z. B. `/docs`)

### 📌 Eigenschaften

* Teil des Repositories
* Ideal für:

  * Dokumentation
  * Projektbeschreibungen
  * öffentliche Infos

### 🛠️ Beispiel mit MkDocs

```bash
pip install mkdocs mkdocs-material
mkdocs new .
mkdocs serve        # lokale Vorschau auf localhost:8000
mkdocs build        # generiert /site Ordner
mkdocs gh-deploy    # Deployment auf GitHub Pages
```

Danach:

* `Settings → Pages`
* Branch: `gh-pages`
* Ordner: `/ (root)`

---

## 📚 Wiki Pages

### Eigenschaften

* Kein Markdown-Wissen notwendig
* Direkt in GitHub integriert
* Kein Setup erforderlich

### 👍 Gut geeignet für:

* interne Notizen
* Team-Dokumentation
* How-Tos

### 👎 Nachteile

* Kein eigenes Design
* Kein Deployment über GitHub Actions

---

# 🛠️ Projektmanagement mit GitHub

## 🐞 Issues & Labels

Dienen zur Aufgabenverwaltung.

### Funktionen:

* Labels vergeben (z. B. `bug`, `documentation`)
* Meilensteine definieren
* Aufgaben Personen zuweisen

### 🔗 Automatisches Schließen

Wenn du in einem Commit schreibst:

```bash
Fixes #1
Closes #1
```

→ wird das Issue automatisch geschlossen

### 💡 Im Code referenzieren

```cpp
// TODO: Workaround Bug #1
// FIXME: siehe Issue #1
```

---

## 🚀 Release Management

* Releases direkt im Repository erstellen
* Versionen mit Labels kennzeichnen
* Überblick über Entwicklungsstand

---

## 👀 Reviews & Code Owners

### Automatische Reviewer

Datei `.github/CODEOWNERS` erstellen:

```txt
*       @global-owner        # für alle Dateien
/docs/  @docs-team          # für /docs
*.py    @python-dev         # für Python-Dateien
```

---

## 💬 Discussions

* Muss unter `Settings → General` aktiviert werden
* Besonders nützlich für:

  * Open Source Projekte
  * Community-Austausch

---

## 🏢 Organizations

### Vorteile:

* Gemeinsame Repositories
* Teams & Rollenverwaltung:

  * Lesen
  * Schreiben
  * Admin

### Zentrale Verwaltung:

* Einstellungen
* Integrationen
* Secrets (z. B. API-Keys)
* CI/CD Workflows

---

## 📊 Projects

GitHub Projects bietet klassische Projektmanagement-Funktionen:

### Funktionen:

* Bugtracking
* Feature-Verwaltung
* Priorisierung
* Aufgaben-Zuordnung

### Vorteile:

* Verknüpft mit:

  * Issues
  * Pull Requests
  * Repositories
* Integration mit GitHub Actions
* Alles an einem Ort

---

## 🔐 Sicherheit & Compliance

### 🤖 Dependabot

* Automatische Updates für Abhängigkeiten
* Erkennt Sicherheitslücken

Beispiel (`.github/dependabot.yml`):

```yaml
version: 2
updates:
  - package-ecosystem: "pip"
    directory: "/"
    schedule:
      interval: "weekly"
```

---

### 🔍 CodeQL

* Semantische Codeanalyse
* Unterstützt viele Programmiersprachen

### Erkennt:

* Sicherheitslücken (z. B. SQL Injection)
* Hardcoded Secrets (Passwörter, API-Keys)
* Schlechte Codequalität:

  * Unreachable Code
  * Zyklische Abhängigkeiten

---
