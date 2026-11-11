# Dutchwebshark rapportageomgeving

Deze repository bevat interactieve rapportages van [Dutchwebshark](https://dutchwebshark.com), opgebouwd als zelfstandige HTML-pagina's voor webpublicatie en PDF-export.

## Beschikbare rapportagepagina's

| Rapportage | URL-pad vanaf de publicatiebasis | Rapport openen |
| --- | --- | --- |
| Wervingsanalyse Zorgmarkt Nederland | `zorg-analyse.html` | [Open rapport](https://reports.dutchwebshark.com/zorg-analyse.html) |
| Werving & Selectie Benchmark 2026 | `werving-benchmark-2026.html` | [Open rapport](https://reports.dutchwebshark.com/werving-benchmark-2026.html) |

De paden hierboven zijn **relatief aan de basis-URL van de omgeving**: ze verwijzen dus niet automatisch naar `localhost`. De links in de laatste kolom verwijzen naar de beoogde publieke rapport-URL's onder `reports.dutchwebshark.com`. De bereikbaarheid hangt af van de hostingconfiguratie en is hiermee niet bevestigd.

## Lokaal starten

Er is geen buildstap nodig. Start vanuit de hoofdmap van de repository een statische webserver:

```bash
python3 -m http.server 8000 -d www
```

Open voor een **lokale test** `http://localhost:8000/zorg-analyse.html` of `http://localhost:8000/werving-benchmark-2026.html`. Dit zijn uitsluitend voorbeelden voor de lokale server; de GitHub-links en de gepubliceerde routes zijn hier niet aan gekoppeld. Voor externe CSS-, lettertype-, grafiek- en kaartbronnen is een internetverbinding nodig.

## Opslaan als PDF

1. Open de gewenste rapportagepagina in de browser.
2. Kies **Afdrukken** (`Ctrl+P` of `Cmd+P`).
3. Selecteer **Opslaan als PDF**.
4. Gebruik voor **Zorg Analyse** papierformaat **A4**, oriëntatie **Staand**, marges **Geen**. De benchmarkpresentatie gebruikt een eigen **16:9-landscape** printopmaak; laat de paginagrootte daarvoor bij voorkeur door de browser/CSS bepalen. Schakel **Achtergrondafbeeldingen** in als de browser daar een aparte optie voor toont.
5. Sla de PDF op.

## Hosting en insluiten

De repository bevat `CNAME` met `reports.dutchwebshark.com`. De uiteindelijke URL wordt gevormd door de **werkelijke publicatiebasis** plus het relatieve pad uit de tabel; bijvoorbeeld `<basis-URL>/werving-benchmark-2026.html`. Bij een publicatiebasis `https://reports.dutchwebshark.com/` is dat `https://reports.dutchwebshark.com/werving-benchmark-2026.html`. Controleer eerst of de hosting daadwerkelijk de inhoud van `www/` serveert; een GitHub-commit en het `CNAME`-bestand bewijzen op zichzelf niet dat de pagina live staat. Bij een iframe op een ander domein (bijvoorbeeld WordPress) moet de `src` wel verwijzen naar de echte gepubliceerde URL, niet naar een relatief pad op het WordPress-domein.

De benchmark is één zelfstandige HTML-pagina met 12 slides en kan na publicatie via een iframe op de website worden ingesloten. De huidige HTML bevat nog geen automatische iframe-hoogtekoppeling; geef het iframe voorlopig een passende vaste hoogte of voeg later een gecontroleerde `postMessage`-resizekoppeling toe. De bestaande Zorg Analyse-pagina heeft al een resizebericht voor de WordPress-integratie.
