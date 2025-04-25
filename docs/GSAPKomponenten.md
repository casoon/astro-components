# GSAP-Komponenten für Astro

Eine Sammlung von Astro-Komponenten mit GSAP-Animationen für moderne, interaktive Websites.

## SVGOverlay

Eine SVG-Overlay-Komponente mit einer animierten Maske und Logo-Bewegungen, angetrieben von GSAP.

### Animation

Die Komponente bietet eine spektakuläre Eingangsanimation, bei der ein kleines Loch in einer Maske sich erweitert und schließlich das gesamte Bild freigibt, während ein Logo nach oben bewegt wird. Diese Animation ist ideal für Intro-Sequenzen auf Landing Pages.

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

### Anpassung

Die Animation wird in drei Phasen ausgeführt:
1. Anfangsphase (0% - 30%)
2. Pausenphase (30% - 40%)
3. Abschlussphase (40% - 100%)

Die Dauer und die Keyframes können angepasst werden, um die gewünschte Animation zu erzielen.

## HeroSection

Eine komplette Hero-Sektion mit SVG-Overlay, animierten Menüs und Hintergrundübergängen.

### Funktionen

- SVG-Overlay-Animation mit GSAP
- Animierter Hintergrundwechsel
- Einfahrende obere Navigationsleiste
- Ausfahrender Text am unteren Bildschirmrand
- Einfahrendes Seitenmenü
- Ausgeklapptes Hauptmenü mit Kategorien
- Vollständig responsive für alle Geräte

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

### Zeitliche Abfolge der Animationen

1. SVG-Overlay startet sofort (Dauer: 5s)
2. Nach 1.5s beginnt der Hintergrundübergang
3. Nach 5s (Ende der SVG-Animation):
   - Top-Bar fährt ein
   - Unterer Text erscheint von rechts
   - Nach weiteren 0.5s erscheint das Seitenmenü

### CSS-Variablen

Die Komponente verwendet CSS-Variablen für Farben, Typografie und Layouts. Diese können im globalen CSS überschrieben werden:

```css
:root {
  --color-primary: #267DF4;  /* Primärfarbe ändern */
  --font-family-primary: 'Montserrat', sans-serif;  /* Schriftart ändern */
  --font-size-huge: clamp(3rem, 2.5rem + 2.5vw, 3.5rem);  /* Größere Überschriften */
}
```

### Mobile Ansicht

Für Bildschirme unter 768px Breite:
- Seitenmenü wird ausgeblendet
- Top-Bar wird höher und zentriert das Logo
- Menüstruktur wird angepasst für bessere Touch-Bedienung

## Integration mit anderen Komponenten

Beide Komponenten können leicht mit anderen Astro-Komponenten kombiniert werden:

```astro
---
import HeroSection from '../components/HeroSection.astro';
import ContentSection from '../components/ContentSection.astro';
---

<main>
  <HeroSection logoUrl="/logo.svg" />
  <ContentSection />
</main>
```

## Browser-Kompatibilität

Die Komponenten wurden in folgenden Browsern getestet:
- Chrome (neueste Version)
- Firefox (neueste Version)
- Safari (neueste Version)
- Edge (neueste Version)

## Fehlerbehebung

Falls die Animationen nicht korrekt funktionieren:

1. Stelle sicher, dass GSAP korrekt geladen wird
2. Überprüfe, ob die Pfade zu Bildern und Logos korrekt sind
3. Bei Z-Index-Problemen überprüfe die Stacking-Reihenfolge
4. Bei Performance-Problemen reduziere die Animationskomplexität 