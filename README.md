# dotfiles

## Usage

> [!NOTE]
> Make sure to follow [POST_INSTALL](./POST_INSTALL.md) before continuing.

```sh
stow -t ~/.config ~/.dotfiles/.config

# This is intentionally done after Stow because Nix Flakes requires a configuration.
nix profile add \
    nixpkgs#neovim \
    nixpkgs#starship \
    nixpkgs#nerd-fonts.commit-mono
```

### Installing Node

> [!NOTE]
> This is for my own reference because I'm forgetful af.

```sh
nix profile add \
    nixpkgs#nodejs \
    nixpkgs#nodePackages.pnpm
```

## Todo

- [ ] Add Neovim configuration
- [ ] Change default colorscheme from Dracula to Catppuccin
