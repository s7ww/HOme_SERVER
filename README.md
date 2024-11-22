# Fedora 41 Home Server

A personal home server built from a fresh Fedora 41 ISO installation. This repository documents the setup process, configurations, and additional services added to enhance functionality.

## Current Progress
- **Fedora 41 Installed**: Downloaded and installed the official Fedora ISO.
- **SSH Tested**: Successfully configured and tested SSH access on the local network.

## Future Goals
- Secure the SSH setup further (disable root login, change default port, etc.).
- Add network file sharing with Samba.
- Deploy a web server (NGINX or Apache).
- Implement containerized services (Podman/Docker).
- Configure a backup strategy.

## Quick Start
1. Install Fedora 41 from the official ISO.
2. Follow the `setup/` directory for post-installation scripts and service configurations.
3. Explore `docs/` for detailed steps and explanations.


# Fedora 41 Installation Steps

## Step 1: Download the Fedora ISO
1. Go to the official Fedora download page: [https://getfedora.org/](https://getfedora.org/).
2. Select the Fedora 41 Workstation or Server edition, depending on your use case.
3. Download the ISO file.

## Step 2: Create a Bootable USB
1. Use a tool like Rufus (Windows), Balena Etcher (Linux/Mac), or the Fedora Media Writer.
2. Write the Fedora ISO to a USB drive.

## Step 3: Boot from USB
1. Insert the bootable USB into your system and reboot.
2. Access the boot menu (usually by pressing F2, F12, or ESC during startup).
3. Select the USB drive and boot into the Fedora installer.

## Step 4: Install Fedora
1. Follow the on-screen prompts to:
   - Select your language and keyboard layout.
   - Partition the drive (automatic or custom).
   - Set up a root password and user account.

2. Complete the installation and reboot into your new Fedora system

## Step 5: Post-Installation Tasks
- Update the system:
  ```bash
  sudo dnf update -y

## Now lets Establish an SSH connection
# Check if SSH is installed
sudo dnf install -y openssh-server

# Enable SSH to start on boot
sudo systemctl enable sshd

# Start the SSH service
sudo systemctl start sshd

# Check the status of SSH
sudo systemctl status sshd

# Test ssh from another system
ssh -p 2222 your-username@your-server-ip



