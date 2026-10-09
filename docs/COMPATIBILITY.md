# Compatibility and updates

## Target

The project targets KDE Plasma 6. Research currently uses the Plasma 6.7 and Qt 6.11 documentation as a development reference. No release compatibility matrix is certified yet.

## Maintenance strategy

- Reuse public KDE/Qt APIs and Breeze resources where possible.
- Keep a small set of explicit overrides rather than a full copy of the desktop.
- Record the upstream revision and license for reused resources.
- Review overridden files when their upstream component changes.
- Test new inherited elements for visual consistency.
- Adapt or rebuild native modules when their API or compatibility requires it.

A Breeze fallback can supply missing Plasma Style assets; it does not merge upstream fixes into files this theme overrides. QML changes, new states and native module compatibility need their own checks.

## Release checks

Record supported Plasma/Qt versions, dependencies and architecture for compiled modules. Verify appearance, keyboard interaction, dock sizing, notifications, scaling and resource use. Keep package versions, migration notes and a recoverable previous release.

Updating appearance must preserve layout and preferences. Layout installation, if offered, must be a separate explicit operation.
