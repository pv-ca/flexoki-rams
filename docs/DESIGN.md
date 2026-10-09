# Design direction

Flexoki-Rams combines the Flexoki palette with clarity, restraint and a carefully composed desktop. Apple-inspired rounded surfaces and subtle depth inform the appearance; KDE remains the implementation foundation.

## Initial material tokens

| Role | Initial color |
|---|---|
| Deep background | `#100F0F` |
| Raised background | `#1C1B1A` |
| Dock and panel surface | `#282726` |
| Raised control | `#343331` |
| Border | `#575653` |
| Body text | `#CECDC3` |
| Strong text | `#F2F0E5` |
| Warm highlight | `#FFFCF0` |
| Accent | `#4385BE` |

These are starting tokens, not a complete KDE color scheme. Selection, disabled and inactive states require their own contrast review. Transparency and the background underneath affect the visible result.

## Visual acceptance

- Top and bottom panels share the approved material language.
- Menus, notifications, calendar, tray, tooltips, toggles and sliders follow coherent spacing and states.
- Highlights remain within their controls and do not collide with neighboring icons.
- Application tiles use the Eden geometry; folders and small symbols retain appropriate profiles.
- Notifications remain clear of the visible top panel.
- Dock height, icon size and magnification remain independent.
- Keyboard focus, reduced effects and small-screen behavior remain usable.

Breeze supplies a native foundation and fallback. Customization should be selective and maintainable.
