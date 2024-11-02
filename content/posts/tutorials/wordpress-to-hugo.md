---
date: '2024-10-30T09:10:00+01:00'
draft: true
title: 'Von Wordpress zu Hugo'
tags: [Tutorials, Wordpress, Hugo]
categories: ["Tutorials"]
---

Die Entscheidung, von WordPress zu Hugo zu wechseln, bringt eine Menge Flexibilität und Geschwindigkeit mit sich. Falls du deine bestehenden WordPress-Posts auf Hugo übertragen möchtest, hilft dir diese Schritt-für-Schritt-Anleitung dabei, die Migration möglichst einfach und reibungslos zu gestalten. 

## Schritt 1: Export der WordPress-Posts

Der einfachste Weg, WordPress-Posts für Hugo zu exportieren, ist das Plugin **WordPress to Hugo Exporter**. Es wandelt die Posts und Seiten automatisch in Markdown-Dateien mit YAML-Frontmatter um, die Hugo-kompatibel sind.

- Installiere und aktiviere das Plugin „[WordPress to Hugo Exporter](https://github.com/SchumacherFM/wordpress-to-hugo-exporter)“ in deinem WordPress-Dashboard.
- Gehe zu **Werkzeuge > Hugo Export**.
- Das Plugin erstellt eine ZIP-Datei, die alle Posts und Seiten im Markdown-Format enthält. Lade diese ZIP-Datei herunter und entpacke sie auf deinem Computer.

## Schritt 2: Dateien in Hugo importieren

Nachdem du die ZIP-Datei entpackt hast, findest du deine WordPress-Posts als `.md`-Dateien, die mit YAML-Frontmatter versehen sind und direkt in Hugo verwendet werden können.

- Öffne das Verzeichnis deines Hugo-Projekts und navigiere in den `content`-Ordner.
- Kopiere alle entpackten `.md`-Dateien in diesen `content`-Ordner.
- Falls du eine bestimmte Ordnerstruktur (z. B. Kategorien oder Jahre) in WordPress hattest, kannst du diese Struktur auch im `content`-Ordner deines Hugo-Projekts nachbilden.

## Schritt 3: Medien und Bilder migrieren

Die Markdown-Dateien enthalten nur den Text und die Struktur der Posts – Bilder und andere Medien müssen separat übertragen werden:

- Kopiere den `uploads`-Ordner aus deinem WordPress-Verzeichnis (meistens in `wp-content/uploads`) in den `static`-Ordner deines Hugo-Projekts.
- Falls du absolute URLs zu Bildern und anderen Medien verwendest, passe die Pfade in den Markdown-Dateien an, damit sie auf die neue Medienstruktur im `static`-Ordner verweisen.

## Schritt 4: Beiträge anpassen und überprüfen

Öffne einige der übertragenen `.md`-Dateien, um sicherzustellen, dass alle Metadaten im YAML-Frontmatter stimmen. Typische Anpassungen könnten sein:

- Korrektur von `categories`, `tags`, und anderen spezifischen Feldern im Frontmatter.
- Falls Beiträge als „Entwurf“ markiert sind, setze `draft: false`, damit sie veröffentlicht werden.

## Schritt 5: Hugo-Server starten und Migration testen

Starte den Hugo-Server, um deine Webseite zu überprüfen:

```bash
hugo server
