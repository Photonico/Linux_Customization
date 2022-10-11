# Linux System Settings and Packages

The major distro demonstrated is Arch with KDE desktop.

## System Hostname

* Show current hostname: `hostnamectl`

* Edit static hostname: `sudo vim /etc/hostname`
  or `sudo hostnamectl set-hostname <your hostname>`

* Edit network hostname: `sudo vim /etc/hosts`
  127.0.0.1 localhost
  127.0.0.1 localhost.localdomain your_hostname
  ::1       localhost
  127.0.1.1 localhost.localdomain your_hostname

* Set TTY login
  * Setting: `sudo systemctl set-default multi-user.target`
  * Login to GUI desktop: `startx`

## Driver

* Intel integrated GPU
  * ArchLinux: `sudo pacman -S mesa lib32-mesa vulkan-intel lib32-vulkan-intel mesa-demos`

* AMD integrated and discrete GPU
  * ArchLinux: `sudo pacman -S mesa lib32-mesa xf86-video-amdgpu vulkan-radeon lib32-vulkan-radeon libva-mesa-driver lib32-libva-mesa-driver mesa-vdpau lib32-mesa-vdpau`

* Nvidia discrete driver
  * ArchLinux: `sudo pacman -S nvidia-lts nvidia-setting nvidia-dkms nvidia-utils lib32-nvidia-utils nvidia-prime`
  * openSUSE:
    * Add repository: `sudo zypper addrepo --refresh https://download.nvidia.com/opensuse/tumbleweed NVIDIA`
    * Refresh repositories list: `sudo zypper refresh`
    * Get the hardware information: `lspci | grep VGA`, `lscpu | grep Arch`
    * Search Nvidia hardware code: [Nvidia](https://www.nvidia.com/Download/index.aspx)
    * Search driver from repository: `zypper se -s x11-video-nvidiaG0*`, `zypper se -s nvidia-glG0*`
    * Install the driver: `sudo zypper install x11-video-nvidiaG06`
    * Install the OpenGL accelerator: `sudo zypper install nvidia-glG06`

* Optimus
  * ArchLinux: `yay -S optimus-manager optimus-manager-qt`
    * Active optimus: `sudo systemctl enable optimus-manager`

* Nvidia Prime
  * Demonstrate the current GPU: `glxinfo | grep -i render | grep -Ei 'intel|nvidia'`
  * ArchLinux: `sudo pacman -S nvidia-prime`
    * Dynamic switch: `prime-run <program>`
  * openSUSE: `sudo zypper suse-prime`
    * Switch to NVidia GPU: `sudo prime-select nvidia`
    * Switch to Intel GPU: `sudo prime-select intel`

* Printer
  * ArchLinux: `sudo pacman -S hplip cups`
  * Enable server: `sudo systemctl enable --now cups.service`

* BlueTooth
  * ArchLinux: `sudo pacman -S bluez bluez-utils pulseaudio-bluetooth`
    * Enable: `sudo systemctl enable --now bluetooth` 

* KeyChron Keyboard Function Keys  
  * Method 1: `https://github.com/adam-savard/keychron-k2-function-keys-linux`
  * Method 2: `KeyChron Linux Function Keys`  
    * Set the keyboard to Windows mode via the side switch;
    * Use `Fn` + `X` + `L` to set the function key row to “Function” mode;
    * `echo 0 | sudo tee /sys/module/hid_apple/parameters/fnmode`
    * `echo "options hid_apple fnmode=0" | sudo tee -a /etc/modprobe.d/hid_apple.conf`

* Hardware information
  * Check hardware information: `sudo dmidecode`
  * ArchLinux: `yay -S cpu-x gpu-viewer`

* CPU benchmark
  * ArchLinux: `sudo pacman -S sysbench hyperfine`
  * ArchLinux AUR: `yay -S ohoronix-test-suite`
  * openSUSE: `sudo zypper -install sysbench hyperfine`

* GPU benchmark
  * ArchLinux: `sudo pacman -S mesa-utils`
  * ArchLinux AUR: `yay -S glmark2`
  * openSUSE: `sudo zypper -install mesa-utils`

## Fonts

* Adobe source fonts
  * ArchLinux: `sudo pacman -S adobe-source-sans-fonts adobe-source-serif-fonts adobe-source-han-sans-cn-fonts adobe-source-han-serif-cn-fonts`
  * openSUSE: `sudo zypper -S adobe-sourcesanspro-fonts adobe-sourceserifpro-fonts adobe-sourcehansans-cn-fonts adobe-sourcehanserif-cn-fonts`

* Century Schoolbook
  * via Git: `https://github.com/TimothyGu/Century-Schoolbook-L/tree/gh-pages/fonts`
  * ArchLinux: `yay -S ttf-century-schoolbook tex-math-millennial`

* CJK fonts:
  * ArchLinux: `sudo pacman -S noto-fonts noto-fonts-cjk noto-fonts-extra noto-fonts-emoji`
  * openSUSE: `sudo zypper install noto-sans-cjk-fonts`

* CMU Serif
  * ArchLinux: `yay -S ttf-cm-unicode ttf-cmu-typewriter`
  * openSUSE: `sudo zypper install cm-unicode-fonts`

* Courier Code
  * ArchLinux: `yay -S ttf-courier-prime-code ttf-courier-code`

* GNU free fonts
  * ArchLinux: `sudo pacman -S gnu-free-fonts`
  * openSUSE: `zypper install gnu-free-fonts`

* Latin
  * ArchLinux: `sudo pacman -S otf-latin-modern otf-latinmodern-math`

* Nerd fonts: [Nerd Fonts](https://www.nerdfonts.com/)
  * ArchLinux: `yay -S nerd-fonts-complete`

* WQY fonts:
  * ArchLinux: `sudo pacman -S wqy-zenhei wqy-microhei`
  * openSUSE: `sudo zypper install wqy-bitmap-fonts wqy-microhei-fonts wqy-zenhei-fonts`

## Development packages

* Basic development libs
  * ArchLinux: `sudo pacman -S base-devel`
  * openSUSE: `sudo zypper install -t pattern devel_basis`
  * RedHat: `sudo dnf group install 'Development Tools'`
  * Solus: `sudo eopkg install -c system.devel`

* C/C++ development environment
  * ArchLinux: `sudo pacman -S gcc`
  * openSUSE: `zypper install -t pattern devel_C_C++`
  * Solus: `sudo eopkg install -c system.devel`

* CMake
  * ArchLinux: `sudo pacman -S cmake make`
  * openSUSE: `sudo zypper install cmake make`
  
* Dynamic Kernel Module Support
  * ArchLinux: `sudo pacman -S dkms`
  * openSUSE: `sudo zypper install dkms`

* Expect
  * ArchLinux: `sudo pacman -S expect`
  * openSUSE: `sudo zypper in expect`

* Linear Algebra Library Eigen
  * ArchLinux: `sudo pacman -S eigen`
  * openSUSE: `sudo zypper in eigen3-devel eigen3-doc`

* Linear Algebra Library openCL
  * ArchLinux: `sudo pacman -S opencl-clhpp opencl-headers`
  * openSUSE: `sudo zypper in eigen3-devel eigen3-doc`

* LLVM
  * ArchLinux: `sudo pacman -S llvm clang`
  * openSUSE: `sudo zypper install llvm llvm-clang`

* Node.js and NPM
  * ArchLinux: `sudo pacman -S nodejs npm`

* Python Devel headers
  * openSUSE: `sudo zypper in python-dev`

* Python QT support
  * Pip: `pip install pyqt5 pyqt6`

* QEMU with KVM acceleration
  * openSUSE: `sudo zypper in qemu-kvm`

* LibXC
  * openSUSE:
    * Add repository: `sudo zypper addrepo https://download.opensuse.org/repositories/science/openSUSE_Tumbleweed/science.repo`
    * Refresh repositories list: `sudo zypper refresh`
    * Install: `sudo zypper install libxc`

* Nvidia CUDA
  * ArchLinux: `sudo pacman -S cuda`
  * openSUSE:
    * CUDA Introduction: [CUDA](https://developer.nvidia.com/accelerated-computing-toolkit)
    * CUDA Download and installation: [CUDA](https://developer.nvidia.com/cuda-downloads)
    * Find the highest CUDA version the installed driver support: `nvidia-smi`
    * CUDA API  
    * CUDA for Python: CuPy(Cuda 11.4): `pip3 install cupy-cuda114`
      * Detail: [CuPy Dev](https://docs.cupy.dev/en/stable/install.html?highlight=install#requirements)
    * Add repository: `sudo zypper addrepo https://developer.download.nvidia.com/compute/cuda/repos/opensuse15/x86_64/cuda-opensuse15.repo`
    * Refresh repositories list: `sudo zypper refresh`
    * Installation: `sudo zypper install -y cuda`

## Terminal Packages

* Htop
  * ArchLinux: `sudo pacman -S htop`
  * openSUSE: `sudo zypper install htop`

* SSH
  * ArchLinux: `sudo pacman -S openssh`

* Yakuake  
  * ArchLinux: `sudo pacman -S yakuake`
  * openSUSE: `sudo zypper install yakuake`

* Zsh
  * ArchLinux: `sudo pacman -S zsh`
  * openSUSE: `sudo zypper install zsh`

## Softwares

* Libre Office
  * ArchLinux: `sudo pacman -S libreoffice-still`

* DarkTable
  * Avoid trick files automatically: Preferences -> Storage -> XMP:
    * Write sidecar file for each image: `never`
    * Store XMP tags in compressed format: `never`

* Google Chrome
  * openSUSE:
    * Add repository: `sudo zypper addrepo http://dl.google.com/linux/chrome/rpm/stable/x86_64 Google-Chrome`
    * Add key: `wget https://dl.google.com/linux/linux_signing_key.pub`
    * Import key: `sudo rpm --import linux_signing_key.pub`
    * Refresh repositories list: `sudo zypper refresh`
    * Install: `sudo zypper in google-chrome-stable`

* Images View
  * Gwenview Configure
    * General
      * Lossy image save quality: `100%`
  * Geeqie
    * ArchLinux: `sudo pacman -S geeqie`
    * openSUSE: `sudo zypper install geeqie`
  * Nomacs
    * ArchLinux: `sudo pacman -S nomacs`
    * openSUSE: `sudo zypper install nomacs`
  * Feh
    * ArchLinux: `sudo pacman -S Feh`
    * openSUSE: `sudo zypper install Feh`

* Fcitx 5
  * ArchLinux: `sudo pacman -S fcitx5-im fcitx5-chinese-addons fcitx5-pinyin-zhwiki fcitx5-material-color fcitx5-nord`
  * openSUSE: `sudo zypper install fcitx5`
  * Edit environment profile: `EDITOR=vim sudoedit /etc/environment`
    * Theme: `KDE Plasmad`

* Screenshot tools
  * FlameShot
    * ArchLinux: `sudo pacman -S flameshot`
    * openSUSE: `sudo zypper install flameshot`
  * Spectacle
    * ArchLinux: `sudo pacman -S spectacle`
    * openSUSE: `sudo zypper install spectacle`

* qBittorrent
  * ArchLinux:
  * openSUSE: `sudo zypper install qbittorrent`

* Steam
  * Steam Proton
    View > Settings > Steam Play and toggle the option:  
      Enable: Steam Play for Supported Titles
  * HiDPI via Official Support
    View > Settings > Interface
  * HiDPI via General Settings
    * File direction: `~/.local/share/applications/steam.desktop`
      * ArchLinux: `/usr/share/applications/steam.desktop`  
    * From this: `Exec=/usr/bin/steam %U`
      * ArchLinux: `Exec=/usr/bin/steam-runtime %U`
    * To this: `Exec=env GDK_SCALE=2 /usr/bin/steam %U`
      * ArchLinux: `Exec=env GDK_SCALE=2 /usr/bin/steam-runtime %U`
    * Active the editing: `source ~/.local/share/applications/steam.desktop`
      * ArchLinux: `source /usr/share/applications/steam.desktop`

* Vesta
  * ArchLinux: `yay -S vesta`
  * openSUSE: `sudo zypper install vesta`

* VSCode
  * ArchLinux: `yay -S visual-studio-bin`
  * openSUSE:
    * Import key: `sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc`
    * Add repository: `sudo zypper addrepo https://packages.microsoft.com/yumrepos/vscode vscode`
    * Refresh repositories list: `sudo zypper refresh`
    * Install VSCode: `sudo zypper install code`

* Wakatime for Kate: `https://github.com/wakatime/kate-wakatime/blob/master/README.md`

* Mudfish
  * Install the necessary libraries
    * ArchLinux: `sudo pacman -S libappindicator-gtk3`
    * Fedora: `sudo dnf install libappindicator-gtk3`
  * Download manually: `[MUDFISH](https://mudfish.net/download)`
  * Run `mudrun` after installation

## Repositories

* YAY AUR packages management (ArchLinux)
  * Clone YAY project: `git clone https://aur.archlinux.org/yay.git`
  * Active directory: `cd yay`
  * Start the building process: `makepkg -si`

* Packman (openSUSE)
  * Add repository: `sudo zypper ar -cfp 90 https://ftp.gwdg.de/pub/linux/misc/packman/suse/openSUSE_Tumbleweed/ packman`
  * Refresh repositories list: `sudo zypper refresh`
  * Apply change: `sudo zypper dup --from packman --allow-vendor-change`
  * Install multimedia packages: `sudo zypper install --from packman ffmpeg gstreamer-plugins-{good,bad,ugly,libav} libavcodec-full vlc-codecs`

## Python environment

* Switch default Python3 version (Linux)
  * Show alternatives: `sudo update-alternatives --config python`
  * Clean alternatives list: `sudo update-alternatives --remove-all python`
  * Update the `update-alternatives`: `sudo update-alternatives --install /usr/bin/python3 python /usr/bin/python<version> 0`
  * Optional method: `sudo update-alternatives --set python /usr/bin/python<version>`

* Switch default Pip3 version (Linux)
  * Show alternatives: `sudo update-alternatives --config pip`
  * Clean alternatives list: `sudo update-alternatives --remove-all pip`
  * Update the `update-alternatives`: `sudo update-alternatives --install /usr/bin/pip3 pip /usr/bin/pip<version> 0`
  * Optional method: `sudo update-alternatives --set pip /usr/bin/python<version>`
