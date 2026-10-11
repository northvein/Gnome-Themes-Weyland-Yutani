# WEYLAND-YUTANI CORPORATION
## GNOME Theme — "Building Better Worlds"
### Clearance Level: EXECUTIVE

---

```
██╗    ██╗███████╗██╗   ██╗██╗      █████╗ ███╗   ██╗██████╗
██║    ██║██╔════╝╚██╗ ██╔╝██║     ██╔══██╗████╗  ██║██╔══██╗
██║ █╗ ██║█████╗   ╚████╔╝ ██║     ███████║██╔██╗ ██║██║  ██║
██║███╗██║██╔══╝    ╚██╔╝  ██║     ██╔══██║██║╚██╗██║██║  ██║
╚███╔███╔╝███████╗   ██║   ███████╗██║  ██║██║ ╚████║██████╔╝
 ╚══╝╚══╝ ╚══════╝   ╚═╝   ╚══════╝╚═╝  ╚═╝╚═╝  ╚═══╝╚═════╝
██╗   ██╗██╗   ██╗████████╗ █████╗ ███╗   ██╗██╗
╚██╗ ██╔╝██║   ██║╚══██╔══╝██╔══██╗████╗  ██║██║
 ╚████╔╝ ██║   ██║   ██║   ███████║██╔██╗ ██║██║
  ╚██╔╝  ╚██╗ ██╔╝   ██║   ██╔══██║██║╚██╗██║██║
   ██║    ╚████╔╝    ██║   ██║  ██║██║ ╚████║██║
   ╚═╝     ╚═══╝     ╚═╝   ╚═╝  ╚═╝╚═╝  ╚═══╝╚═╝
```

---

## OVERVIEW

A fully corporate dark GNOME theme inspired by the Weyland-Yutani Corporation from the *Alien* franchise. Dark phosphor-screen amber on near-black, monospaced terminal typography, cold industrial UI lines, and the unmistakable weight of a megacorporation that controls half the known galaxy.

---

## COLOR SYSTEM

| Token | Hex | Usage |
|-------|-----|-------|
| `wy_bg_darkest` | `#080A08` | Window backgrounds, panel |
| `wy_bg_dark` | `#0D100D` | Primary UI background |
| `wy_bg_mid` | `#111811` | Raised surfaces |
| `wy_amber` | `#C8920A` | Primary accent, borders |
| `wy_amber_bright` | `#E8AA18` | Hover/active states |
| `wy_green_terminal` | `#39FF14` | Terminal text, input |
| `wy_text_primary` | `#C8B896` | Body text |
| `wy_text_secondary` | `#8A7A62` | Dimmed text |
| `wy_red_alert` | `#8B1A1A` | Destructive actions |
| `wy_corp_blue` | `#1A3A5C` | Info states |

**Typography:** `Courier New` / `Courier` monospace throughout.  
This is intentional — MU/TH/UR 6000 doesn't use rounded sans-serifs.

---

## FILES

```
weyland-yutani-theme/
├── index.theme                    ← Theme metadata
├── install.sh                     ← One-shot installer
├── gtk-3.0/
│   ├── gtk.css                    ← GTK3 entry (imports dark)
│   └── gtk-dark.css               ← Full GTK3 stylesheet
├── gtk-4.0/
│   ├── gtk.css                    ← GTK4 entry
│   └── gtk-dark.css               ← Full GTK4 stylesheet
├── gnome-shell/
│   └── gnome-shell.css            ← Shell/panel/notifications
├── wallpapers/
│   └── weyland-yutani-4k.svg      ← 4K SVG wallpaper
└── assets/
    ├── terminal-colors.ini        ← GNOME Terminal color palette
    └── dash-to-panel-settings.json ← Dash to Panel config
```

---

## INSTALLATION

### Quick Install (recommended)
```bash
chmod +x install.sh
./install.sh
```

### Manual Install
```bash
# 1. Copy theme to your themes directory
cp -r weyland-yutani-theme ~/.themes/Weyland-Yutani

# 2. Apply via GNOME Tweaks
sudo apt install gnome-tweaks
# Open Tweaks → Appearance → Applications: Weyland-Yutani

# 3. Apply via command line
gsettings set org.gnome.desktop.interface gtk-theme "Weyland-Yutani"
gsettings set org.gnome.desktop.interface color-scheme "prefer-dark"

# 4. Set wallpaper
gsettings set org.gnome.desktop.background picture-uri \
  "file://$HOME/.themes/Weyland-Yutani/wallpapers/weyland-yutani-4k.svg"
```

