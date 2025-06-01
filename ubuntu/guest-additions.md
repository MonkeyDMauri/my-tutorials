# 🐧 How to Install VirtualBox Guest Additions on Ubuntu (Host: Windows)

This guide explains how to mount and install Guest Additions on an Ubuntu VM when your host system is Windows. Guest Additions enable features like shared clipboard, drag & drop, shared folders, and automatic screen resizing.

---

## ✅ Prerequisites

- You have a Ubuntu virtual machine running in **VirtualBox** on **Windows**
- VirtualBox is installed and updated
- Ubuntu VM is running

---

## 🧱 1. Update Ubuntu & Install Required Packages.

Open a terminal in the Ubuntu VM and run:

```bash`
sudo apt update && sudo apt upgrade -y
sudo apt install build-essential dkms linux-headers-$(uname -r)

## 💿 2. Insert the Guest Additions CD Image.


With your Ubuntu machine running, click on the **Devices** option at the upper left corner in the **Virtual Box** window(On your host machine):

Devices > Insert Guest Additions CD Image…

If prompted to download the ISO, accept it.

## 📂 3. Mount the CD (if not auto-mounted).

First check if it was auto-mounted by opening your terminal and doing:

```bash`
ls /media/$USER

You should see a folder like this:

```bash`
VBox_GAs_7.1.4

If it doesn't exist, mount it manually:

```bash`
sudo mount /dev/cdrom /mnt

If this doesn't work you might wanna try mounting the ISO from sr* or sr0:

```bash`
sudo mount /dev/sr* /mnt
cd /mnt
ls

## ⚙️ 4. Run the Installer.

Our current working directory should be where we can see VBoxLinuxAdditions.run which should be in /mnt,
once this is done we run the installer.

```bash`
sudo ./VBoxLinuxAdditions.run


## 🔁 5. Reboot the VM

```bash`
sudo reboot


