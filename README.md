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
- [HeroSection](docs/UI-Komponenten.md) - Animierte Hero-Sektion mit Masken-Overlay

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

<!-- Hero-Sektion mit animiertem Overlay -->
<HeroSection 
  logoUrl="https://placehold.co/400/2A3B4C/FFFFFF?text=LOGO"
  background1Url="https://placehold.co/1920x1080/111111/FFFFFF?text=Hintergrund+1"
  background2Url="https://placehold.co/1920x1080/222222/FFFFFF?text=Hintergrund+2"
/>
```

Weitere Details zur Verwendung und Konfiguration der einzelnen Komponenten findest du in der jeweiligen Dokumentation.

## HeroSection

Eine interaktive Hero-Sektion mit animiertem Masken-Overlay und Hintergrundübergängen. Diese Komponente verwendet native CSS-Animationen für optimale Performance.

### Features

- Animiertes SVG-Overlay mit Maskeneffekt
- Übergang zwischen zwei Hintergrundbildern
- Anpassbare Animationszeiten und -parameter
- Leichtgewichtig und ohne externe Abhängigkeiten

### Props

| Prop | Standardwert | Beschreibung |
|------|--------------|--------------|
| `logoUrl` | Platzhalter | Pfad zum Logo |
| `background1Url` | Platzhalter | URL zum ersten Hintergrundbild |
| `background2Url` | Platzhalter | URL zum zweiten Hintergrundbild |
| `maskColor` | "white" | Farbe der Maske |
| `animationDuration` | 5 | Animation Dauer in Sekunden |
| `pauseDuration` | 1.5 | Pause zwischen Bildwechsel in Sekunden |
| `maskInitialX` | 45 | Start X-Position der Maske |
| `maskInitialY` | 45 | Start Y-Position der Maske |
| `maskInitialWidth` | 10 | Start Breite der Maske |
| `maskInitialHeight` | 10 | Start Höhe der Maske |

### Animation

Die Animation besteht aus mehreren Phasen:
1. Ein Loch in der weißen Overlay-Maske wächst allmählich
2. Das Logo bewegt sich sanft nach oben
3. Ein Übergang zwischen den beiden Hintergrundbildern erfolgt

Alle Animationsparameter können über Props angepasst werden.

## Lizenz

MIT 