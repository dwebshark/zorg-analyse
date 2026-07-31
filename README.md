# Dutchwebshark rapportageomgeving

Deze repository bevat interactieve rapportages van [Dutchwebshark](https://dutchwebshark.com), opgebouwd als zelfstandige HTML-pagina's voor webpublicatie en PDF-export.

## Beschikbare rapportagepagina's

| Rapportage | Lokale route | Publieke versie | Bestand |
| --- | --- | --- | --- |
| Wervingsanalyse Zorgmarkt Nederland | [`/zorg-analyse.html`](http://localhost:8000/zorg-analyse.html) | [Zorgrapportage](https://dutchwebshark.com/zorg-analyse/) | `www/zorg-analyse.html` |

## Lokaal starten

Er is geen buildstap nodig. Start vanuit de hoofdmap van de repository een statische webserver:

```bash
python3 -m http.server 8000 -d www
```

Open daarna [http://localhost:8000/zorg-analyse.html](http://localhost:8000/zorg-analyse.html). Voor de externe lettertypen, grafiekenbibliotheken en kaartlagen is een internetverbinding nodig.

## Opslaan als PDF

1. Open de gewenste rapportagepagina in de browser.
2. Kies **Afdrukken** (`Ctrl+P` of `Cmd+P`).
3. Selecteer **Opslaan als PDF**.
4. Gebruik papierformaat **A4**, oriëntatie **Staand** en marges **Geen**. Schakel **Achtergrondafbeeldingen** in als de browser daar een aparte optie voor toont.
5. Sla de PDF op.
