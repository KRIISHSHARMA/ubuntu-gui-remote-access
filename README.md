# Installation Steps
1. Install a GUI Environment
To install a GUI on your Ubuntu server, we will use the tasksel tool to choose a desktop environment.

## Update your package list:

```
sudo apt update
```
## Install a Lightweight Display Manager 
- To manage the GUI login screen, install a lightweight display manager like SLiM (or alternatives like lightdm or sddm):
```
sudo apt install slim
```
- To check default DM 
```
cat /etc/X11/default-display-manager
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

# Accessing via VNC

## To access the GUI through VNC:

### On Server side 

- Install vncserver 
```
sudo apt update
sudo apt install tigervnc-standalone-server tigervnc-common
```
- Setup and start a vncserver
```
vncserver
```
- Create a Password 
- use the following to see your connection info 
```
vncserver -list
```

### On Client Side

- Install a VNC client (like TigerVNC Viewer) on your local machine. (If you are using a Linux-based distribution, Remmina may already be installed)

- Open the VNC client and enter the server IP followed by the port. If you're using the WireGuard IP, enter:

```
<WireGuard-IP>:<Listnening Port> #for listnening port use command vncserver -list on server
```
- Enter the password that was set during the VNC server setup.
