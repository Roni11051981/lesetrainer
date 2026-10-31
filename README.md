# Lese-Trainer

Statische Web-App für Kinder ab ca. 10 Jahren (läuft auf GitHub Pages, kein Server, keine API-Schlüssel):

- **Blitz** – Blitzwörter: ein Wort blitzt kurz auf, Antwort per Mikrofon oder Tippen.
- **Reader** – RSVP-Schnelllesen (ein Wort nach dem anderen am Fixpunkt), .txt/.epub oder eingefügter Text.
- **Lesen** – Text selber laut lesen (Spracherkennung markiert mit) oder vorlesen lassen, mit Verständnisfrage pro Absatz.

## Stimmausgabe

- Web Speech API; die beste deutsche Stimme wird automatisch gewählt (Microsoft „Online (Natural)“, Google, Apple Premium/Enhanced bevorzugt), alle deutschen Stimmen sind im Menü nach Qualität gruppiert.
- Tempo und Tonhöhe sind einstellbar und werden im Browser gespeichert.
- Vorgelesen wird satzweise mit Pause/Weiter/Nächster Satz/Stopp; das aktuelle Wort wird im Text markiert.
- **Offline-Stimme (Beta):** optional zuschaltbare Piper-Neuralstimme per WebAssembly (`@diffusionstudio/vits-web`), läuft in einem Web Worker. Wird erst beim Einschalten geladen (Stimmpaket ca. 25–60 MB plus ca. 30 MB Laufzeit, danach im Browser gespeichert).

Alles liegt in `index.html`; Einstellungen, Verlauf und Texte bleiben im `localStorage`.
