# Development guide

## Source components

Keep each theme layer independently testable. Global Theme defaults select components; they do not automatically supply every referenced package.

Use the source directories under `src/`. Their README files are scaffolding, not complete KDE packages. Add real metadata, assets and configuration only as each component is implemented and checked.

## Tools

- Inkscape: SVG authoring and offline exports.
- Plasma SDK: Plasma Style, Global Theme and icon explorers; widget testing.
- KPackage tools: package inspection and controlled installation.
- Qt QML tools: syntax/type analysis, formatting, tests and profiling.
- CMake, Ninja and a C++ compiler: native modules where required.
- Git: versioned sources and release history.

Exact dependencies and build commands will accompany implemented components. Do not install or rebuild the whole desktop just to produce color and artwork data.

## Validation

1. Check metadata, component IDs, declared paths, SVG IDs and icon-theme entries.
2. Review actual-size artwork and all interaction states.
3. Exercise configuration persistence, cancellation and component lifetime.
4. Test in an appropriate isolated environment before applying to a daily desktop.
5. Compare resource use and frame times with an equivalent Breeze baseline.
6. Validate the actual session and preserve a recovery path.

Independent configuration/cache directories do not isolate the session's D-Bus or compositor. Full shell integration requires a suitable test session; hardware performance still needs measurement on the target machine.

Keep appearance-only application separate from layout changes. Avoid edits to distribution-owned files and unintended resets of pinned apps or user preferences.