### Shell Theme (requires User Themes extension)
```bash
# Install extension
sudo apt install gnome-shell-extensions
# Then install User Themes from extensions.gnome.org/extension/19/

# Apply shell theme
gsettings set org.gnome.shell.extensions.user-theme name "Weyland-Yutani"
```

---

## RECOMMENDED EXTENSIONS

Install from **extensions.gnome.org** or with Extension Manager:

| Extension | Purpose |
|-----------|---------|
| **User Themes** | Required for Shell theme |
| **Dash to Panel** | Full corporate taskbar with config included |
| **Just Perfection** | Fine-tune shell elements |
| **Blur my Shell** | Optional: blur panel for depth |
| **Caffeine** | Keep the terminal awake on long operations |
| **System Monitor** | Live readouts in the panel |

---

## FONT RECOMMENDATIONS

For maximum authenticity, install one of these monospace fonts:

```bash
# Courier Prime (elegant, readable)
sudo apt install fonts-courier-prime

# Share Tech Mono (free, clean)
sudo apt install fonts-share-tech

# Or use the built-in Courier New (already referenced)
```

After installing, set the system monospace font in GNOME Tweaks:
> Fonts → Monospace Text → Courier Prime Regular 11

---

## TERMINAL SETUP

The included `assets/terminal-colors.ini` configures your terminal with:
- **Background:** `#080A08` — deep void
- **Foreground:** `#C8920A` — amber readout
- **Green text:** `#39FF14` — phosphor green for input
- **Full 16-color ANSI palette** tuned to the W-Y aesthetic

The `install.sh` script applies this automatically to your default GNOME Terminal profile.

For **Tilix** or **Kitty**, see the colors in `assets/terminal-colors.ini` and apply manually.

---

## DASH TO PANEL CONFIG

After installing Dash to Panel, import the provided config:

```bash
# Open Dash to Panel settings → hamburger menu → Import
# Or via dconf:
cat assets/dash-to-panel-settings.json | \
  python3 -c "import sys,json; d=json.load(sys.stdin); \
  [print(f'{k}={v}') for k,v in d.items() if not k.startswith('_')]"
```

Config features:
- **Bottom panel**, 36px height
- **Amber accent dots** on running/focused apps
- **24-hour clock with seconds**
- **Near-opaque dark background**
- **Square indicator dots** (xenomorph egg aesthetic)

---

## CUSTOMIZATION

Edit `gtk-3.0/gtk-dark.css` to adjust colors. All values use CSS custom properties defined at the top of the file under `/* --- COLOR PALETTE --- */`.

Key variables:
```css
@define-color wy_amber       #c8920a;  /* ← Change accent color here */
@define-color wy_bg_dark     #0d100d;  /* ← Change background here */
@define-color wy_text_primary #c8b896; /* ← Change text color here */
```

After editing, reload with:
```bash
gsettings set org.gnome.desktop.interface gtk-theme "Default"
gsettings set org.gnome.desktop.interface gtk-theme "Weyland-Yutani"
```

---

## COMPATIBILITY

- **Ubuntu:** 22.04, 24.04
- **GNOME:** 42, 43, 44, 45, 46, 47
- **GTK:** 3.x, 4.x
- **Display:** Works on HiDPI/4K (SVG wallpaper scales perfectly)

---

## KNOWN ISSUES

- GTK4 apps (newer GNOME apps) may have partial theming due to libadwaita defaults. For full control on GTK4, set:
  ```bash
  gsettings set org.gnome.desktop.interface gtk-theme "Weyland-Yutani"
  # AND add to ~/.config/gtk-4.0/settings.ini:
  # [Settings]
  # gtk-application-prefer-dark-theme=1
  ```
- Some Snap/Flatpak apps may not respect the theme. Run them with:
  ```bash
  GTK_THEME=Weyland-Yutani snap run <app>
  ```

---

## LICENSE

*This theme is a fan project inspired by the Alien franchise.*  
*Weyland-Yutani and all related marks are property of 20th Century Studios / Disney.*  
*Theme code is free for personal use.*

---

```
WEYLAND-YUTANI CORPORATION
"Building Better Worlds"
[END OF DOCUMENT — ACCESS LOG RECORDED]
```
