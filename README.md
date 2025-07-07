# My DWM Configuration

This is my custom build of dwm (Dynamic Window Manager) with several patches and customizations.

## Changes from Original DWM

### Patches Applied
- **AlwaysCenter**: Makes new floating windows always appear in the center
- **AttachBottom**: New windows are added at the bottom of the stack
- **MoveStack**: Allows moving windows through the stack
- **NoBorder**: Removes borders when only one window is visible
- **PerTag**: Per-tag window behavior settings
- **Warp**: Warps cursor to center of newly focused windows

### Custom Keybindings
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

2. Build and install:
```sh
make clean install
```

## Setup
### No desktop manager
Add to ~/.xinitrc:
```sh
exec dwm
```

### With a desktop manager
Create a script that start dwm
```sh
sudo nano /usr/local/bin/startdwm
```

```sh
#!/bin/sh

#feh --bg-scale ~/Download/black.png
ibus-daemon -drxR
slstatus &
dwmblocks &


while true; do
        # Log stderror to a file
        dwm 2> ~/.dwm.log
        # No error loggin
        #dwn >/deb/null 2>&1
done
```

Create a .desktop file for xsessions
```sh
[Desktop Entry]
Encoding=UTF-8
Name=dwm
Comment=Dynamic window manager
Exec=/usr/local/bin/startdwm
Icon=dwm
Type=XSession
```
Now change the session to dwm when login

## Usage

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
