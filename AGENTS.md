# AGENTS.md — instructies voor rapportages

Deze instructies gelden voor de volledige repository `dwebshark/zorg-analyse`. Gebruik ze bij het toevoegen, wijzigen of publiceren van rapportagepagina's.

## Repositoryconventies

- Plaats elke nieuwe rapportage als zelfstandige HTML-pagina in `www/<rapport-slug>.html`.
- Houd de bestaande rapporten intact, tenzij expliciet om een wijziging daarvan wordt gevraagd.
- Rapportages worden als statische HTML gepubliceerd: voeg niet zonder noodzaak een buildstap, framework of nieuwe afhankelijkheid toe.
- `CNAME` bevat momenteel `reports.dutchwebshark.com`. Verander dit bestand niet wanneer je een rapport toevoegt.
- De publieke URL is **bedoeld** als `https://reports.dutchwebshark.com/<rapport-slug>.html`, voor zover de hosting de inhoud van `www/` daadwerkelijk publiceert. Een commit garandeert geen live publicatie.
- Let bij interactieve rapportages op responsive weergave, iframe-gebruik, navigatie en PDF-/printweergave. Bewaar de kleuren van de pagina in de PDF waar mogelijk met `print-color-adjust: exact` en `-webkit-print-color-adjust: exact`. Pas de documentinhoud of stijl niet ongevraagd aan.

## Verplichte README-update bij elk nieuw rapport

**Als je een HTML-rapport in `www/` toevoegt, werk je in dezelfde wijziging ook `README.md` bij.** Maak de README-update niet optioneel of afhankelijk van een apart verzoek.

1. Open de actuele `README.md` en zoek `## Beschikbare rapportagepagina's`.
2. Voeg precies één rij toe aan de bestaande tabel met de kolommen:
   - **Rapportage:** de leesbare, officiële titel van het nieuwe rapport.
   - **URL-pad vanaf de publicatiebasis:** alleen de bestandsnaam, tussen backticks, bijvoorbeeld `nieuw-rapport.html` (geen `www/` en geen `localhost`).
   - **Rapport openen:** een klikbare Markdown-link naar `https://reports.dutchwebshark.com/nieuw-rapport.html`, bijvoorbeeld `[Open rapport](https://reports.dutchwebshark.com/nieuw-rapport.html)`.
3. Behoud de bestaande kolomnamen en rijen; maak geen dubbele vermelding. De broncode-URL van GitHub mag de publieke rapportlink **niet** vervangen.
4. Controleer of de bestandsnaam in de README **exact** overeenkomt met het nieuwe bestand in `www/`.
5. Pas andere README-tekst alleen aan wanneer die door het nieuwe rapport aantoonbaar onjuist of onvolledig wordt, bijvoorbeeld instructies voor lokale tests, PDF-export of iframe-inbedding. Behoud rapportspecifieke verschillen (zoals staande A4-rapportage versus liggende 16:9-presentatie).
6. Maak duidelijk onderscheid tussen een **beoogde publieke URL** en een **daadwerkelijk geteste live URL**. Claim geen succesvolle publicatie zonder controle.

### Voorbeeld van een nieuwe tabelrij

```markdown
| Voorbeeldrapport 2027 | `voorbeeldrapport-2027.html` | [Open rapport](https://reports.dutchwebshark.com/voorbeeldrapport-2027.html) |
```

## Test- en oplevercheck

- Controleer dat `www/<rapport-slug>.html` bestaat, complete HTML bevat en lokaal te openen is.
- Test bij wijzigingen aan de pagina, waar mogelijk, desktop en mobiel; controleer interactie, iframe-weergave en PDF-/printuitvoer.
- Controleer de README-tabel op juiste titel, pad, publieke link en eventuele dubbele rijen.
- Voorkom harde `localhost`-links in de overzichtstabel. `localhost` is alleen toegestaan in het onderdeel **Lokaal starten** als ontwikkelvoorbeeld.
- Publiceer geen extra bestanden en wijzig geen bestaande rapportages buiten de gevraagde scope.
- Rapporteer na afloop welke bestanden zijn gewijzigd, op welke branch en of de publieke URL daadwerkelijk is gecontroleerd.

**Kortom:** bij `www/nieuw-rapport.html` hoort altijd een passende rij met een `reports.dutchwebshark.com`-link in `README.md`.
