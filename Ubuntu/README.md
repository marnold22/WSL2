# Specifications & Other Notes

1. Change the hostname from `marnold@DESKTOP-QHEH3D4` to `SP3` or whatever other hostname you want
> hostname
> sudo nano /etc/wsl.conf

    ```
    [network]
    hostname = SrcCodes
    generateHosts = false
    ```



2. Replace all instances of `DESKTOP-QHEH3D4` with `SP3` or whatever other hostname you want in the /etc/hosts file
> sudo nano /etc/hosts

    ```
    127.0.1.1       DESKTOP-QHEH3D4.localdomain     DESKTOP-QHEH3D4
    ```

    ```
    127.0.1.1       SP3.localdomain     SP3
    ```
