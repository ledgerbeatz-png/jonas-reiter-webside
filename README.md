# Jonas Reiter – Autorenseite zu *Der Stream*

Statische Website (HTML/CSS, kein JavaScript) für den Thriller **Der Stream** von Jonas Reiter. Keine Tracker, keine Cookies, keine externen Schrift-CDNs. Schriften liegen im Ordner `fonts/` (SIL Open Font License).

## Amazon-Links ersetzen

Solange das eBook bei KDP noch geprüft wird und die Produktseiten keine ASIN haben, führen alle Kauf-Buttons auf die Amazon-Suche:

```
https://www.amazon.de/s?k=Der+Stream+Jonas+Reiter
```

**Diese Links müssen ersetzt werden, sobald die ASINs feststehen.**

Suchen Sie im Projekt nach der Markierung:

- HTML-Kommentar: `AMAZON-LINK-PLACEHOLDER`
- CSS-Klasse / Hook: `js-amazon-link`

Betroffene Dateien und Stellen:

| Datei            | Stelle                                      | Empfohlenes Ziel                         |
| ---------------- | ------------------------------------------- | ---------------------------------------- |
| `index.html`     | Hero-Button „Bei Amazon kaufen“             | eBook- oder gemeinsame Produktseite      |
| `index.html`     | Karte „eBook bei Amazon“                    | `https://www.amazon.de/dp/ASIN-EBOOK`    |
| `index.html`     | Karte „Taschenbuch bei Amazon“              | `https://www.amazon.de/dp/ASIN-TASCHENBUCH` |
| `leseprobe.html` | Button „Weiterlesen bei Amazon“             | eBook- oder Taschenbuch-ASIN             |
| `autor.html`     | Button „Bei Amazon kaufen“                  | wie Startseite                           |

Die ISBN des Taschenbuchs lautet **979-8-1458-5611-8** (KDP: `9798145856118`). Sie ist nicht automatisch die Amazon-ASIN.

Nach dem Austauschen den Hinweistext „Derzeit in Prüfung bei Amazon. Link führt vorerst zur Suche.“ auf der Startseite entfernen oder anpassen.

## Open-Graph-URL

In allen HTML-Dateien steht vor dem ersten Deploy der Platzhalter

```
https://jonas-reiter.onrender.com
```

in `canonical`, `og:url`, `og:image`, `twitter:image` und im JSON-LD. Nach dem Live-Gang durch die echte Origin ersetzen (ohne abschließenden Schrägstrich), z. B. `https://jonas-reiter.onrender.com`.

## Lokal ansehen

Die Seite ist rein statisch. Im Projektordner zum Beispiel:

```bash
python3 -m http.server 8080
```

Dann http://127.0.0.1:8080 öffnen.

## Deploy

Bevorzugt: **Render Static Site** (kostenlos, `*.onrender.com`).

Die Datei `render.yaml` beschreibt den Dienst:

- Build-Befehl: `true` (nichts zu bauen)
- Veröffentlichungsverzeichnis: `.`

Voraussetzung ist ein öffentliches GitHub-Repository, das Render lesen kann. Alternativ: GitHub Pages aus demselben Repository.

## Inhalte

- Startseite: Cover, Klappentext, Buchdaten, Kauf-Buttons, Autorenblock
- Leseprobe: die ersten 2028 Wörter von Kapitel 1 (bis zur ersten Zäsur nach dem dritten Namen)
- Autorenseite: kurzer, nicht erfundener Text plus Autorenfoto
- Impressum (§ 5 DDG) und Datenschutzerklärung

## Lizenz der Website-Datei

Der Text von *Der Stream* und das Cover unterliegen dem Urheberrecht des Autors. Die eingebetteten Schriften stehen unter der SIL Open Font License, siehe `fonts/LICENSES.txt`.
