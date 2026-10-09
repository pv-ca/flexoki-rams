# Flexoki-Rams

I started Flexoki-Rams because I wanted a modern, elegant KDE desktop that stayed responsive without sacrificing performance. The dock, panels and everyday controls should feel consistent, and animations should remain smooth with as little CPU and memory overhead as possible.

The project is being built on Breeze, using native KDE and Qt components as its foundation. Other KDE themes, including [WhiteSur](https://github.com/vinceliuice/WhiteSur-kde), [MacSonoma](https://github.com/vinceliuice/MacSonoma-kde) and [MacTahoe](https://github.com/vinceliuice/MacTahoe-kde), inform the visual direction. [Klassy](https://github.com/paulmcauley/klassy) is a technical reference for extending Breeze.

> **Status: early development.** This repository currently contains the project structure and development documentation. There is no installable release yet, and performance targets have not been benchmarked.

## Why Flexoki-Rams?

Flexoki comes from the [Flexoki color scheme](https://github.com/kepano/flexoki), whose colors are inspired by printing inks and warm shades of paper. That palette gives the theme its color identity.

Rams refers to [Dieter Rams and his principles of good design](https://www.vitsoe.com/us/about/good-design). His emphasis on usefulness, clarity and care for the details guides the interface: readable controls, deliberate spacing and decoration that leaves room for the work on screen. I want the same restraint to shape how the theme uses system resources.

## Design goals

- A consistent dark material across the top panel, dock, menus and popups.
- Rounded shapes, clear hierarchy, readable states and contained hover highlights.
- A dedicated icon family with consistent application-tile geometry.
- Independent dock height, icon size and hover magnification settings.
- Smooth, finite animations and a coherent reduced-effects appearance.
- Reuse of Breeze and KDE/Qt components, with small, focused customizations.
- Preservation of the user's layout, pinned applications and preferences.

## Architecture

| Component | Responsibility |
|---|---|
| Global Theme / Look and Feel | Select the tested appearance components |
| Plasma Style | Shell surfaces, borders, selections and related SVG elements |
| Color scheme | Semantic Flexoki colors and interaction states |
| Icon theme | Application icons, places, actions, devices, status and emblems |
| Dock widget | Magnification, sizing and live configuration preview |
| KWin integration | Small behavior components where necessary |

Breeze is the foundation. Missing Plasma Style artwork can use its native fallback. Application styling and window decoration will reuse Breeze wherever it meets the approved design.

## Repository layout

```text
src/
  icons/PVCA-Flexoki-Rams/
  color-schemes/
  plasma/
    desktoptheme/flexoki-rams/
    look-and-feel/org.pvca.flexoki-rams.desktop/
    plasmoids/org.pvca.flexokidock/
  kwin/
docs/                  design, development and compatibility notes
assets/previews/       reviewed screenshots and presentation assets
scripts/               future build, packaging and validation tools
tests/                 future behavior and integration tests
```

## Development

Start with the [design direction](docs/DESIGN.md), [development guide](docs/DEVELOPMENT.md) and [roadmap](docs/ROADMAP.md). The [icon standard](docs/ICON-STANDARD.md) defines the initial application-tile geometry.

QML provides interfaces and motion; C++/Qt is reserved for focused native components. SVG, PNG, JSON and KDE configuration files provide artwork and package data. Build and authoring tools will not be required as resident processes merely to use the theme.

See [compatibility](docs/COMPATIBILITY.md), [official references](docs/REFERENCES.md) and [licensing status](docs/LICENSING.md). Installation instructions and a tested-version matrix will be added with the first usable package.

## Performance

Low overhead is a design requirement, not a result already established. Releases should compare idle CPU and memory, sustained dock hover, popup interaction, startup and retained memory against an equivalent Breeze baseline. GPU and frame-time costs are part of that comparison.

## Contributing

The project is currently establishing its assets and packaging. Discuss substantial changes before implementation. Keep native behavior, accessibility, scope and measured performance in view. Reused code and artwork must include their origin and license information.
