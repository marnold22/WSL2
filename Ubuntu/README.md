# Specifications & Other Notes

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
