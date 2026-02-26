# Bikenomics Stadsanalyse

**Urban Mobility Resource Navigator — Bikenomics Module**

Een interactieve calculator die de economische baten van fietsinfrastructuur-investeringen berekent op stadsniveau. Het tool vertaalt fietskilometers naar concrete financiële voordelen op het gebied van gezondheid, milieu, mobiliteit en maatschappij.

🌐 **Live demo:** [https://velomondial.github.io/bikenomics/](https://velomondial.github.io/bikenomics/)

---

## Kenmerken

- **Stadsprofielinvoer** — stadsnaam, inwoneraantal, fietsmodal-split, gemiddelde ritafstand
- **Economische batenberekening** — gezondheidsbaten, milieubaten, mobiliteitsbaten, maatschappelijke baten
- **Investeringsscenario's** — vergelijk huidige situatie met uitbreiding van fietsinfrastructuur
- **Kosten-batenanalyse** — automatische berekening van baten/kosten-ratio
- **Meertalig** — Nederlands, Engels, Duits, Frans, Spaans, Portugees, Italiaans
- **Responsief design** — werkt op desktop, tablet en mobiel
- **Geen server nodig** — volledig client-side, draait als statische site

## Deel van het Urban Mobility Resource Navigator ecosysteem

Dit tool is een van de modules van de [Urban Mobility Resource Navigator](https://velomondial.net), een AI-ondersteund kennissysteem voor duurzame stedelijke mobiliteit ontwikkeld door Velo-Mondial.

## Lokaal draaien

```bash
# Clone de repository
git clone https://github.com/velomondial/bikenomics.git
cd bikenomics

# Open in browser (geen build-stap nodig)
open index.html
# of gebruik een lokale server:
python3 -m http.server 8000
```

## Deployment

Deze site wordt automatisch gedeployd via GitHub Pages bij elke push naar de `main` branch. Zie `.github/workflows/deploy.yml` voor de configuratie.

## Licentie

© 2025 Velo-Mondial. Alle rechten voorbehouden.

## Contact

Pascal van den Noort — [pascal@velomondial.net](mailto:pascal@velomondial.net)
