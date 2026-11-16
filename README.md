# Grimoire — D&D 5e Character Manager

Eine statische, deutschsprachige Web-App für GitHub Pages. Kein Build-Schritt, kein Backend und keine API-Schlüssel nötig.

## Funktionen

- Mehrere Charaktere lokal verwalten
- Charakterbogen mit Attributen, Modifikatoren, Übungsbonus, Rettungswürfen, Fertigkeiten, Kampf- und Zauberwerten
- Regelbibliothek für Spezies, Klassen, Unterklassen, Hintergründe, Talente, Zauber, Gegenstände, optionale Features und Klassenfeatures
- Quellen einzeln aktivieren/deaktivieren
- 5e.tools-Homebrew-Repository durchsuchen und Werke aktivieren
- Eigene Homebrew-JSON-Dateien und Raw-URLs importieren
- Details zu Inhalten anzeigen, Charaktere importieren/exportieren, Bogen drucken/PDF
- Hell-/Dunkelmodus, responsiv für Desktop, Tablet und Smartphone

## GitHub Pages veröffentlichen

1. Erstelle auf GitHub ein neues Repository, z. B. `grimoire-5e`. Für eine öffentliche GitHub-Free-Site muss das Repository öffentlich sein.
2. Lade den gesamten Inhalt dieses Ordners in den **Root** des Repositorys hoch. Wichtig: `index.html` muss direkt im Root liegen.
3. Öffne im Repository **Settings → Pages**.
4. Stelle bei **Build and deployment → Source** `GitHub Actions` ein.
5. Öffne den Tab **Actions**. Der Workflow `Deploy Grimoire to GitHub Pages` wird beim Push auf `main` automatisch ausgeführt.
6. Nach erfolgreichem Lauf findest du die Website unter `https://DEIN-NUTZERNAME.github.io/REPOSITORY-NAME/`.

Bei einem Repository mit dem Namen `DEIN-NUTZERNAME.github.io` liegt die Seite direkt unter `https://DEIN-NUTZERNAME.github.io/`.

## Lokal testen

`index.html` im Browser öffnen. Für zuverlässige Datenabfragen ist ein lokaler Webserver empfehlenswert, z. B.:

```bash
python -m http.server 8000
```

Dann `http://localhost:8000` öffnen.

## Datenquellen und Hinweise

- Standard-Datenbasis: `5etools-mirror-3/5etools-src` (Raw GitHub JSON).
- Homebrew-Katalog: `TheGiddyLimit/homebrew` (GitHub API + Raw-Dateien).
- Die Daten werden zur Laufzeit im Browser geladen. Internetverbindung erforderlich.
- Manche Browser/Netzwerke können externe Anfragen blockieren oder durch CORS einschränken. In dem Fall in **Einstellungen** eine kompatible Raw-JSON-Datenbasis verwenden.
- Homebrew-Repository-Dateien können sehr umfangreich sein. Lade nur Werke, die du wirklich brauchst.
- Charaktere und Einstellungen werden nur lokal im Browser (`localStorage`) gespeichert. Sie synchronisieren sich nicht automatisch zwischen Geräten. Nutze regelmäßig **Alle Charaktere exportieren** als Backup.
- Die App ist ein Fan-Projekt und nicht mit Wizards of the Coast oder 5e.tools verbunden. D&D-Regeltexte sind nicht in diesem Repository gebündelt.

## Bekannte Grenzen

Diese Version ist ein Charaktermanager und Regelbibliothek, keine vollständige Regel-Engine. Sie berechnet allgemeine Attributsmodifikatoren, Übungsbonus und Fertigkeits-/Rettungswurfboni. Sie automatisiert nicht alle Klassenprogressionen, Zauberplätze, Voraussetzungen, Ressourcen, Aktionsökonomie oder Sonderregeln. Klassen-/Zauber-/Ausrüstungsdaten können je nach JSON-Datei unterschiedliche Strukturen haben; deshalb werden Rohdaten zusätzlich in der Detailansicht angezeigt.
