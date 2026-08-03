# Changelog

All notable changes to this project will be documented in this file.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [2.0.0] - 2026-08-03

### Changed

- Design auf die Tokens von marcschraepler.com umgestellt: Primärfarbe `oklch(52% 0.085 234)`, Radius `0.65rem`, Schriftpaar Bricolage Grotesque (Headline) und Plus Jakarta Sans (Fließtext), Transition-Dauer 0.2s
- Seitensprache von `en` auf `de` umgestellt, passend zur kanonischen Sprache der Hauptseite
- Texte an die Positionierung der Hauptseite angeglichen: Rolle "Digital Architect für den wachsenden Mittelstand", Kurzbeschreibung aus der Hero-Sektion
- Link-Liste von einem auf fünf Ziele erweitert (Kontakt als primärer CTA, Website, Lösungen, Über mich, LinkedIn) plus Footer mit EN-Version, Standpunkte, Impressum, Datenschutz

### Fixed

- Profilbild zeigte auf einen alten, gehashten Astro-Asset-Pfad, der nicht mehr existiert (404). Jetzt aktueller Pfad plus Monogramm-Fallback, falls der Hash beim nächsten Build erneut wechselt
- Kontrast im Dunkelmodus: Primärbutton nutzt den hellen Akzent, damit die Button-Beschriftung WCAG AA erfüllt

### Added

- Erweiterte Meta-Daten: Open Graph mit Bild, Twitter Card, `hreflang` für DE und EN, `theme-color` je Farbschema, `color-scheme`
- JSON-LD `Person`-Schema mit `sameAs` auf Hauptseite und LinkedIn
- Sichtbarer Fokus-Ring für Tastaturbedienung
- Hex-Fallbacks für alle `oklch`-Farbwerte via `@supports`

## [1.0.0] - 2025-02-13

### Added

- Initial release: minimal about.me-style landing page
- Profile card with avatar, name, tagline, and bio
- Single CTA linking to main website (marcschraepler.com)
- Dark mode support via `prefers-color-scheme`
- Responsive layout
- Reduced motion support
