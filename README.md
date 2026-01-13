### How to use dotfiles with GNU Stow

1. Create `~/dotfiles`
2. Create directory structure relative as if the `dotfiles` directory was `~`
3. Move existing files into the `dotfiles` directory. For example: `mv ~/.config/nvim/*` `~/dotfiles/nvim/.config/nvim/`
4. Then run `stow nvim`

```
├── nvim
│   └── .config
│       └── nvim
│           ├── init.lua
│           ├── stylua.toml
│           └── lua
├── waybar
│   └── .config
│       └── waybar
│           ├── config.jsonc
│           └── style.css
├── hyprland
│   └── .config
│       └── hypr
│           ├── bindings.conf
|           ├── hyprland.conf
|           ├── input.conf
│           └── monitors.conf
```
### How to install on a new machine

1. Clone the repo and `cd` in there.
2. For each package in the repo that you want symlinked, run `stow <package>` (e.g. `stow nvim`). You will need to use `--adopt` if the package already exists on the machine. This creates a symlink for the package to your dotfiles repo.
