# KALI-LINUX

## Install Steps

1. Download Kali-Linux from Microsoft Store

2. Launch Kali-linux this will run the install and prompt for username & password

3. Update system
    > sudo apt update && sudo apt upgrade

4. Install Win-KeX (GUI)
    > sudo apt install kali-win-kex
    To start Win-Kex run the following command:
    > kex --win -s

5. Install tools / metapackages
    > sudo apt install kali-linux-core
    > sudo apt install kali-linux-default

6. Hide Launch Message
    > touch ~/.hushlogin

## Specifications & Other Notes

Need to add a set user id (stick bit) to the ping function

> sudo chmod +s /bin/ping

## Change the hostname

Change the hostname from `marnold@DESKTOP-QHEH3D4` to `UBUNTU` or whatever other hostname you want

> hostname
> sudo nano /etc/wsl.conf

    ```
    [network]
    hostname = KALI
    generateHosts = false
    ```

Replace all instances of `DESKTOP-QHEH3D4` with `UBUNTU` or whatever other hostname you want in the /etc/hosts file

> sudo nano /etc/hosts

    ```
    127.0.1.1       DESKTOP-QHEH3D4.localdomain     DESKTOP-QHEH3D4
    ```

    ```
    127.0.1.1       KALI.localdomain     KALI
    ```

## ZSH - Installation

1. Download ZSH
    > sudo apt install zsh

2. Set ZSH as defualt login shell
    > sudo usermod -s /usr/bin/zsh $(whoami)

3. Installing Oh-My-ZSH
    > sh -c "$(curl -fsSL <https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh>)"

4. Install Powerline Fonts
    > sudo apt install fonts-powerline

5. Install Powerlevel10K Theme
    > git clone --depth=1 <https://github.com/romkatv/powerlevel10k.git> ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k

6. Edit .zshrc file to apply theme
    > code ~/.zshrc
    Paste in `ZSH_THEME="powerlevel10k/powerlevel10k"`

7. Apply Changes
    > source ~/.zshrc

## TOOLS

1. gef for GDB (GNU Debugger)
    > bash -c "$(curl -fsSL <http://gef.blah.cat/sh>)"
