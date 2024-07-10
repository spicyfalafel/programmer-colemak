![Programmer Colemak (1)](https://user-images.githubusercontent.com/37231424/157564870-ddb7807e-f0cc-421f-be77-968efcdec4f3.svg)

# Background
1. I tried to type Clojure better and it was strange to use little finger all the time (`[]{}()`) .
2. I wanted to try Colemak or Workman.
3. I wanted to use left, right, up, down easily. Sometimes you have to quit Vim/Emacs and use arrows.

# Layout

The layout is based on [Colemak][colemak] keyboard layout and this repo I've found: https://github.com/aru-py/programmer-colemak.
Changes:
1. New modifier to add arrows and squares into main row.
2. Using CapsLock as Esc and ctrl at the same time.
3. Backspace is moved next to enter.

![keyboard-layout](https://github.com/spicyfalafel/programmer-colemak/assets/58147555/4a7f69d7-299e-455a-ae96-5d8ef0cb4ff4)


# Installation

## [MacOS]

**The installation on macOS is very simple:**

1. Install [Karabiner](https://karabiner-elements.pqrs.org) (you can also use `brew install --cask karabiner-elements`)

2. Replace the Karabiner configuration (likely `~/.config/karabiner/karabiner.json`) with the [configuration](/layouts/macOS/karabiner.json) in the GitHub repository (if you’re already using Karabiner, just copy and paste the profile from the GitHub configuration)

**Note: On macOS, caps lock becomes ⌘, and ⌘ becomes ctrl + shift (⌘ is now a free key that can be remapped to anything you want).**

**Removal**

To return to the default layout, create a new profile through the Karabiner GUI (under `Profiles`) and switch to it. To uninstall completely, remove the `Programmer Colemak` profile or uninstall Karabiner.

## [Linux]

### [X Windowing System]
Just replace files:
* /usr/share/X11/xkb/rules/evdev.xml
* /usr/share/X11/xkb/symbols/us
