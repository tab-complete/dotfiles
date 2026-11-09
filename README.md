# Tab Complete dotfiles

The config behind the videos on [Tab Complete](https://www.youtube.com/@tabcomplete): one
[stow](https://www.gnu.org/software/stow/) package per episode, and only the tools that
episode actually covers.

## Install a package

Each top-level folder is a stow package that mirrors `$HOME`.

```sh
git clone https://github.com/tab-complete/dotfiles.git
cd dotfiles && stow karabiner
```

Remove it with `stow -D karabiner`.

## karabiner

Needs [Karabiner-Elements](https://karabiner-elements.pqrs.org/), which asks for Input
Monitoring and its driver the first time.

Caps Lock becomes Ctrl when held and Escape when tapped. Ctrl-h/j/k/l are arrow keys in
any app - editor, browser list, dialog.

| Key | Action |
|---|---|
| Caps Lock (hold) | Ctrl |
| Caps Lock (tap) | Esc |
| Ctrl-h / Ctrl-j / Ctrl-k / Ctrl-l | left / down / up / right |

This file is the live config: it is symlinked to `~/.config/karabiner/karabiner.json`, so
Karabiner picks up edits on save.

The same two rules can be added without the file: Karabiner-Elements → Complex
Modifications → Add predefined rule, then in the gallery **Change caps_lock to dual keys,
escape and left_control**, and **Vi Style Arrows** → *Change Control + h/j/k/l to Arrows*.

## Raycast

Raycast's export is password-encrypted and bundles every setting, so it is not in this
repo. The hotkeys it uses:

| Key | App or action |
|---|---|
| Ctrl-1 | Browser |
| Ctrl-2 | Chat |
| Ctrl-3 | Terminal |
| Ctrl-4 | Editor |
| Ctrl-M | Maximise window to fill the screen |
| Ctrl-Space | Raycast itself |

Set them in Raycast → Settings → Extensions → Applications (per app), and Window
Management (Maximise). Nothing else: the map is by role, so it is the same on every Mac.

## Packages

| Package | Episode | Status |
|---|---|---|
| `karabiner` | ep-01 keyboard-only Mac | added |
| `raycast`, `rio`, `nvim` | later episodes | planned |
