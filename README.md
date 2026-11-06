# Vrachtplanner V2

Trimble Connect 3D Viewer-extensie voor prefab-vrachtlijsten (PDF -> IFC assemblies).

## Installatie

1. Maak/bewerk de GitHub repository `ictaltez/Altez_Vrachtindeling`.
2. Upload `index.html`, `manifest.json` en `icon.svg` in de root van die repo.
3. Activeer GitHub Pages vanaf de main branch (root).
4. Controleer of `https://ictaltez.github.io/Altez_Vrachtindeling/manifest.json` bereikbaar is.
5. Voeg deze manifest URL als Custom Extension toe aan het Trimble Connect project en open het IFC-model in de 3D Viewer.

## Gebruik

- Kies een PDF-vrachtlijst, of gebruik de ingebouwde Hydroos-voorbeeldlijst (12 vrachten, 72 elementen).
- Vul de prefix van de elementnummers in (bijvoorbeeld HYD). Een tekstgebaseerde PDF met herkenbare koppen `Vracht 01`, `ElementNr` is nodig; scans zijn niet ondersteund.
- Kies het geladen model, klik `Koppel en kleur vrachten`.
- De tool zoekt UITSLUITEND `IfcElementAssembly` met propertyset `Tekla Assembly` en eigenschap `Assembly/Cast unit Mark`. Als de Viewer dit propertyset niet ontsluit, meldt de tool geen match.
- De volledige assembly en onderliggende onderdelen (assembly-hiërarchie type 4) worden gekleurd. Eén gekleurde tekstmarkup per vracht (indien de positie via de API beschikbaar is).
- Klik op een vracht om de merken te bekijken, te selecteren of te focussen. De volgordeweergave selecteert de vrachten achtereenvolgens; het is geen 4D-datumplanning.
- `Wis Altez-kleuren` verwijdert eigen kleuren en labels. Eventuele eerder bestaande kleuren worden zo goed mogelijk hersteld.

## Grenzen huidige versie

- De echte Trimble Connect Viewer en de positionering van 3D-labels zijn niet live getest.
- PDF-interpretatie ondersteunt tekst-PDF's en leverancierlayout vergelijkbaar met de meegeleverde Hydroos-lijst, geen gescande PDF's zonder tekstlaag.
- Laden van een PDF gebeurt alleen lokaal in de browser, niet rechtstreeks vanuit een Trimble-projectmap.
- Geen opslag als Trimble View, geen A3/PDF-export of afbeeldingsexport.
- Bij meerdere geladen modellen best één model kiezen om onbedoelde dubbele matches te voorkomen.
- Door browser-CDN's zijn internetverbindingen met `components.connect.trimble.com` en `cdnjs.cloudflare.com` vereist.
