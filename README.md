# Global Menu for Gnome

![Fildem](https://user-images.githubusercontent.com/19943481/95288612-1d272a80-083f-11eb-9400-be88f61e054d.png)

## Installation

### Arch

Run `sudo pacman -S python-fildem`


### Extension

`git clone https://github.com/corneal64/Gnome-Global-Menu.git && cd Gnome-Global-Menu && cp -r fildemGMenu@gonza.com ~/.local/share/gnome-shell/extensions/`


## Configuration

In order for the application to work, you must configure the following files (applies to all operating systems):

- Create the file `~/.gtkrc-2.0` and append `gtk-modules="appmenu-gtk-module"`
- The file `~/.config/gtk-3.0/settings.ini` should have the line `gtk-modules="appmenu-gtk-module"` under [Settings]. If it doesn’t exist create it and paste the following

```
[Settings]
gtk-modules="appmenu-gtk-module"
```

## Running

After installation you’ll have two executables, `fildem` and `fildem-hud`.  To check if it works use the first one. `fildem-hud` is for using the HUD, if you are on Xorg, you already have it bound to Alt + Space. If you are on Wayland, you can bind some keybinding to that command.

## Customization

### Menu always visible

By default, the menu is visible when you hover the mouse on the panel. If you want the menu to be always visible, unselect “Show menu only when the mouse is over the panel” in the preferences of the extension.

### AppMenu Button always visible

The AppMenu button shows the application name or window title (if you have some extension) in the panel. By default, the fildem extension hides that label when the menu is being shown. If you want it to be always visible, you can unselect “Hide App Menu label” in the preferences of the extension.

### Reduce space between buttons

If the menu shown on the panel is shifted with relation to the one that appears, like this:

![Screenshot from 2021-06-17 11-09-00](https://user-images.githubusercontent.com/864630/122452193-da852880-cf5d-11eb-8ca8-27e481ab682c.png)

you can tweak the "Button padding" in the preferences window of the extension (accessible from the tweak tool).

### Remove space in between buttons

In some gnome themes, the buttons have a small spacing between them. This can make the buttons easy to miss and unfocusing our window if it’s not maximized. To fix this, add this somewhere on your `gnome-shell.css` theme:

```
#panel #panelLeft {
  spacing: 0px; }
#panel #panelLeft .panel-button {
  spacing: 0px; }
```

## Running the program at startup

If you manage to make the program work and want to have it running automatically at startup you can add an entry to `gnome-session-properties` with the name of the program and the path to execute it.

## Create a shortcut for the HUD on Wayland

Since it’s not possible to create a shortcut from the app on Wayland, you have to create it yourself. Go to Settings → Keyboard Shorcuts and create a shortcut that executes `inithud.sh`.

