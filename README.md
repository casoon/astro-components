# @casoon/astro-components

Eine Sammlung wiederverwendbarer UI-Komponenten für Astro-Projekte.

## Installation

```bash
# Via npm
npm install @casoon/astro-components

# Via yarn
yarn add @casoon/astro-components

# Via pnpm
pnpm add @casoon/astro-components
```

## Verfügbare Komponenten

- [CanvasGrid](docs/CanvasGrid.md) - Eine interaktive Raster-Komponente mit Hover-Effekten
- [SVGOverlay & HeroSection](docs/GSAPKomponenten.md) - GSAP-animierte Komponenten für moderne Landing Pages

## Grundlegende Verwendung

```astro
---
import CanvasGrid from '@casoon/astro-components';
import HeroSection from '@casoon/astro-components/HeroSection';
---

<!-- CanvasGrid als Hintergrund -->
<div style="position: relative; height: 100vh;">
  <CanvasGrid />
  <!-- Dein Inhalt hier -->
</div>

<!-- GSAP Hero-Sektion -->
<HeroSection 
  logoUrl="/logo.svg"
  mainText="WILLKOMMEN<br>BEI UNS"
  subText="Entdecke unsere Dienstleistungen"
/>
```

Weitere Details zur Verwendung und Konfiguration der einzelnen Komponenten findest du in der jeweiligen Dokumentation.

## Lizenz

MIT 

# Astro GSAP Komponenten

Eine Sammlung von Astro-Komponenten mit GSAP-Animationen.

## SVGOverlay

Eine SVG-Overlay-Komponente mit einer animierten Maske und Logo-Bewegungen, angetrieben von GSAP.

### Installation

```bash
# GSAP-Abhängigkeiten installieren
npm install gsap
```

### Verwendung

```astro
---
import SVGOverlay from '../components/SVGOverlay.astro';
---

<div style="position: relative; height: 100vh;">
  <SVGOverlay 
    logoUrl="/pfad/zum/logo.svg"
    maskColor="white"
    animationDuration={5}
  />
</div>
```

### Props

| Prop | Standardwert | Beschreibung |
|------|--------------|--------------|
| `logoUrl` | "/logo.svg" | Pfad zum Logo SVG |
| `maskColor` | "white" | Farbe der Maske |
| `animationDuration` | 5 | Animation Dauer in Sekunden |
| `maskInitialX` | 45 | Start X-Position der Maske |
| `maskInitialY` | 45 | Start Y-Position der Maske |
| `maskInitialWidth` | 10 | Start Breite der Maske |
| `maskInitialHeight` | 10 | Start Höhe der Maske |
| `logoSize` | 10 | Größe des Logos |
| `logoInitialY` | -5 | Start Y-Position des Logos |
| `logoFinalY` | -40 | End Y-Position des Logos |

## HeroSection

Eine komplette Hero-Sektion mit SVG-Overlay, animierten Menüs und Hintergrundübergängen.

### Verwendung

```astro
---
import HeroSection from '../components/HeroSection.astro';
---

<HeroSection 
  logoUrl="/logo.svg"
  background1Url="/hintergrund1.jpg"
  background2Url="/hintergrund2.jpg"
  mainText="BEISPIEL<br>ÜBERSCHRIFT"
  subText="Ein inspirierender Untertitel."
  logoText="Markenname"
  clinicText="ZUSATZ"
/>
```

### Props

| Prop | Standardwert | Beschreibung |
|------|--------------|--------------|
| `logoUrl` | "/logo.svg" | Pfad zum Logo SVG |
| `background1Url` | Platzhalter | URL zum ersten Hintergrundbild |
| `background2Url` | Platzhalter | URL zum zweiten Hintergrundbild |
| `mainText` | "WORLD'S BEST..." | Haupttext (unterstützt HTML) |
| `subText` | "Hier gibt es..." | Untertitel |
| `logoText` | "Sauerstoffzentrum" | Text für das Logo in der Navigationsleiste |
| `clinicText` | "NORDOST" | Zusatztext für das Logo |

## Hinweise

- Beide Komponenten benötigen GSAP, das über CDN geladen wird
- Die Komponenten sind vollständig responsive und für mobile Geräte optimiert
- Alle Animationen und Farben können über Props oder CSS-Variablen angepasst werden

## Lizenz

MIT 