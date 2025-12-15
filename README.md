# hyprland

## Installing Basic Tools

```bash
sudo pacman -S --needed git curl vim
```

## Getting the AUR Helper

Paru (or any other AUR helper like yay) simplifies the search, compilation, and installation of packages that are not in the official Arch repositories, but rather in the AUR (Arch User Repository). Installing it is a crucial step in Arch Linux to manage community packages.

```bash
sudo pacman -S --needed base-devel
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si
```

## Essential Components

```bash
paru -S --needed \
kitty fish ly \
wofi waybar \
pipewire pipewire-alsa pipewire-pulse pipewire-jack wireplumber pavucontrol \
thunar networkmanager \
imv mpv zathura \
nwg-look \
nerd-fonts
```

## Additional Fonts

```bash
paru -S --needed \
noto-fonts noto-fonts-emoji noto-fonts-cjk \
ttf-dejavu ttf-liberation ttf-ubuntu-font-family
```

## Create Default Directories

```bash
paru -S --needed xdg-user-dirs
xdg-user-dirs-update
```


## Thumbnail and Preview Dependencies

```bash
paru -S --needed tumbler poppler-glib ffmpegthumbnailer freetype2 libgsf
```
