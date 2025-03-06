## Taking RDC to EC2-Ubuntu:

### Step#1: Installing Essential Softwares on EC2

**Code:**

```python
#Type the Following command in AWS EC2 shell

sudo apt update
sudo apt install ubuntu-gnome-desktop tightvncserver

vncserver
nano ~/.vnc/xstartup

#paste the below script in the xstartup file
#!/bin/bash

export XKL_XMODMAP_DISABLE=1
export XDG_CURRENT_DESKTOP="GNOME-Flashback:Unity"
export XDG_MENU_PREFIX="gnome-flashback-"
unset DBUS_SESSION_BUS_ADDRESS
xrdb "$HOME/.Xresources"
gnome-session &

#Give permission to file:
chmod +x ~/.vnc/xstartup
vncserver -kill :1
vncserver

#Installation of xrdp and setting password:
sudo apt update
sudo apt install xrdp
sudo systemctl start xrdp
sudo systemctl enable xrdp
sudo apt install gnome-tweaks
echo "gnome-session" > ~/.xsession
sudo ufw allow 3389/tcp

sudo systemctl status xrdp
sudo systemctl status xrdp-sesman

sudo passwd ubuntu
```
**Result of Code:**

![Code Execution](https://i.imgur.com/ybPcPFh.png)


### Step#2: Connecting Instance with Remote Desktop Connection

**Code:**

```python
#Go to windows Remote desktop Connection(RDC) &:

<PublicIP of EC2>:3389

```
**Result of Code:**

![Code Execution](https://i.imgur.com/MLY3Vhc.png)

![Code Execution](https://i.imgur.com/GaO2BMo.png)

### Step#3: Installing Pycharm from Terminal

**Code:**

```python
#Type following command in Terminal
snap find pycharm
snap install pycharm-community --classic
apt install python3-pip
pip3 install selenium

```
**Result of Code:**

![Code Execution](https://i.imgur.com/luGsKeN.png)



