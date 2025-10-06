# Post Install

This guide was written for Fedora 42 KDE Plasma Desktop.

## Update System

```sh
sudo dnf update
```

## Add Flathub as Source

Open the Discover app, then add Flathub as a source. It should look like the image below:

![Discover Settings](./assets/discover-settings.png)

## Optimizations

### Boot Time

```sh
sudo systemctl disable NetworkManager-wait-online.service
```

### DNF

```sh
echo -e "[main]\ninstall_weak_deps=False" | sudo tee -a /etc/dnf/dnf.conf
sudo dnf update
```

### Power Profiles (for Laptops)

Open the System Settings app, then navigate to **Power Management** and set the following:

- **On AC Power**
  Switch to power profile: Performance
- **On Battery**
  Switch to power profile: Balanced
- **On Low Battery**
  Switch to power profile: Power Save

## Essentials

> [!NOTE]
> "Essentials" is subjective.

```sh
sudo dnf install git git-lfs gh stow kitty fish fd-find ripgrep
```

### Zen Browser

Install via Flatpak using the Discover app.

### Zed Editor

```sh
curl -f https://zed.dev/install.sh | sh
```

### Nix

```sh
sh <(curl --proto '=https' --tlsv1.2 -L https://nixos.org/nix/install) --no-daemon
```

## Remove Bloatware

> [!NOTE]
> "Bloatware" is subjective.

```sh
sudo dnf remove firefox kmahjongg kmines konsole kpat
sudo dnf autoremove
rm -rf ~/.{mozilla,cache/mozilla}
```
