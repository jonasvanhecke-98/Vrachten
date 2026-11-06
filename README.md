# Altez Vrachtplanner V3 - Trimble Connect extensie

## Wat is veranderd?

- Foutieve propertyset-toegang `set.set` hersteld: de Workspace API gebruikt `PropertySet.name`.
- Detecteert assemblages via de modelobjectklasse en leest `getObjectProperties` per model en runtime-ID.
- Extra scan voor viewers die IFC-classes anders teruggeven; geen fallback naar `Default.comment` of losse onderdeelparameters.
- Ingebouwde Hydroos-voorbeeldlijst, herstelknop en verplichte prefix verwijderd.
- De gebruiker importeert altijd eerst een tekstgebaseerde PDF-vrachtlijst.
- 1 tekstmarkup per vracht, kleur op de volledige assembly en assembly-kinderen.

## Installatie

Upload `index.html`, `manifest.json` en `icon.svg` naar de root van `ictaltez/Altez_Vrachtindeling`, met GitHub Pages actief. Gebruik in Trimble Connect de manifest-URL:

`https://ictaltez.github.io/Altez_Vrachtindeling/manifest.json`

## Werking

1. Open IFC-model in Trimble Connect 3D Viewer.
2. Importeer PDF met vrachtkopjes en de kolom **ElementNr**.
3. Kies geladen model, klik **Koppel en kleur vrachten**.
4. De extensie leest uitsluitend `Tekla Assembly -> Assembly/Cast unit Mark` op `IfcElementAssembly`.
5. Bij iedere vracht een kleur en maximaal één tekstmarkup, met focus/selectie vanuit de lijst.

## Nog live te controleren

De exacte weergave van assembly-kinderen en positie van tekstmarkups is afhankelijk van de daadwerkelijke geladen Trimble Viewer en blijft een live praktijktest. PDF-scans zonder selecteerbare tekst worden niet ondersteund. De vrachtkleuren worden niet in de IFC opgeslagen. Deze extensie slaat geen Trimble Views op en exporteert geen A3/PDF.
