# Luke's build of dwm

## FAQ

> What are the bindings?

This is suckless, mmmbud, the source code is the documentation! Check out [config.h](config.h).

Okay, okay, actually I keep a readme in `larbs.mom` for my whole system, including the binds here.
Press <kbd>super+F1</kbd> to view it in dwm (zathura is required for that binding).
I haven't kept `man dwm`/`dwm.1` updated though. PRs welcome on that, lol.

## Patches and features

- [Clickable statusbar](https://dwm.suckless.org/patches/statuscmd/) with my build of [dwmblocks](https://github.com/lukesmithxyz/dwmblocks).
- Reads [xresources](https://dwm.suckless.org/patches/xresources/) colors/variables (i.e. works with `pywal`, etc.).
- scratchpad: Accessible with <kbd>mod+shift+enter</kbd>.
- New layouts: bstack, fibonacci, deck, centered master and more. All bound to keys <kbd>super+(shift+)t/y/u/i</kbd>.
- True fullscreen (<kbd>super+f</kbd>) and prevents focus shifting.
- Windows can be made sticky (<kbd>super+s</kbd>).
- [hide vacant tags](https://dwm.suckless.org/patches/hide_vacant_tags/) hides tags with no windows.
- [stacker](https://dwm.suckless.org/patches/stacker/): Move windows up the stack manually (<kbd>super-K/J</kbd>).
- [shiftview](https://dwm.suckless.org/patches/nextprev/): Cycle through tags (<kbd>super+g/;</kbd>).
- [vanitygaps](https://dwm.suckless.org/patches/vanitygaps/): Gaps allowed across all layouts.
- [swallow patch](https://dwm.suckless.org/patches/swallow/): if a program run from a terminal would make it inoperable, it temporarily takes its place to save space.


## Installation for newbs

```bash
sudo apt-get install git xorg libx11-dev libxft-dev libxinerama-dev suckless-tools libharfbuzz-dev xrandr -y
cd st
sudo make install
cd
git clone https://github.com/LukeSmithxyz/dwm.git
cd dwm
vim config.h #Make sure that the terminal and browers is to your choice
sudo make clean install
touch .xinitrc
vim .xinitrc
and paste
exec dwm &
xrdb ~/.Xresources &
exec slstatus
xrandr -s 1920x1080
Escape
:x
cd /usr/share/xsessions
sudo vim dwm.desktop
and paste
[Desktop Entry]
Encoding=UTF-8
Name=Dwm
Comment=the dynamic window manager
Exec=dwm
Icon=dwm
Type=XSession
Escape
:x
use this tool to get a working multi monitor set up command (make sure to add refresh rate if needed (-r )  add the xrandr command into the end of the .xinitrc file
sudo logout
Then log in with DWM
Run the xrandr command in DWM (Use Super + D to run your terminal)
Follow this guide and add xrander to the autostart
https://www.ubuntupit.com/how-to-auto-execute-linux-startup-scripts-and-commands/

```

Important Keybindings

Super + D to run apps
Super + Q to close apps
Super + B to enable free floting windows
Super + Left Mouse = Alt Drag
Super + Right Mouse = Resizing windows
Super + F for full screen
killall dwm ends dwm
Super + V opens search


(thanks to this guide for fixing the errors of the main branch lol https://scribe.privacydev.net/hacker-toolbelt/dwm-windows-manager-in-ubuntu-14958224a782)
