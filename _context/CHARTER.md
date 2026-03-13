# Project Charter — jasonmcdermott.net

| Field          | Value                          |
|----------------|--------------------------------|
| Status         | Canonical                      |
| Workspace Code | JM                             |
| Created        | 2026-03-10                     |
| Version        | 1.0.0                          |
| Visibility     | Open source                    |
| Type           | Software                       |

## Purpose

Personal landing page for Jason McDermott at jasonmcdermott.net. A single-page static site that communicates who Jason is, what he's working on, and where to find him online. Serves as the canonical public-facing personal web presence.

## Success Criteria

- Page loads fast and renders correctly on all modern browsers and devices
- Content is current and accurately reflects active projects and links
- Design is clean, typographically considered, and distraction-free
- Site is deployable as a static page with zero build tooling

## Boundaries

- **In scope:** Single-page personal site (bio, projects, links), styling, responsive design
- **Out of scope:** Blog engine, CMS, backend services, analytics dashboards, JavaScript frameworks

## Design Principles

1. **Simplicity over tooling** — Single HTML file with inline CSS. No build step, no dependencies beyond Google Fonts.
2. **Typography-first** — Design driven by type choices (Libre Baskerville + DM Mono), whitespace, and restraint.
3. **Content is the product** — The page exists to communicate, not to demonstrate technical complexity.
4. **Mobile-ready by default** — Responsive layout with sensible breakpoints.

## Binding Rules

1. Keep the site as a single `index.html` file unless there is a compelling reason to split.
2. Do not introduce JavaScript frameworks, bundlers, or build tooling.
3. External dependencies are limited to font loading; all styling remains inline.
4. Content updates (bio, projects, links) should be the most common type of change.
5. Maintain the existing visual language (warm paper tones, serif/mono pairing, red accent).
