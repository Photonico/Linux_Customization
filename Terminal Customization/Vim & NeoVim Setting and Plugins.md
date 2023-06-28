# Vim & NeoVim Setting and Plugins

## Settings

* Check info: `:version`

* Check the problem:
  * Vim: `:checkhealth`
  * NeoVim: `:help nvim-configuration`

* Configuration file
  * Vim: `~/.vimrc`
  * NeoVim: `~/.config/nvim/init.vim`

* Editor
  * Set Tab 4 spaces: `set tabstop=4`
  * Set line number: `set number`

## Plugin Manager: Vim-plug(Recommended)

* Install
  * Vim
    * via Curl: `curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim`
    * ArchLinux: `yay -S vim-plug`
  * NeoVim:
    * via Curl: `curl -fLo ~/.config/nvim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim`
    * ArchLinux: `yay -S neovim-plug`

* Plugins Installation Path
  * Vim: `~/.vim/plugged`
  * NeoVim: `~/.config/nvim/plugged`

* Plugins Configuration file
  * Plug Begin: `call plug#begin('<Plug Installation Path>')`
  * Plug Import: `Plug 'itchyny/lightline.vim'`
  * Plug End: `call plug#end()`

* Plugins Commands
  * Install Plugins: `:PlugInstall`
  * Check Plugins Status: `:PlugStatus`
  * Update Plugins: `:PlugUpdate`
  * Remove Plugins: `:PlugClean`
  * Vim-plug Upgrade: `:PlugUpgrade`
  
## Plugins (with Vim-plug)

* Vim Plugins Demonstration: [VIM AWESOME](https://vimawesome.com/)

* Vim dict
  * Install: `Plug 'szw/vim-dict'`
  * Usage: `:Dict`

* Lightline
  * Install: `Plug 'itchyny/lightline.vim'`
  * Configure: [GitHub](https://github.com/itchyny/lightline.vim)

* Wakatime plugin:
  * Install:
    * Open configuration file and add: `Plug 'https://github.com/wakatime/vim-wakatime.git'`
    * Install Plugin: `:PlugInstall`  
  * Configure Wakatime: `https://github.com/wakatime/vim-wakatime`
    * Change the api key saved in your `~/.wakatime.cfg`: `:WakaTimeApiKey`
    * Enable debug mode (may slow down Vim so disable when finished debugging): `:WakaTimeDebugEnable`
    * Disable debug mode: `:WakaTimeDebugDisable`
    * Disable screen redraw: `:WakaTimeScreenRedrawDisable`
    * Echo your total coding activity for Today: `:WakaTimeToday`

* NERDTree
  * Install: `Plug 'preservim/nerdtree'`
  * Active: `:NERDTree`

* Complete
  * Install: `Plug 'valloric/youcompleteme'`
  * Compile YCM core: `python3 /home/lu/.vim/plugged/youcompleteme/install.py`
  * Enable YCM server: `:YcmRestarServer`

* COC
  * Install nodejs >= 12.12: `curl -sL install-node.now.sh/lts | bash`
  * Install: `Plug 'neoclide/coc.nvim', {'branch': 'release'}`
