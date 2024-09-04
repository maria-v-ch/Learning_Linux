# HOW-TO LINUX

Quick guide on the basics of a powerful and versatile operating system used by millions around the world.

## Why Linux
1. [x] **Open Source:** free and open-source, meaning the source code is available for anyone to view, modify, and distribute.


2. [x] **Security:** has robust security features, making it less vulnerable to viruses and malware.


3. [x] **Customizability:** almost every aspect is customizable, from the kernel to the desktop environment.


4. [x] **Multi-User:** designed as a multi-user system, allowing multiple people to use the system  simultaneously 
   without affecting each other.


5. [x] **Portability:** can run on a wide variety of hardware, from powerful servers to small embedded systems.


6. [x] **Stability and Performance:** highly stable and performs well under heavy workloads, which is why it's often 
   used in server environments.

## Popular Linux Distributions (or "distros")

#### **Ubuntu ([ubuntu.com]())**
One of the most popular and user-friendly, based on Debian, is a great choice for beginners.
Easy installation, large community support, and regular updates.

#### **Fedora ([getfedora.org]())**
Focuses on integrating the latest technologies, great for developers and tech 
enthusiasts. Frequent updates, strong support for containerization, focus on innovation.

#### **Debian ([debian.org]())**
Stable and reliable, serves as the foundation for many other distros, including Ubuntu.
Stability, large software repository, and excellent package management.

#### **Linux Mint ([linuxmint.com]())**
Based on Ubuntu, known for its simplicity and ease of use, ideal for users switching from Windows.
User-friendly interface, pre-installed multimedia codecs, strong community support.

#### **Arch Linux ([archlinux.org]())**
A lightweight and flexible distribution that follows a rolling release model. Ideal for advanced users who prefer to 
build their system from scratch. Highly customizable, minimalistic, and up-to-date software.
 
#### **CentOS/RHEL ([centos.org / redhat.com]())**
A free, community-supported version of Red Hat Enterprise Linux (RHEL). Mainly for servers and enterprise  environments.
Long-term support, stability, and enterprise-grade features.

## Installation Guide
### Prerequisites
1. [x] A USB drive (minimum 4GB)
2. [x] A computer with at least 2GB RAM
3. [x] Stable internet connection (optional, but recommended for updates)
4. [x] Backup any important data from your computer before proceeding.
### 1. Download the Linux Distribution
   1. Go to the official website of your chosen Linux distribution. 
   2. Download the ISO file (a disk image that contains the Linux OS).
### 2. Create a Bootable USB Drive
**For Windows Users:**
1. Download and install Rufus.
2. Open Rufus, select your USB drive, choose the downloaded ISO file, and click "Start".

**For macOS/Linux Users:**
1.   Download and install Etcher.
2.   Open Etcher, select the ISO file and USB drive, and click "Flash".
### 3. Boot from the USB Drive

Insert the bootable USB drive into your computer. 
Restart your computer and enter the BIOS/UEFI setup (usually by pressing F2, F10, Del, or Esc during startup). 
Change the boot order to boot from the USB drive first. 
Save the changes and exit BIOS/UEFI.

### 4. Install Linux
1. **Choose to Install:** When the Linux boot menu appears, select "Install Linux". 
2. **Select Language and Keyboard Layout:** Follow the prompts to choose your preferred language and keyboard layout. 
3. **Set Up Wi-Fi (if required)**: Connect to your Wi-Fi network for updates during installation.
4. **Choose Installation Type**:
   - Erase Disk and Install Linux: This will delete all data on the disk and install Linux.
   - Install Alongside Existing OS: Dual-boot with another operating system.
   - Something Else: Custom partitioning for advanced users.
5. **Create a User Account**: Enter your name, username, password, and computer name.
6. **Install**: Review your settings and click "Install Now". Wait for the installation to complete.
7. **Reboot**: Once installation is complete, remove the USB drive and reboot the computer.

### 5. Post-Installation Setup
1. **Update System**: Open a terminal and run the following commands to update your system:
(bash) `sudo apt update && sudo apt upgrade -y`.
2. **Install Additional Software**: Use the package manager (`apt`, `dnf`, `pacman`, etc.) to install any additional 
   software you need.
3. **Customize Your Environment**: Adjust settings like themes, wallpapers, and application preferences to suit your 
   needs.