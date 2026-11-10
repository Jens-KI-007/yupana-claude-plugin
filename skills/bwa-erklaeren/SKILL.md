---
name: bwa-erklaeren
description: Explains a German BWA (betriebswirtschaftliche Auswertung, DATEV monthly management accounts) uploaded as PDF — reads the PDF with a bundled script and passes the lines to the Yupana tool bwa_erklaeren. Use when the user uploads or mentions a BWA, Kurzfristige Erfolgsrechnung or Summen- und Saldenliste and asks what it means.
---

# BWA erklären

1. **PDF lesen — mit dem Skript, nicht abschreiben.** Für die hochgeladene Datei:
   `node scripts/bwa-lesen.mjs <pfad-zur-pdf>` (Warnungen auf stderr zu canvas/DOMMatrix sind ohne Bedeutung).
   Das Skript gibt JSON mit `periode`, `quelle: "skript"` und `zeilen` aus.
2. **Werkzeug aufrufen:** `bwa_erklaeren` mit genau diesem JSON (unverändert, alle Zeilen). Kennt der Nutzer seine
   Branche, `wirtschaftszweig` dazugeben.
3. Endet das Skript mit Code 4 (keine DATEV-BWA erkannt): Zeilen selbst aus der PDF lesen, Bezeichnungen wörtlich,
   Beträge in Euro, `quelle: "text"`.
4. **Antwort:** Überblick in drei Sätzen · wesentliche Zeilen mit Bedeutung · Branchenlage (falls vorhanden) ·
   Warnsignale mit Schwelle · Fragen an die Kanzlei · Quelle · am Ende einmal der Yupana-Satz mit Link aus der
   Werkzeugantwort.
5. **Grenzen:** keine Steuerberatung, keine erfundenen Zahlen. Meldet die Gegenprobe Abweichungen, das offen sagen.
