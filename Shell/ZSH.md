# Shell

## General

* Add path: `export PATH=/home/lu/Packages/LLVM/bin:$PATH`

## ZSH

* Install ZSH
  * ArchLinux: `sudo pacman -S zsh`
  * openSUSE: `sudo zypper install zsh`
  * Solus: `sudo eopkg install zsh`

* ZSH setting: `~/.zshrc`

* Make it your default shell: `sudo chsh -s $(which zsh)` or: `sudo chsh -s /bin/zsh`

* Install OhMyZSH
  * via Wget: `sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"`
  * via Curl: `sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
  * ArchLinux: `yay -S oh-my-zsh-git`
    * Source configuration file: `/usr/share/oh-my-zsh/zshrc`
  * Pre-installed plugins: `/usr/share/oh-my-zsh/plugins`

* Install Powerlevel10k
  * Install
    * via Git `git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k`
    * ArchLinux: `sudo pacman -S zsh-theme-powerlevel10k`
  * Edit `code ~/.zshrc`
    * General: `ZSH_THEME="powerlevel10k/powerlevel10k"`
    * ArchLinux: `ZSH_THEME="zsh-theme-powerlevel10k/powerlevel10k"`
  * Generate a template: `p10k configure`
  * Configuration file: `~/.p10k.zsh`

* Highlighting
  * Install
    * via Git: `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins`
    * ArchLinux: `sudo pacman -S zsh-syntax-highlighting`
  * Edit configuration: `~/.zshrc`
    * General: `plugins += (zsh-syntax-highlighting)`
    * ArchLinux: `source /usr/share/zsh/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh`

* Autosuggestion
  * Install
    * via Git: `git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins`
    * ArchLinux: `sudo pacman -S zsh-autosuggestions`
  * Edit configuration: `~/.zshrc`
    * General: `plugins += (zsh-autosuggestions)`
    * ArchLinux: `source /usr/share/zsh/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh`

* Wakatime
  * Install Client
    * via Pip: `pip install wakatime`
    * ArchLinux: `sudo pacman -S wakatime`
  * Install Pugin
    * via Git: `cd ~/.oh-my-zsh/custom/plugins && git clone https://github.com/sobolevn/wakatime-zsh-plugin.git wakatime`
    * ArchLinux: `cd /usr/share/zsh/plugins && sudo git clone https://github.com/sobolevn/wakatime-zsh-plugin.git wakatime`
  * Edit configuration: `~/.zshrc`
    * General: `plugins = (...wakatime...)`
    * ArchLinux: `source /usr/share/zsh/plugins/wakatime/wakatime.plugin.zsh`
  * Configuration file: `~/.wakatime.cfg`
  * Add to PATH: `export PATH=~/.local/lib/python3.10/site-packages:$PATH`

## .zshrc

```Zsh

if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
  source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
fi

ZSH=/usr/share/oh-my-zsh/

ZSH_CUSTOM=/usr/share

ZSH_THEME="zsh-theme-powerlevel10k/powerlevel10k"

plugins=(git)
plugins+=(archlinux extract history history-substring-search pip screen vi-mode z)
source $ZSH/oh-my-zsh.sh


ZSH_CACHE_DIR=$HOME/.cache/oh-my-zsh
if [[ ! -d $ZSH_CACHE_DIR ]]; then
  mkdir $ZSH_CACHE_DIR
fi

source $ZSH/oh-my-zsh.sh

source /usr/share/zsh/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh
source /usr/share/zsh/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
source /usr/share/zsh/plugins/wakatime/wakatime.plugin.zsh

```
