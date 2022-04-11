# Install Notes

You have to install Kali-linux from the microsoft store otherwise the gpg key was missing and could not restore through apt-key

`ERROR: Invalid signature for Kali Linux repositories : "The following signatures were invalid: EXPKEYSIG ED444FF07D8D0BF6 Kali Linux Repository"`


┃ This is a minimal installation of Kali Linux, you likely
┃ want to install supplementary tools. Learn how:
┃ ⇒ https://www.kali.org/docs/troubleshooting/common-minimum-setup/

https://www.kali.org/docs/general-use/metapackages/

I chose this meta package:

> sudo apt install kali-linux-core

Run: “touch ~/.hushlogin” to hide this message (on launch)
> touch ~/.hushlogin
# Specifications & Other Notes
Need to add a set user id (stick bit) to the ping function

> sudo chmod +s /bin/ping

## Change the hostname

1. Change the hostname from `marnold@DESKTOP-QHEH3D4` to `UBUNTU` or whatever other hostname you want
> hostname
> sudo nano /etc/wsl.conf

    ```
    [network]
    hostname = UBUNTU
    generateHosts = false
    ```



2. Replace all instances of `DESKTOP-QHEH3D4` with `UBUNTU` or whatever other hostname you want in the /etc/hosts file
> sudo nano /etc/hosts

    ```
    127.0.1.1       DESKTOP-QHEH3D4.localdomain     DESKTOP-QHEH3D4
    ```

    ```
    127.0.1.1       UBUNTU.localdomain     UBUNTU
    ```
