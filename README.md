# My DWM Configuration

This is my custom build of dwm (Dynamic Window Manager) with several patches and customizations.

## Changes from Original DWM

### Appearance
- Custom fonts setup:
  - JetBrains Mono NF as primary font
  - Font Awesome 6 for icons
  - Noto Color Emoji for emoji support
- Modified colors scheme with black accent color
- 1px window borders

### Patches Applied
- **AlwaysCenter**: Makes new floating windows always appear in the center
- **AttachBottom**: New windows are added at the bottom of the stack
- **AutoStart**: Enables running autostart script on dwm startup
- **MoveStack**: Allows moving windows through the stack
- **NoBorder**: Removes borders when only one window is visible
- **PerTag**: Per-tag window behavior settings
- **Warp**: Warps cursor to center of newly focused windows

### Custom Keybindings
- **Alt** as MODKEY (instead of Windows/Super key)
- Media keys support:
  - Brightness control (brightnessctl)
  - Volume control (pactl)
  - Screenshot (flameshot)

## Installation

1. Install dependencies:
```sh
sudo apt install build-essential libx11-dev libxft-dev libxinerama-dev xorg \
                 brightnessctl pulseaudio flameshot
```

2. Install required fonts:
```sh
# Install JetBrains Mono Nerd Font
# Install Font Awesome 6
# Install Noto Color Emoji
```

3. Build and install:
```sh
make clean install
```

## Usage

Add to ~/.xinitrc:
```sh
exec dwm
```

### Key Bindings

- Alt + Enter: Open terminal (Alacritty)
- Alt + p: Open dmenu
- Alt + b: Toggle status bar
- Alt + j/k: Focus next/previous window
- Alt + Shift + j/k: Move window in stack
- Alt + [1-9]: Switch to tag
- Alt + Shift + c: Close window
- Alt + Shift + q: Quit dwm
- Print Screen: Screenshot (Flameshot)
- Brightness/Volume Keys: Hardware keys work directly

### Mouse Bindings
- Alt + Left Click: Move window
- Alt + Right Click: Resize window
- Alt + Middle Click: Toggle floating

## Credits
Based on [dwm](https://dwm.suckless.org/) by suckless.org