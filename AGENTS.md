# AGENTS.md

## Project Overview

This repository contains a single-file, zero-dependency Chinese-language web application: **全国机器人实验室人才情报平台** (National Robotics Lab Talent Intelligence Platform), branded as **RoboLab · CN**.

The application is aimed at corporate HR and recruiting professionals who need to discover, filter, and analyze top Chinese university robotics labs and their graduates for talent acquisition purposes.

## Repository Structure

```
/workspace/
└── 全国机器人实验室人才情报平台.html   # The entire application (HTML + CSS + JS)
```

There is no build system, package manager, test suite, or external tooling. All logic, styles, and data live inline in a single HTML file.

## Running the Application

Open `全国机器人实验室人才情报平台.html` directly in any modern web browser. No server, install step, or build process is required.

The only runtime external dependency is a Google Fonts CDN import (requires an internet connection to load fonts):
- `Noto Serif SC`, `Noto Sans SC`, `JetBrains Mono`

## File Layout (inside the HTML file)

| Lines       | Content                                                                                  |
|-------------|------------------------------------------------------------------------------------------|
| 8 – 236     | **CSS** — dark glassmorphism design system, CSS custom properties, responsive layouts, modal/map styles, animations |
| 238 – 389   | **HTML** — three-page SPA skeleton (Home, Map, Labs) with a modal overlay; pages toggled via JS |
| 394 – 865   | **`LABS` data array** — hard-coded data for 20 robotics labs across 18 universities in 11 Chinese cities |
| 868 – 900   | **`PROVS` array** — SVG polygon paths approximating Chinese provincial boundaries        |
| 900+        | **Application JS** — navigation, SVG map engine (pan/zoom, city nodes, tooltips), lab card grid with filters, tabbed modal |

## Key Conventions

- **All content is in Simplified Chinese.** Keep any new user-facing strings in Simplified Chinese.
- **No external JS libraries.** All JavaScript is vanilla ES6+. Do not introduce npm packages, CDN script tags for JS libraries, or any build step.
- **Inline everything.** Styles, scripts, and data all belong inside the single HTML file. Do not split into separate files unless explicitly asked.
- **Data is hard-coded.** The `LABS` array is the source of truth for lab data. There is no API or database.
- **Dark theme.** The visual design uses a dark background with glassmorphism-style cards and CSS custom properties defined in `:root`. Preserve this aesthetic when adding UI elements.

## Making Changes

1. Edit `全国机器人实验室人才情报平台.html` directly.
2. To verify changes, open the file in a browser (no build step needed).
3. When adding a new lab entry to the `LABS` array, follow the structure of existing entries exactly (name, university, city, SVG coordinates, research directions, mentor profiles, results, partners, graduate flow, recruiting tips).
4. When modifying CSS, respect the existing custom properties (`--accent`, `--bg`, `--surface`, etc.) defined in `:root`.

## Testing

There is no automated test suite. Manual verification in a browser is the only testing method. After making changes, confirm:
- All three pages (Home, Map, Labs) render without console errors.
- The interactive SVG map loads and city nodes pulse correctly.
- The lab card grid filters work.
- The lab detail modal opens and all tabs display content.
