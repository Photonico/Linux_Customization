# KDE Plasma Settings and Widgets

## Kvantum Manager

* Install
  * ArchLinux: `sudo pacman -S kvantum`

* Kvantum themes store: [KDE Store](https://store.kde.org/browse?cat=123&ord=latest)
  * Themes: `Relax Light Kvantum`, `Blur Glassy Kvantum`, `pearKV`

## Appearance

* Application Style: `kvantum`

* Global Theme: `Breeze`, `Spectrum`, `WinSur`

* Plasma theme: `Colloid`, `Canta`, `Fulent`, `Layan-light`, `Inverse`, `Spectrum`, `Afterglow`

* Colors: `Optical Breeze`, `Pear`
  * Colors path: `~/.local/share/color-schemes`

* Window Decorations: `Breeze`, `OpenMandriva`

* Fonts
  * General: `CMU Concrete Bold`
  * Fixed with: `FantasqueSansMono Nerd Font`, `Fira Comp`
  * Small: `CMU Concrete @ 9pt`
  * Toolbar: `CMU Concrete Bold`
  * Menu: `CMU Concrete Bold`
  * Window title: `CMU Concrete Bold`

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

* Windows Management
  * KWin Scripts
    * Minimize All: Active
    * Force Blur: Active
    * Latte Window Colors: Active

## Konsole

* Color scheme: `GitHub Light`

## Widgets

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

## rEFind

* Download from repository
  * ArchLinux: `sudo pacman -S refind`

* Installation: `sudo refind-intall`

* rEFind configuration: `/boot/efi/EFI/refind/refind.conf`
  * Hide useless option: `dont_scan_dirs /EFI/BOOT,/EFI/arch`

* rEFind themes
  * Quick installation for Regular theme: `sudo bash -c "$(curl -fsSL https://raw.githubusercontent.com/bobafetthotmail/refind-theme-regular/master/install.sh)"`
  * ArchLinux: `yay -S refind-theme-dracula refind-theme-nord refind-theme-regular-git`
