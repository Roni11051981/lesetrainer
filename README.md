# Lese-Trainer

Statische Web-App für Kinder ab ca. 10 Jahren (läuft auf GitHub Pages, kein Server, keine API-Schlüssel):

- **Blitz** – Blitzwörter: ein Wort blitzt kurz auf, Antwort per Mikrofon oder Tippen.
- **Reader** – RSVP-Schnelllesen (ein Wort nach dem anderen am Fixpunkt), .txt/.epub oder eingefügter Text.
- **Lesen** – Text selber laut lesen (Spracherkennung markiert mit) oder vorlesen lassen, mit Verständnisfrage pro Absatz.

## Stimmausgabe

- Web Speech API; die beste deutsche Stimme wird automatisch gewählt (Microsoft „Online (Natural)“, Google, Apple Premium/Enhanced bevorzugt), alle deutschen Stimmen sind im Menü nach Qualität gruppiert.
- Tempo und Tonhöhe sind einstellbar und werden im Browser gespeichert.
- Vorgelesen wird satzweise mit Pause/Weiter/Nächster Satz/Stopp; das aktuelle Wort wird im Text markiert.
- **Offline-Stimme (Beta):** optional zuschaltbare Piper-Neuralstimme per WebAssembly (`@mintplex-labs/piper-tts-web`, Modell wird einmal geladen und wiederverwendet), läuft in einem Web Worker. Wird erst beim Einschalten geladen (Eva 21 MB, Thorsten/Kerstin 63 MB, plus ca. 30 MB Laufzeit; danach im Browser gespeichert).

## Bibliothek

- `texte/` enthält den mitgelieferten Textbestand (Märchen, Sagen, Fabeln, Abenteuer, Sachtexte, Geschichten; 120–250 Wörter, CC0 – eigene Nacherzählungen gemeinfreier Stoffe und eigene Texte, siehe `texte/LIZENZ.md`). Neue Texte: `.txt` ablegen und in `texte/index.json` eintragen.
- **Klexikon-Suche** (optional, braucht Internet): holt den Anfang eines Artikels aus dem freien Kinderlexikon klexikon.zum.de über die MediaWiki-API (anonym, `origin=*`). Quelle und Lizenz (CC BY-SA 4.0) werden angezeigt. Ist der Server nicht erreichbar, erscheint ein Hinweis; die mitgelieferten Texte funktionieren auch offline.

Die App besteht aus `index.html` und dem Ordner `texte/`; Einstellungen, Verlauf und Texte bleiben im `localStorage`.
