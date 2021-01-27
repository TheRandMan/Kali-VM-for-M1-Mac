# Kali VM on M1 Mac
How to set up a Kali Linux VM on a M1 Mac with Parallels Technical Preview. Most of this is not my own findings. I'm just piecing it together in an easy to follow guide for my own notes and to share with others.

For now, this won't be too detailed, will have poor formatting, and likely isn't 100% perfect but it should be enough to get you set up.

## Steps

1. Install Parallels Technical Preview - https://b2b.parallels.com/Apple-Silicon
1. Download the base Debian arm64 installation image - https://cdimage.debian.org/debian-cd/current/arm64/iso-cd/debian-10.7.0-arm64-xfce-CD-1.iso
1. Boot the Debian image in Parallels and install
    1. Do NOT install a window manager or GUI (this will come later)
    1. I use hostname kali and username kali to make it similar to a real Kali image
1. After Debian installs, reset the VM and boot to your Debian installation
1. Login with your user account
1. Switch to root - `su`
1. Install sudo - `apt install sudo`
1. Add your user to the sudoers file - https://linuxize.com/post/how-to-add-user-to-sudoers-in-debian/
1. Exit root - `exit`
1. Logout of your user - `exit`
1. Log back in
1. Install wget - `sudo apt install wget`
1. Download the install_kali.sh script - `wget https://github.com/TheRandMan/Kali-VM-for-M1-Mac/raw/main/install_kali.sh`
1. Make the script executable - `chmod +x install_kali.sh`
1. Run the install_kali.sh script with sudo - `sudo ./install_kali.sh`
    1. When prompted, the default options are suggested to be used
1. Once the script finishes reboot the VM and you should have a full Kali install
    1. Burpsuite doesn't seem to be installed so you probably want to install that `sudo apt install burpsuite`



### Credits
Primarily posts 11 and 15 from this forum thread - https://forum.parallels.com/threads/kali-linux-arm-images.351911/
