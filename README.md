# Yupana für Claude

Erklärt Ihre BWA (die betriebswirtschaftliche Auswertung Ihrer Kanzlei) in Klartext, stellt sie neben die
Branchenwerte der Deutschen Bundesbank und prüft USt-IdNr., IBAN und E-Rechnungen — direkt im Gespräch mit Claude.

## Was drin ist

| Teil | Wofür |
|---|---|
| Skill `bwa-erklaeren` | Liest eine BWA als PDF mit einem mitgelieferten Skript und gliedert die Antwort: Überblick, wesentliche Zeilen, Branchenlage, Warnsignale, Fragen an die Kanzlei, Quelle |
| Server `yupana` (`https://mcp.yupana.de/mcp`) | Werkzeuge ohne Anmeldung: BWA erklären, Branchenwerte, Wirtschaftszweig suchen, USt-IdNr. (Format und amtlich), IBAN, E-Rechnung lesen, Upload-Link |
| Server `yupana-konto` (`https://mcp.yupana.de/mcp/konto`) | Mit Ihrem Yupana-Konto, nur lesend: Kennzahlen Ihrer Firma, Bankverbindungen Ihrer Lieferanten prüfen. Die Anmeldung läuft über `app.yupana.de/verbinden`; zum Ausprobieren gibt es dort die Beispielfirma |

## Installieren

In Claude Code:

```
/plugin marketplace add Jens-KI-007/yupana-claude-plugin
/plugin install yupana@yupana
```

In claude.ai verbinden Sie den Server unter Einstellungen → Konnektoren mit der Adresse `https://mcp.yupana.de/mcp`
(und für Ihre eigenen Zahlen `https://mcp.yupana.de/mcp/konto`).

Schritt für Schritt mit Bildern für Claude, Microsoft 365 Copilot und ChatGPT:
https://www.yupana.de/docs/ki-assistent

## Daten

Die Werkzeuge ohne Anmeldung verarbeiten Ihre Eingaben nur für die jeweilige Antwort. Die Branchenwerte stammen aus der Fachreihe
„Jahresabschlussstatistik“ der Deutschen Bundesbank, die USt-Prüfung fragt BZSt bzw. VIES. Datenschutz:
https://www.yupana.de/datenschutz

## Anbieter

frag.hugo Informationssicherheit GmbH, Spaldingstraße 64-68, 20097 Hamburg · https://www.yupana.de · info@yupana.de

Lizenz: MIT (`LICENSE`).
