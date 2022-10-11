# macOS System Settings and Packages

## Settings

* Change hostname  
  System Preferences -> Sharing  

## Shortcuts Setting

* Customize:  Setting / Keyboard

* Input switch: `Ctrl` + `Space`

## Remote

* Get root authorization: `sudo su -`  

* Login: `ssh -p <port> <username>@<ip>`  
    Example: `ssh -p 22 username@111.22.33.44`  

## Hardware Detection Tool

* CPU info check: `cpufetch`

## Packages / Softwares

* Brew: `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`  

* Neofetch: `brew install neofetch`  

* XCODE Select: `xcode-select --install`  

* Pyenv: `brew install pyenv`  
  * Edit `~./zshrc`  

    ```zsh
    export PYENV_ROOR="$HOME/.pyenv"
    export PATH=$PYENV_ROOT/shims:$PATH
    eval "$(pyenv init -)"
    eval "$(pyenv virtualenv-init -)"
    ```

* BalenaEtcher  
  * Install: `brew install BalenaEtcher`  
  
* gfxCardStatus  
  * Install: `brew install gfxCardStatus`  

* iTerm
  * Install: [iTerm](https://iterm2.com/)
  * Preferences → Profiles → Text  
    ✔ Use a different font for Non-ASCII Font: MesloLGS NF

* ZSH
  * Install: `brew install zsh`  
  * Make it your default shell: `chsh -s $(which zsh)`  

* Screenshot
  * Snipaste

* ColorPick
  * Digi Color Meter

* Mouse acceleration  
  * Read setting: `defaults read -g com.apple.mouse.scaling`  
  * Write Setting: `defaults write -g com.apple.mouse.scaling -integer 0`  

* NeoVim  
    Alias: `alias nv=nvim`  

* Link VSCode to terminal:
  * Open `~/.zshrc`  
  * Add `code () { VSCODE_CWD="$PWD" open -n -b "com.microsoft.VSCode" --args $* ;}`  

* Tensorflow for macOS:

  ```zsh
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/apple/tensorflow_macos/master/scripts/download_and_install.sh)"
  ```

## Python environment

* Switch default Python3 version (macOS)
  * Unlink: `brew unlink python<version>`
  * Link: `brew link python<version>`

* Path Settings (macOS)  
  * If you need to have python<@version> first in your PATH, run: `echo 'export PATH="/usr/local/opt/python<@version>/bin:$PATH"' >> ~/.zshrc`  
  * For compilers to find python<@version> you may need to set: `export LDFLAGS="-L/usr/local/opt/python<@version>/lib"`
