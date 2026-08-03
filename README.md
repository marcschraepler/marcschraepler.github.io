# marcschraepler.github.io

Minimale Landingpage für [Marc Schraepler von Gerlach](https://marcschraepler.com/) – Digital Architect für den wachsenden Mittelstand.

## Überblick

Einzelne HTML-Datei im about.me-Stil, ohne Build-Schritt, ohne Abhängigkeiten, ohne JavaScript-Framework. Sie dient als Verteilerseite auf die Hauptseite [marcschraepler.com](https://marcschraepler.com/) und übernimmt deren Design-Tokens, damit beide Auftritte visuell zusammengehören.

**Live:** [marcschraepler.github.io](https://marcschraepler.github.io/)

## Features

- Einzelne `index.html`, rund 10 KB, keine externen Stylesheets außer Google Fonts
- Design-Tokens aus dem `BaseLayout` der Hauptseite gespiegelt (Farben, Radius, Schriften, Transition-Dauer)
- Automatischer Dunkelmodus über `prefers-color-scheme`, Farbwerte aus dem Dark-Theme der Hauptseite
- `oklch`-Farben mit Hex-Fallback über `@supports`
- Kontrast durchgehend über WCAG AA, sichtbarer Fokus-Ring, `prefers-reduced-motion` berücksichtigt
- Open Graph, Twitter Card, `hreflang` DE/EN und JSON-LD `Person`-Schema
- Profilbild vom Hauptserver mit Monogramm-Fallback, falls der gehashte Asset-Pfad nach einem Astro-Build wechselt
- Hosting über GitHub Pages

## Design-Tokens

Übernommen aus `https://marcschraepler.com/_astro/BaseLayout.*.css`.

| Token | Hell | Dunkel |
|-------|------|--------|
| `--background` | `oklch(98.5% 0 none)` | `oklch(14.5% 0 none)` |
| `--foreground` | `oklch(14.5% 0 none)` | `oklch(98.5% 0 none)` |
| `--primary` | `oklch(52% 0.085 234)` | `oklch(57% 0.076 219)` |
| `--primary-accent` | `oklch(50% 0.088 234)` | `oklch(72% 0.076 219)` |
| `--muted-foreground` | `oklch(43.9% 0 none)` | `oklch(70.8% 0 none)` |
| `--radius` | `0.65rem` | `0.65rem` |

Schriften: Bricolage Grotesque für Überschriften, Plus Jakarta Sans für Fließtext.

Im Dunkelmodus liegt die Button-Fläche bewusst auf `--primary-accent` statt auf `--primary`. Mit `--primary` als Fläche und heller Schrift läge der Kontrast bei 4.2:1 und damit unter WCAG AA.

## Tech Stack

| Ebene | Technologie |
|-------|-------------|
| Markup | Semantisches HTML5 |
| Styling | Inline-CSS mit Custom Properties |
| Schriften | Bricolage Grotesque, Plus Jakarta Sans (Google Fonts) |
| Hosting | GitHub Pages |
| Assets | Profilbild von [marcschraepler.com](https://marcschraepler.com) |

## Lokale Entwicklung

Kein Build nötig, `index.html` im Browser öffnen.

```bash
open index.html
```

## Wartung

Die Hauptseite ist ein Astro-Projekt und versieht Bilder mit einem Content-Hash. Nach einem Deploy dort kann sich der Pfad des Profilbilds ändern. Dann in `index.html` das `src` des Avatars aktualisieren; bis dahin greift automatisch das Monogramm.

## Verwandt

- **Hauptseite:** [marcschraepler.com](https://marcschraepler.com/) (Astro, vollständiges Portfolio)
- **Quelltext der Hauptseite:** privates Repository

## Lizenz

Inhalte © Marc Schraepler von Gerlach. Alle Rechte vorbehalten.
