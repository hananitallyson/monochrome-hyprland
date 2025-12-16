# MONOCHROME HYPRLAND

Welcome to the Monochrome Hyprland Guide! A minimal Hyprland setup for Arch Linux, focused on looks and simplicity.

## GETTING STARTED
This guide assumes prior knowledge of Linux, with a focus on [Arch Linux](https://archlinux.org/). The following prerequisites are required.

### Getting the AUR Helper

Paru (or any other AUR helper like yay) simplifies the search, compilation, and installation of packages that are not in the official Arch repositories, but rather in the AUR (Arch User Repository). Installing it is a crucial step in Arch Linux to manage community packages.

```txt
sudo pacman -S --needed git base-devel
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si
```

### Text and Code Editor

Any text editor will suffice. This guide will use vim and neovim for demonstration purposes, but feel free to use your editor of choice (nano, etc.).

```bash
sudo pacman -S vim neovim
```

### Getting Multilib

To enable multilib support in pacman, edit the configuration file:

```bash
sudo vim /etc/pacman.conf
```

Scroll down until you find the following lines:

```ini
#[multilib]
#Include = /etc/pacman.d/mirrorlist
```

Then remove the leading #:

```ini
[multilib]
Include = /etc/pacman.d/mirrorlist
```

Save the file and exit the editor. Then, synchronize the package databases:

```bash
sudo pacman -Syu
```

### Video Stack

Install the necessary graphics drivers and libraries for proper GPU support, rendering, and video acceleration. I use AMD, so I'm installing the packages for AMD.

```bash
sudo pacman -S mesa, lib32-mesa, xf86-video-amdgpu, vulkan-radeon, lib32-vulkan-radeon
```

### Audio Stack

Set up PipeWire and related components for a modern, flexible audio system with volume and device management.

```bash
sudo pacman -S pipewire pipewire-alsa pipewire-pulse pipewire-jack wireplumber pavucontrol pamixer
```

### Nerd Fonts & Extra Fonts

Install Nerd Fonts and additional fonts to ensure proper icon support, emoji rendering, and multilingual text display.

```bash
sudo pacman -S nerd-fonts noto-fonts noto-fonts-emoji noto-fonts-cjk ttf-dejavu ttf-liberation ttf-ubuntu-font-family
```

### Display Manager

SDDM is recommended for Hyprland, but Ly is fully compatible—simpler, cleaner, and ideal for this minimal setup.

```bash
sudo pacman -S ly
```

Then, you need to enable the Ly service:

```bash
sudo systemctl enable ly@tty2.service
```

### Archiving Utility

Tar is a command-line utility for creating and extracting archives. It’s essential for handling various packages and files.

```bash
sudo pacman -S tar
```
