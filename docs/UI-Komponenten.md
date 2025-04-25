# UI-Komponenten für Astro

Eine Sammlung von Astro-Komponenten mit CSS-Animationen für moderne, interaktive Websites.

## HeroSection

Eine interaktive Hero-Sektion mit animiertem Masken-Overlay und Hintergrundübergängen.

### Animation

Die Komponente bietet eine spektakuläre Eingangsanimation, bei der ein kleines Loch in einer Maske sich erweitert und schließlich das gesamte Bild freigibt, während ein Logo nach oben bewegt wird. Diese Animation ist ideal für Intro-Sequenzen auf Landing Pages.

### Installation

Keine externen Abhängigkeiten erforderlich – die Komponente nutzt native CSS-Animationen.

### Verwendung

```astro
---
import HeroSection from '../components/HeroSection.astro';
---

<HeroSection 
  logoUrl="https://placehold.co/400/2A3B4C/FFFFFF?text=LOGO"
  background1Url="https://placehold.co/1920x1080/111111/FFFFFF?text=Hintergrund+1"
  background2Url="https://placehold.co/1920x1080/222222/FFFFFF?text=Hintergrund+2"
  maskColor="white"
  animationDuration={5}
  pauseDuration={1.5}
/>
```

### Props

| Prop | Standardwert | Beschreibung |
|------|--------------|--------------|
| `logoUrl` | "https://placehold.co/400/2A3B4C/FFFFFF?text=LOGO" | Pfad zum Logo |
| `background1Url` | "https://placehold.co/1920x1080/111111/FFFFFF?text=Hintergrund+1" | URL zum ersten Hintergrundbild |
| `background2Url` | "https://placehold.co/1920x1080/222222/FFFFFF?text=Hintergrund+2" | URL zum zweiten Hintergrundbild |
| `maskColor` | "white" | Farbe der Maske (Standard: weiß) |
| `animationDuration` | 5 | Animation Dauer in Sekunden |
| `pauseDuration` | 1.5 | Pause zwischen Bildwechsel in Sekunden |
| `maskInitialX` | 45 | Start X-Position der Maske |
| `maskInitialY` | 45 | Start Y-Position der Maske |
| `maskInitialWidth` | 10 | Start Breite der Maske |
| `maskInitialHeight` | 10 | Start Höhe der Maske |
| `logoSize` | 10 | Größe des Logos |
| `logoInitialY` | -5 | Start Y-Position des Logos |
| `logoFinalY` | -40 | End Y-Position des Logos |

### Funktionsweise der Animation

Die Animation läuft in drei Phasen ab:
1. **Anfangsphase (0-30%)**: Das Loch in der Maske wächst auf Zwischengröße, Logo bewegt sich leicht nach oben
2. **Pausenphase (30-40%)**: Kurze Pause im Wachstum für einen dramatischen Effekt
3. **Finalphase (40-100%)**: Das Loch wächst weiter bis zum Vollbild, Logo bewegt sich zur finalen Position

Parallel dazu:
- Das erste Hintergrundbild wird animiert (Skalierung und Helligkeit)
- Nach der definierten Pausenzeit wird ein Übergang zum zweiten Hintergrundbild eingeleitet

### Integration in Ihr Projekt

Die Komponente ist einfach zu integrieren:

```astro
---
import { HeroSection } from '@casoon/astro-components';
---

<main>
  <HeroSection />
  
  <!-- Weitere Inhalte -->
  <section id="content">
    <!-- Ihr Content hier -->
  </section>
</main>
```

## Technische Details

- **Animationstechnik**: Verwendet native CSS-Animationen und Keyframes
- **SVG-Masking**: Nutzt SVG-Masken für den Reveal-Effekt
- **Responsive Design**: Passt sich automatisch verschiedenen Bildschirmgrößen an
- **Optimierte Performance**: Leichtgewichtige Implementierung ohne externe Bibliotheken

## Browser-Kompatibilität

Die Komponente wurde in folgenden Browsern getestet:
- Chrome (neueste Version)
- Firefox (neueste Version)
- Safari (neueste Version)
- Edge (neueste Version)

## Fehlerbehebung

Falls die Animationen nicht korrekt funktionieren:

1. Überprüfe, ob die Pfade zu Bildern und Logos korrekt sind
2. Bei Z-Index-Problemen überprüfe die Stacking-Reihenfolge
3. Bei Performance-Problemen reduziere die Animationskomplexität durch Anpassung der Dauer 