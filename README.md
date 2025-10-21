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

2. Replace the Karabiner configuration (likely `~/.config/karabiner/karabiner.json`) with the [configuration](/layouts/macOS/karabiner.json) in the GitHub repository (if you're already using Karabiner, just copy and paste the profile from the GitHub configuration)

### How it works on macOS

The macOS configuration uses Karabiner-Elements to implement the layout through key remapping:

**CapsLock behavior:**
- **Tap** CapsLock: Sends `Esc` (perfect for Vim/Emacs users)
- **Hold** CapsLock: Acts as `Ctrl` (for shortcuts like Ctrl+C, Ctrl+V)

**N-layer modifier:**
The physical `N` key (which appears as J in Colemak) acts as a layer modifier. When you hold N and press other keys:

**Navigation (hold N + home row):**
- `D` → Left arrow
- `F` → Right arrow
- `J` → Down arrow
- `K` → Up arrow

**Brackets and braces (hold N + top row):**
- `Q` → `[`
- `W` → `]`
- `E` → `{`
- `R` → `}`

**Parentheses (hold N + left home row):**
- `A` → `(`
- `S` → `)`

**Quotes (hold N + various keys):**
- `V` → `"` (double quote)
- `B` → `'` (single quote)
- `G` → `:` (colon)
- `H` → `^` (caret)
- `L` → `"` (double quote)
- `;` → `'` (single quote)

**Other remappings:**
- `'` (apostrophe key) → `Backspace` (moved next to Enter)
- `[` and `]` keys → `Z` (to match Linux layout)
- Full Colemak letter remapping (only active when English input is selected)

**Removal**

To return to the default layout, create a new profile through the Karabiner GUI (under `Profiles`) and switch to it. To uninstall completely, remove the `Programmer Colemak` profile or uninstall Karabiner.

## [Linux]

### [X Windowing System]

Replace these system files:
* `/usr/share/X11/xkb/rules/evdev.xml` - adds the layout to the system's keyboard layout list
* `/usr/share/X11/xkb/symbols/us` - contains the actual key mappings

**Note:** You may need to restart your X session or run `setxkbmap programmer-colemak1` to activate the layout.

### How it works on Linux

The Linux configuration uses XKB (X Keyboard Extension) to implement the layout at a lower level:

**CapsLock behavior:**
- CapsLock → `Ctrl` (always acts as Control, no Esc on tap like macOS)

**Base layout:**
- Full Colemak letter remapping (QWERTY → Colemak)
- Standard number row (1-9-0, symbols on Shift)

**Third level (ISO_Level3_Shift) modifier:**
The physical `K` key (which appears as N in Colemak) at position `<AB06>` acts as the `ISO_Level3_Shift` modifier. Hold this key and press others to access:

**Brackets and braces (Level3 + top row):**
- `Q` → `[`
- `W` → `]`
- `F` → `{`
- `P` → `}`

**Parentheses and navigation (Level3 + home row left):**
- `A` → `(`
- `R` → `)`
- `S` → Left arrow
- `T` → Right arrow

**More special characters (Level3 + home row right):**
- `G` → `:` (colon)
- `K` → `^` (caret)
- `N` → Down arrow
- `E` → Up arrow
- `I` → `"` (double quote)
- `O` → `'` (single quote)

**Quotes (Level3 + bottom row):**
- `V` → `"` (double quote)
- `M` → `'` (single quote)

**Other remappings:**
- Quote key (`<AC11>`) → `Backspace`
- Left Ctrl key (`<LCTL>`) → `Z`
- Keys `<AD11>` and `<AD12>` (normally `[` and `]`) → `Z`
