# KDE Plasma Settings and Widgets

## Kvantum Manager

* Install
  * Arch Linux: `sudo pacman -S kvantum`

* Kvantum themes store: [KDE Store](https://store.kde.org/browse?cat=123&ord=latest)
  * Themes: `Relax Light Kvantum`, `Blur Glassy Kvantum`, `pearKV`

## Appearance

* Application Style: `kvantum`

* Global Theme: `Breeze`, `Spectrum`, `WinSur`

* Plasma theme: `Lightly Plasma`, `Colloid`, `Canta`, `Fulent`, `Layan-light`, `Inverse`, `Spectrum`, `Afterglow`

* Colors: `Optical Breeze`, `Pear`
  * Colors path: `~/.local/share/color-schemes`

* Window Decorations: `Breeze`, `OpenMandriva`

* Fonts
  * General: `Arbutus Slab @ 10pt`, `CMU Concrete Bold`
  * Fixed with: `Photonico Code @ 12pt`, `FantasqueSansMono Nerd Font`, `Fira Comp`
  * Small: `Arbutus Slab @ 8pt`, `CMU Concrete @ 9pt`
  * Toolbar: `Arbutus Slab @ 10pt`, `CMU Concrete Bold`
  * Menu: `Arbutus Slab @ 10pt`, `CMU Concrete Bold`
  * Window title: `Arbutus Slab @ 10pt`, `Trocchi`, `CMU Concrete Bold`

* Icons: `Tela circle`, `Sadri`

* Display Configure
  * Global scale
    * FHD: `106.25%`
    * QHD: `162.50%`
    * UHD: `212.50%`

## Workspace Behavior

* Workspace Behavior
  * General Behavior
    * Clicking files or folders: `Select them`  
  * Desktop Effects - Blur
    * Blur Strength: `1`
    * Noise Strength: `8`
  * Desktop Effects: LightlyShaders
    * Install for Arch Linux: `yay -S lightlyshaders-git`

* Windows Management
  * KWin Scripts
    * Minimize All: Active
    * Force Blur: Active
    * Latte Window Colors: Active

## Konsole

* Color scheme: `GitHub Light`

## Widgets

* Google client for KDE
  * Arch Linux: `sudo pacman -S kio-gdrive`

* Time Format: `ddd MMM dd yyyy`, `long date`
  * Font: `Latin Modern Roman Unslanted`

* Active Window Control
  * Appearance
    * Cancel: `Fill width`, `Show window title`
    * Enable: `Hide titlebar for maximized windows`

* Physical situation monitor
  * Thermal monitor

* System monitor
  * Simple system monitor
  * Netspeed widget

* Clock
  * Better inline Clock
  * Digital Clock BE Style

* GPU Shifter
  * Prime Render Offload Status
  * nvitel

## Latte Dock

* Behavior
  * Visibility: `Dodge Active`
  * Delay
    * Show: `0`
    * Hide: `100`

* Appearance
  * Margins
    * Length: `10%`
    * Thickness: `20%`
    * Screen edge: `8px`
  * Background
    * Size: `100%`
    * Opacity: `40%`
    * Radius: `25%`
    * Active effect: `All corners`

* Effect
  * Style: `Dots`
  * Position: `10%`

## Configuration

* Monitor configuration initialization: `sudo rm -rf .local/share/kscreen`

## rEFind

* Download from repository
  * Arch Linux: `sudo pacman -S refind`

* Installation: `sudo refind-install`

* rEFind configuration: `/boot/efi/EFI/refind/refind.conf`
  * Hide useless option: `dont_scan_dirs /EFI/BOOT,/EFI/arch`

* rEFind themes
  * Quick installation for Regular theme: `sudo bash -c "$(curl -fsSL https://raw.githubusercontent.com/bobafetthotmail/refind-theme-regular/master/install.sh)"`
  * Arch Linux: `yay -S refind-theme-dracula refind-theme-nord refind-theme-regular-git`
