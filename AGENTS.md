# AGENTS.md

Kanonische Projektanweisung für alle KI-Agenten (Codex, Claude Code, Antigravity, Hermes) in diesem Repository. Andere Tool-Adapter (z. B. `CLAUDE.md`) verweisen hierher und ergänzen nur Tool-Spezifisches.

## Projekt

Minimale, statische Landingpage im about.me-Stil für Marc Schraepler von Gerlach. Verteilerseite auf die Hauptseite marcschraepler.com. Details zu Design-Tokens, Features und Stack stehen in [README.md](README.md) — hier nicht duplizieren.

## Architektur

- Einzelne `index.html`, kein Build-Schritt, keine Abhängigkeiten, kein JS-Framework.
- Inline-CSS mit Custom Properties, gespiegelt aus dem `BaseLayout` von marcschraepler.com (siehe README, Abschnitt "Design-Tokens").
- Hosting über GitHub Pages, Deploy-Quelle ist der Branch `master` (nicht `main` — siehe CHANGELOG 2.0.1). Nach Release-Commits auf `main` ggf. `master` per Fast-Forward nachziehen, sonst bleibt das Deployment auf altem Stand.

## Arbeiten in diesem Repo

- Lokale Vorschau: `open index.html` im Browser, kein Server nötig.
- Änderungen am Profilbild-Pfad: Die Hauptseite ist ein Astro-Projekt mit Content-Hash-Pfaden für Assets. Bricht der Bildpfad nach einem Deploy dort, `src` des Avatars in `index.html` aktualisieren; bis dahin greift automatisch der Monogramm-Fallback.
- Design-Token-Änderungen immer gegen `https://marcschraepler.com/_astro/BaseLayout.*.css` abgleichen, nicht frei erfinden.
- Kontrast (WCAG AA), sichtbarer Fokus-Ring und `prefers-reduced-motion` bei jeder visuellen Änderung erhalten.

## Validierung vor Abschluss

- `index.html` im Browser öffnen und Light- sowie Dark-Mode (`prefers-color-scheme`) prüfen.
- Alle Links (Website, LinkedIn) manuell verifizieren.
- Bei Sprachumschalter-Änderungen: DE/EN/FR-Texte auf Konsistenz prüfen.

## Änderungsdokumentation

- Jede sichtbare oder strukturelle Änderung in `CHANGELOG.md` eintragen (Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), Einträge auf Deutsch).
- `README.md` aktualisieren, wenn sich Design-Tokens, Features oder Tech-Stack ändern.

## Sicherheit & Repo-Hygiene

- Niemals Secrets, API-Keys, Tokens, private Schlüssel oder personenbezogene Daten committen.
- Keine lokalen KI-Memory-, Session-, Log- oder Cache-Dateien committen (siehe `.gitignore`).
- Vor jedem Commit den Diff auf versehentlich eingeschlossene sensible Inhalte prüfen.

## Git-Workflow

- Aussagekräftige, auf Deutsch verfasste Commit-Nachrichten (passend zur bestehenden Historie).
- Vor dem Push: lokalen Branch mit `origin` synchronisieren (Rebase oder konfliktfreier Merge).
- Keine Force-Pushes auf `main` oder `master` ohne explizite Freigabe.
