# Steps for a new Raspberry Pi setup

## On Pi
1. flash sd card - etcher
2. `ssh` file in boot partition
3. `wpa_supplicant.conf` (see model file in repo)
4. rename pi in files `/etc/hosts` and `/etc/hostname`
5. add public key to `.ssh/authorized_keys`
6. turn vnc on via `raspi-config`
7. install `rsub`:
	```
	sudo wget -O /usr/local/bin/rsub https://raw.github.com/aurora/rmate/master/rmate
	sudo chmod +x /usr/local/bin/rsub
	```
8. update software `sudo apt update && sudo apt upgrade`

## Locally
1. bind IP address on router
2. add new rpi to `.ssh/config`:
	```
	Host NEWPI
        Port 22
        HostName 192.168.0.THEIP
        User pi
        RemoteForward 52698 127.0.0.1:52698
    ```

## Setting up a new service via systemd
