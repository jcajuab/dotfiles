# dotfiles

## Usage

```sh
git clone https://github.com/jcajuab/dotfiles.git ~/.dotfiles
cd ~/.dotfiles
./setup
```

> [!IMPORTANT]
> Make sure all [prerequisites](#prerequisites) are met before running `setup`.

## Prerequisites

### Fonts

- [CommitMono](https://commitmono.com/)
- [Inter](https://commitmono.com/)

#### Installing Fonts

Here is a quick guide on how to install fonts in Linux. For this example, I am installing CommitMono.

> [!NOTE]
> I am using Fish for the commands below:

```sh
set FONT CommitMono
set TARGET $HOME/.local/share/fonts/$FONT
set URL (curl -s https://api.github.com/repos/eigilnikolajsen/commit-mono/releases/latest \
    | jq -r '.assets[] | select(.name | endswith(".zip")) | .browser_download_url')
set -l ZIP $FONT.zip

mkdir -p -- "$TARGET"
cd /tmp
wget -O "$ZIP" "$URL"
unzip -j "$ZIP" -d "$FONT"
find "$FONT" -type f -iname '*.otf' -exec cp -t "$TARGET" {} +
fc-cache -fv
```

### Programs

- [Fish](https://fishshell.com/)

  ```sh
  dnf install fish
  chsh -s $(which fish) # Set Fish as default shell
  ```

- [Foot](https://codeberg.org/dnkl/foot)

  ```sh
  dnf install foot
  ```

- [Starship](https://starship.rs/)

  ```sh
  curl -sS https://starship.rs/install.sh | sh
  ```

## To-dos

- [ ] Add [Lix](https://lix.systems/)
  - [ ] Add [direnv](https://direnv.net/)
  - [ ] Add [nix-direnv](https://github.com/nix-community/nix-direnv)
- [ ] Add [Neovim](https://github.com/neovim/neovim)
- [ ] Add [Zellij](https://zellij.dev/)
