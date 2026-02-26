# 🚀 GitHub Pages Setup Guide — Bikenomics

Stap-voor-stap handleiding om Bikenomics live te zetten op GitHub Pages.

---

## Optie A: Via GitHub.com (geen command line nodig)

### 1. Repository aanmaken
1. Ga naar **https://github.com/new**
2. Repository naam: `bikenomics`
3. Zet op **Public** (vereist voor gratis GitHub Pages)
4. Klik **Create repository**

### 2. Bestanden uploaden
1. Klik op **"uploading an existing file"** op de lege repo-pagina
2. Sleep **alle bestanden én mappen** uit de gedownloade map hiernaartoe:
   - `index.html`
   - `404.html`
   - `README.md`
   - `.gitignore`
   - `.nojekyll`
   - `.github/` map (met `workflows/deploy.yml` erin)
3. Typ een commit-bericht: `Initial release Bikenomics Stadsanalyse`
4. Klik **Commit changes**

### 3. GitHub Pages activeren
1. Ga naar **Settings** → **Pages** (linker sidebar)
2. Bij **Source** kies: **GitHub Actions**
3. De workflow runt automatisch — binnen ~1 minuut is de site live

### 4. Check je site
Je site staat op:
```
https://velomondial.github.io/bikenomics/
```
(Vervang `velomondial` door je GitHub-gebruikersnaam als die anders is.)

---

## Optie B: Via de command line (Git)

```bash
# 1. Ga naar de map met de bestanden
cd bikenomics

# 2. Initialiseer Git
git init
git branch -M main

# 3. Voeg alle bestanden toe
git add -A
git commit -m "Initial release Bikenomics Stadsanalyse"

# 4. Koppel aan GitHub (maak eerst de repo aan op github.com)
git remote add origin https://github.com/velomondial/bikenomics.git
git push -u origin main
```

Activeer daarna GitHub Pages via Settings → Pages → Source: **GitHub Actions**.

---

## Optioneel: Eigen domein koppelen

Wil je de site op bijv. `bikenomics.velomondial.net`?

### 1. CNAME-bestand aanmaken
Maak een bestand `CNAME` aan in de root met alleen dit erin:
```
bikenomics.velomondial.net
```

### 2. DNS instellen
Voeg een **CNAME-record** toe bij je domeinprovider:
```
Type:   CNAME
Naam:   bikenomics
Doel:   velomondial.github.io
```

### 3. HTTPS activeren
Na DNS-propagatie (kan tot 24 uur duren), ga naar:
Settings → Pages → vink **Enforce HTTPS** aan.

---

## Mapstructuur

```
bikenomics/
├── .github/
│   └── workflows/
│       └── deploy.yml      ← Automatische deployment
├── .gitignore               ← Git-exclusies
├── .nojekyll                ← Bypass Jekyll processing
├── 404.html                 ← Custom 404-pagina
├── index.html               ← De Bikenomics applicatie
├── README.md                ← Projectbeschrijving
└── SETUP.md                 ← Dit bestand
```

---

## Troubleshooting

| Probleem | Oplossing |
|----------|-----------|
| Site toont 404 | Check of `index.html` in de root staat, niet in een submap |
| Workflow faalt | Ga naar Actions tab → klik op de gefaalde run → lees de logs |
| Fonts laden niet | Fonts worden via Google Fonts geladen, dat werkt automatisch |
| Styling mist | Controleer dat `.nojekyll` aanwezig is (voorkomt Jekyll-verwerking) |
| Custom domein werkt niet | DNS-propagatie kan tot 24 uur duren |

---

## Updates deployen

Elke push naar `main` triggert automatisch een nieuwe deployment:

```bash
# Wijziging maken, committen en pushen
git add -A
git commit -m "Update: beschrijving van je wijziging"
git push
```

De site is binnen ~60 seconden bijgewerkt.
