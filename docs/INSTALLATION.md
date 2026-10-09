# Installation plan

Status: planned. This repository does not contain an installable theme or an implemented installer yet.

## User flow

1. Download and extract a release archive, or clone the repository.
2. Run a single `install.sh` entry point and choose light, dark or both variants.
3. Select the installed appearance in KDE System Settings. Applying a supplied layout, if offered, is a separate choice.

The [MacTahoe GTK installation instructions](https://github.com/vinceliuice/MacTahoe-gtk-theme#quick-install) are a reference for a short workflow and variant selection. Our implementation targets KDE packages and does not use GTK/GNOME installers or dependencies for Plasma components.

## Proposed command interface

These options describe the intended interface; they are not available commands yet:

| Option | Intended behavior |
|---|---|
| No arguments | Offer a simple choice of light, dark or both |
| `--variant light` | Install the light variant |
| `--variant dark` | Install the dark variant |
| `--variant both` | Install both variants |
| `--uninstall` | Remove only the selected project's installed resources |
| `--help` | Explain options, dependencies and installation scope |

## Implementation requirements

- Use the current user's standard KDE data locations by default; no administrator access for ordinary theme installation.
- Check the supported Plasma/Qt version and component dependencies, reporting missing requirements clearly.
- Distinguish data-only theme components from native modules that need an appropriate binary or a documented build step.
- Keep authoring tools out of runtime dependencies unless a real installation requirement demonstrates the need.
- Package both color schemes and corresponding Global Theme selections, with shared artwork where appropriate.
- Preserve pinned apps, panel layout and independent dock preferences during installation and appearance switching.
- Track installed resources, preserve replaced versions when necessary and protect later user edits during removal/recovery.
- Install no permanent background process merely to maintain appearance.

Ready-to-run commands, distribution-specific dependencies and recovery instructions will be published after testing an actual release package. This document defines the intended installation experience; it does not certify any installation operation.
