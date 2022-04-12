# KALI-LINUX

## Install Steps

1. Download Kali-Linux from Microsoft Store

2. Launch Kali-linux this will run the install and prompt for username & password

3. Update system
    > sudo apt update && sudo apt upgrade

4. Install Win-KeX (GUI)
    > sudo apt install kali-win-kex

5. Install tools / metapackages
    > sudo apt install kali-linux-everything

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
    hostname = UBUNTU
    generateHosts = false
    ```

Replace all instances of `DESKTOP-QHEH3D4` with `UBUNTU` or whatever other hostname you want in the /etc/hosts file

> sudo nano /etc/hosts

    ```
    127.0.1.1       DESKTOP-QHEH3D4.localdomain     DESKTOP-QHEH3D4
    ```

    ```
    127.0.1.1       UBUNTU.localdomain     UBUNTU
    ```
