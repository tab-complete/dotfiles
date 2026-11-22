# Tab Complete dotfiles

The config behind the videos on [Tab Complete](https://www.youtube.com/@tabcomplete): one
[stow](https://www.gnu.org/software/stow/) package per episode, and only the tools that
episode actually covers.

## Install a package

Install [Stow](https://www.gnu.org/software/stow/) with `brew install stow`. Each top-level
folder is a package that mirrors `$HOME`; pass `-t "$HOME"` so it works wherever the repo is
cloned:

```sh
git clone https://github.com/tab-complete/dotfiles.git ~/dotfiles-tabcomplete
cd ~/dotfiles-tabcomplete
stow -nv -t "$HOME" karabiner   # preview
stow -v  -t "$HOME" karabiner   # link
```

Remove it with `stow -D -v -t "$HOME" karabiner`.
Stow won't overwrite real files: move an existing target aside first, or use `--adopt`.

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

## Packages

| Package | Episode | Status |
|---|---|---|
| `karabiner` | ep-01 keyboard-only Mac | added |
| `raycast`, `rio`, `nvim` | later episodes | planned |
