# My build of st - the simple (suckless) terminal

The [simple terminal (st)](https://st.suckless.org/) with some additional features.

## Features

+ Ligatures.
+ JetBrains Mono typeface at 15pt by default.
+ Three-line (configurable via config.h) scrollback using mouse wheel only.
+ Color scheme inspired by the One Dark syntax theme for the Atom text editor.

## Bindings

+ **Scrollback** with `MouseWheel` or `Shift+{PageUp, PageDown}`
+ **Zoom/change font size** with `Shift+Ctrl+{PageUp, PageDown}`

## Installation on Arch Linux and Arch Linux based distributions

```
git clone https://github.com/monosans/st
cd st
makepkg -si
```

## Installation on other distributions

At first you'll need to install the `JetBrains Mono` typeface. But you can easily get rid of this dependency by changing `JetBrains Mono` to `monospace` in **config.h**.
```
git clone https://github.com/monosans/st
cd st
sudo make clean install
```

## Important note for OpenBSD users

Be sure to edit `config.mk` first and remove `-lrt` from the `$LIBS` before compiling.

## Uninstallation on Arch Linux

`sudo pacman -Rns st-monosans-git`

## Uninstallation on other distributions

```
git clone https://github.com/monosans/st
cd st
sudo make clean uninstall
```
