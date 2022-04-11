# Install Notes

You have to install Kali-linux from the microsoft store otherwise the gpg key was missing and could not restore through apt-key

`ERROR: Invalid signature for Kali Linux repositories : "The following signatures were invalid: EXPKEYSIG ED444FF07D8D0BF6 Kali Linux Repository"`


┃ This is a minimal installation of Kali Linux, you likely
┃ want to install supplementary tools. Learn how:
┃ ⇒ https://www.kali.org/docs/troubleshooting/common-minimum-setup/

https://www.kali.org/docs/general-use/metapackages/

I chose this meta package:

> sudo apt install kali-linux-core

# Specifications & Other Notes
Need to add a set user id (stick bit) to the ping function

> sudo chmod +s /bin/ping