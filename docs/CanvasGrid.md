# CanvasGrid

Eine interaktive Raster-Komponente für Astro-Projekte, die ein reagierendes Gitter mit Hover-Effekten auf einem Canvas rendert.

## Verwendung

```astro
---
import CanvasGrid from '@casoon/astro-components';
---

<div class="container" style="position: relative; width: 100%; height: 100vh;">
  <CanvasGrid 
    gridSize={40} 
    fadeSpeed={0.03} 
    hoverColor="rgba(0,100,255,ALPHA)"
    idleStrokeColor="rgba(0,0,0,0.1)"
    maxRandomNeighbors={3}
    gradientOpacity={0.8}
    enableGradient={true}
    throttleMs={30}
    enableTouchSupport={true}
  />
  <!-- Dein weiterer Inhalt hier -->
</div>
```

## Props

| Prop | Standardwert | Beschreibung |
|------|--------------|--------------|
| `gridSize` | 36 | Größe der Gitterzellen in Pixeln |
| `fadeSpeed` | 0.02 | Geschwindigkeit, mit der der Hover-Effekt verblasst |
| `hoverColor` | "rgba(255,165,0,ALPHA)" | Farbe des Hover-Effekts (ALPHA wird automatisch ersetzt) |
| `idleStrokeColor` | "rgba(0,0,0,0.05)" | Standardfarbe der Gitterlinien |
| `maxRandomNeighbors` | 4 | Maximale Anzahl zufälliger Nachbarzellen, die aktiviert werden |
| `gradientOpacity` | 1 | Deckkraft des Verlaufseffekts oben und unten |
| `enableGradient` | true | Aktiviert oder deaktiviert den Verlaufseffekt |
| `throttleMs` | 30 | Verzögerung für Mausbewegungen (Throttling) in Millisekunden |
| `enableTouchSupport` | true | Aktiviert oder deaktiviert die Unterstützung für Touchgeräte |

## Funktionsweise

Die Komponente erstellt ein responsives Raster, das den gesamten Container ausfüllt. Wenn der Mauszeiger über das Raster bewegt wird, werden die betroffenen Zellen und einige ihrer Nachbarn hervorgehoben und verblassen dann langsam wieder.

### Performance-Optimierungen

- Die Komponente verwendet Throttling für Mausbewegungen, um die Anzahl der Event-Handler-Aufrufe zu reduzieren.
- Das Canvas-Rendering wird nur bei Bedarf durchgeführt (ca. 60fps), um die CPU-Belastung zu minimieren.
- Event-Listener werden ordnungsgemäß entfernt, wenn die Komponente nicht mehr benötigt wird.

### Mobile-Unterstützung

Die Komponente unterstützt Touch-Events auf mobilen Geräten. Diese Funktion kann über den `enableTouchSupport`-Parameter aktiviert oder deaktiviert werden.

### Anpassbarkeit

Der Verlaufseffekt kann vollständig deaktiviert werden, indem `enableGradient` auf `false` gesetzt wird.

## Beispiele

### Standardkonfiguration

```astro
<CanvasGrid />
```

### Blaues Gitter mit schnelleren Effekten

```astro
<CanvasGrid 
  hoverColor="rgba(0,0,255,ALPHA)" 
  fadeSpeed={0.05} 
  gridSize={30}
/>
```

### Ohne Verlaufseffekt

```astro
<CanvasGrid enableGradient={false} />
```

### Optimiert für niedrige Leistung

```astro
<CanvasGrid 
  throttleMs={50} 
  maxRandomNeighbors={2}
/>
```

## Technische Details

Die CanvasGrid-Komponente nutzt das HTML5 Canvas-Element für effizientes Rendering. Sie berechnet die Anzahl der Zellen basierend auf der Fenstergröße und der angegebenen Zellengröße, und aktualisiert das Raster bei Fenstergrößenänderungen.

Der Hover-Effekt wird durch Verfolgen der Mausposition erreicht. Wenn der Mauszeiger über eine Zelle bewegt wird, wird ihre Alpha-Transparenz auf 1 gesetzt und dann schrittweise reduziert, um den Verblassungseffekt zu erzeugen.

Die Komponente verwendet eine Throttling-Technik, um die Häufigkeit der Event-Handler-Aufrufe zu begrenzen und so die Leistung zu verbessern.

## Browser-Kompatibilität

Die CanvasGrid-Komponente ist mit allen modernen Browsern kompatibel, die HTML5 Canvas unterstützen:

- Chrome (neueste Version)
- Firefox (neueste Version)
- Safari (neueste Version)
- Edge (neueste Version)

## Fehlerbehebung

Wenn das Gitter nicht sichtbar ist, überprüfe:

1. Ob der Container der Komponente eine Höhe und Breite hat
2. Ob der Container positioniert ist (position: relative)
3. Ob es keinen CSS-Konflikt mit dem Canvas-Element gibt

Wenn der Hover-Effekt nicht funktioniert, stelle sicher:

1. Dass JavaScript aktiviert ist
2. Dass keine anderen JavaScript-Fehler in der Konsole angezeigt werden 