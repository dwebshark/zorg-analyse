# Dutchwebshark rapportageomgeving

Deze repository bevat interactieve rapportages van [Dutchwebshark](https://dutchwebshark.com), opgebouwd als zelfstandige HTML-pagina's voor webpublicatie en PDF-export.

## Beschikbare rapportagepagina's

| Rapportage | Lokale route | Publieke versie | Bestand |
| --- | --- | --- | --- |
| Wervingsanalyse Zorgmarkt Nederland | [`/zorg-analyse.html`](http://localhost:8000/zorg-analyse.html) | [Zorgrapportage](https://dutchwebshark.com/zorg-analyse/) | `www/zorg-analyse.html` |
| Werving & Selectie Benchmark 2026 | [`/werving-benchmark-2026.html`](http://localhost:8000/werving-benchmark-2026.html) | Nog niet gepubliceerd (featurebranch) | `www/werving-benchmark-2026.html` |

## Lokaal starten

Er is geen buildstap nodig. Start vanuit de hoofdmap van de repository een statische webserver:

```bash
python3 -m http.server 8000 -d www
```

Open daarna [Zorg Analyse](http://localhost:8000/zorg-analyse.html) of [Werving & Selectie Benchmark 2026](http://localhost:8000/werving-benchmark-2026.html). Voor de externe CSS-, lettertype-, grafiek- en kaartbronnen is een internetverbinding nodig.

## Opslaan als PDF

1. Open de gewenste rapportagepagina in de browser.
2. Kies **Afdrukken** (`Ctrl+P` of `Cmd+P`).
3. Selecteer **Opslaan als PDF**.
4. Gebruik voor **Zorg Analyse** papierformaat **A4**, oriëntatie **Staand**, marges **Geen**. De benchmarkpresentatie gebruikt een eigen **16:9-landscape** printopmaak; laat de paginagrootte daarvoor bij voorkeur door de browser/CSS bepalen. Schakel **Achtergrondafbeeldingen** in als de browser daar een aparte optie voor toont.
5. Sla de PDF op.

## Hosting en insluiten

De repository bevat `CNAME` met `reports.dutchwebshark.com`. Controleer de actieve hosting-/publicatie-instellingen voordat je een nieuw bestand op dat subdomein verwacht. Na deployment vanuit de juiste publicatiemap is de beoogde URL voor de benchmark `https://reports.dutchwebshark.com/werving-benchmark-2026.html`.

De benchmark is één zelfstandige HTML-pagina met 12 slides en kan na publicatie via een iframe op de website worden ingesloten. De huidige HTML bevat nog geen automatische iframe-hoogtekoppeling; geef het iframe voorlopig een passende vaste hoogte of voeg later een gecontroleerde `postMessage`-resizekoppeling toe. De bestaande Zorg Analyse-pagina heeft al een resizebericht voor de WordPress-integratie.
