# Black Atom for Waybar

> Elegant, cohesive themes for Waybar by Black Atom Industries

## What is a Black Atom Adapter?

This repository is a **Waybar adapter** for the Black Atom theme ecosystem. In the Black Atom architecture:

- The [core repository](https://github.com/black-atom-industries/core) is the single source of truth for all theme definitions
- Each adapter implements these themes for a specific platform (Waybar, Neovim, terminals, etc.)
- The adapter uses templates to transform core theme definitions into platform-specific files

This modular approach ensures consistent colors and styling across all supported platforms while allowing for platform-specific optimizations.

## Available Themes

Black Atom includes multiple theme collections, each with its own distinct style:

| Collection   | Description                  | Themes    |
| ------------ | ---------------------------- | --------- |
| **Default**  | Core Black Atom themes       | 4 themes  |
| **JPN**      | Japanese-inspired themes     | 4 themes  |
| **MNML**     | Minimal themes               | 11 themes |
| **Stations** | Space station-inspired       | 4 themes  |
| **Terra**    | Earth seasons-inspired       | 8 themes  |

## Installation

### Prerequisites

- Waybar
- [Black Atom Core](https://github.com/black-atom-industries/core) (for generating themes)

### Setup

1. Clone this repository:

```bash
git clone https://github.com/black-atom-industries/waybar.git
cd waybar
```

2. Generate theme files using Black Atom Core:

```bash
black-atom-core generate
```

3. Copy or symlink the generated CSS file to your waybar config:

```bash
# Option 1: Symlink a specific theme
ln -sf /path/to/waybar/themes/jpn/black-atom-jpn-koyo-yoru.css ~/.config/waybar/theme.css

# Option 2: Copy a theme
cp /path/to/waybar/themes/jpn/black-atom-jpn-koyo-yoru.css ~/.config/waybar/theme.css
```

4. Update your waybar `style.css` to import the theme:

```css
@import "theme.css";
```

Or reference it directly in your waybar config.

## Usage

After installation, restart waybar to apply the theme:

```bash
killall waybar && waybar &
```

## Development

This repository uses the Black Atom adapter pattern. Theme files are generated from templates using the core CLI.

### Repository Structure

```
.
├── LICENSE                     # MIT license
├── README.md                   # This documentation
├── black-atom-adapter.json     # Adapter configuration file
└── themes/                     # Template directory
    ├── default/                # Default collection templates
    │   └── collection.template.css
    ├── jpn/                    # JPN collection templates
    │   └── collection.template.css
    ├── mnml/                   # MNML collection templates
    │   └── collection.template.css
    ├── stations/               # Stations collection templates
    │   └── collection.template.css
    └── terra/                  # Terra collection templates
        └── collection.template.css
```

## License

MIT © Black Atom Industries
