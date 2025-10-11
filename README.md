# Aloe

Aloe is a dark VS Code theme with a calm green base, tuned for WCAG-friendly contrast and smooth day-long coding. Brackets, JSX tokens, and UI chrome have been hand-curated to avoid harsh neon tones while still keeping structure easy to scan.

## Highlights

Aloe focuses on comfort and quick code scanning.

- Balanced green and teal accents that stay readable on low-brightness displays
- Dedicated token colors for JSX spreads, template expressions, and variables
- Soft bracket pair coloring without the default pure yellow/blue clash
- Accessible diff and peek highlights that distinguish insertions, deletions, and borders without eye strain
- Polished workbench styling (tabs, breadcrumbs, minimap, sidebar) for a seamless UI

## Installation

### Marketplace (when published)

1. Open the Extensions view (`View → Extensions`).
2. Search for `Aloe` by `lab829` and click **Install**.

### Manual install from source

1. Clone the repository:

   ```bash
   git clone https://github.com/lab829/aloe.git
   ```

2. From the project root, package the extension (requires [`vsce`](https://code.visualstudio.com/api/working-with-extensions/publishing-extension#vsce)):

   ```bash
   npm install --global vsce
   vsce package
   ```

   This creates a `aloe-<version>.vsix` file.

3. Install the VSIX:

   ```bash
   code --install-extension aloe-<version>.vsix
   ```

4. Activate the theme via `Preferences → Color Theme → Aloe`.

## Recommended Settings

These tweaks pair nicely with the palette:

```json
{
  "editor.fontFamily": "'JetBrains Mono', 'Fira Code', 'Dank Mono', monospace",
  "editor.fontLigatures": true,
  "editor.bracketPairColorization.enabled": true,
  "editor.renderWhitespace": "selection",
  "workbench.activityBar.visible": true
}
```

## Palette Cheatsheet

| Role           | Hex         |
| -------------- | ----------- |
| Background     | `#1a1d1a`   |
| Foreground     | `#d9ebe0`   |
| Primary Accent | `#2d4733`   |
| Selection      | `#2d473344` |
| JSX Variable   | `#f5c97a`   |
| Diff Added     | `#264a3499` |
| Diff Removed   | `#73333399` |

## Color Reference

### Syntax Colors

| Color     | Usage                                              |
| --------- | -------------------------------------------------- |
| `#f5c97a` | JSX variables, attribute names, spread operators   |
| `#7dd3c0` | Functions, call expressions, decorators            |
| `#a8e6a3` | Keywords, control flow, template expression braces |
| `#d99ce8` | Numbers, markup italics, punctuation terminators   |
| `#7dc3e8` | Types, interfaces, readonly variables              |
| `#d9ebe0` | Default variables, plain text                      |
| `#cbd7d1` | Operators, punctuation                             |

### UI Colors

| Color       | Usage                                            |
| ----------- | ------------------------------------------------ |
| `#1a1d1a`   | Editor background, panel background              |
| `#1f221f`   | Line highlight, sidebar headers, widgets         |
| `#2d4733`   | Accent borders, selection, focus states          |
| `#6b8370`   | Disabled text, descriptions                      |
| `#d9ebe0`   | Foreground text, active tab labels               |
| `#7dd3c0`   | Activity bar badge, progress indicators          |
| `#264a3499` | Diff added background (gutter, minimap, ruler)   |
| `#73333399` | Diff removed background (gutter, minimap, ruler) |

### Theming Reference

- [VS Code Theme Color Reference](https://code.visualstudio.com/api/references/theme-color)
- [VS Code Theme Documentation](https://code.visualstudio.com/api/extension-guides/color-theme)
- [VS Code Publishing Extensions](https://code.visualstudio.com/api/working-with-extensions/publishing-extension)

## Token Tweaks

If you want to adjust individual scopes, add overrides to your `settings.json`:

```json
{
  "editor.tokenColorCustomizations": {
    "textMateRules": [
      {
        "scope": "meta.template.expression.js.jsx",
        "settings": { "foreground": "#8fc3a5" }
      }
    ]
  }
}
```

## Contributing

Issues and pull requests are welcome. Feel free to open a ticket for palette suggestions, scope tweaks, or accessibility feedback. Before submitting a PR, run through the diffs in VS Code to confirm colors look right in light/dark contrast checkers.

## Inspiration

Aloe draws inspiration from calm, plant-themed palettes and great community themes like [Halcyon](https://github.com/bchiang7/halcyon-vscode) and [Night Owl](https://github.com/sdras/night-owl-vscode).
