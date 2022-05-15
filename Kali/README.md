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

Change the hostname from `marnold@DESKTOP-QHEH3D4` to `KALI` or whatever other hostname you want

> hostname
> sudo nano /etc/wsl.conf

    ```
    [network]
    hostname = KALI
    generateHosts = false
    ```

Replace all instances of `DESKTOP-QHEH3D4` with `KALI` or whatever other hostname you want in the /etc/hosts file

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

2. pwninit install
    Download: musl binaries & pwninit zip and unzip them (in /opt/ directory)
    > cd musl-1.2.3
    > ./configure
    > sudo make install
    > cd ../pwninit-3.2.0
    > cargo install pwninit
    > export PATH="$HOME/.cargo/bin/pwninit:$PATH"
    > cd ~
    > nano .zshrc
    Add the line `alias pwninit="~/.cargo/bin/pwninit"`

3. Weiner's Attack (RSA)
    > git clone <https://github.com/pablocelayes/rsa-wiener-attack.git>

4. RsaCTFTool (python library)
    > cd tools
    > git clone <https://github.com/Ganapati/RsaCtfTool.git>
    > apt install libgmp3-dev libmpc-dev
    > cd RsaCtfTool
    > pip3 install -r "requirements.txt"

5. Exiftool
    > sudo apt install exiftool

6. Steghide
    > sudo apt install steghide

7. stegcracker (py)
    > pip3 install stegcracker
    > export PATH="$PATH:/home/marnold/.local/bin"

8. StegSeek
    > cd /tools
    > wget "https://github.com/RickdeJager/stegseek/releases/download/v0.6/stegseek_0.6-1.deb"
    > sudo apt install ./stegseek_0.6-1.deb

9. gdb-peda
    > git clone <https://github.com/longld/peda.git> ~/peda
    > echo "source ./peda/peda.py" >> ~/.gdbinit
    > nano .gdbinit
        - remove ~/.gef.py
