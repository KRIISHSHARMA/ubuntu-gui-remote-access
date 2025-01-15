# Installation Steps
1. Install a GUI Environment
To install a GUI on your Ubuntu server, we will use the tasksel tool to choose a desktop environment.

## Update your package list:

```
sudo apt update
```
## Install tasksel if not already installed:
```
sudo apt install tasksel
```
## Run tasksel to choose the desktop environment:

```
sudo tasksel
```
## Choose one of the following options depending on your preference:

```
Gnome: Full GNOME desktop environment.
Xfce: Lightweight desktop environment.
MATE: A traditional desktop environment.
LXQt: Another lightweight option.
Lubuntu Desktop: Another version of LXQt.
```

Install the selected environment and wait for the process to complete. (may take some time)

# Use X11 Forwarding (For GUI Applications)

## Enable X11 Forwarding on SSH Connection: Use the -X or -Y flag when connecting via SSH:

```
ssh -X username@remote_server
```
or
```
ssh -Y username@remote_server
```
- -Y is less restrictive but generally safe if you trust the remote server.

## Run GUI Applications: Once connected, run any GUI application. For example:

```
gnuradio-companion #if already installed
or
gedit
```
