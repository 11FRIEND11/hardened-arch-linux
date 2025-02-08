# Installing the Base System

## Now that we have partitioned and mounted our disk, the next step is to install the core system components of Arch Linux.

Why Do We Need to Install These Packages?

When we boot into the Arch Linux ISO, we are running a live environment, meaning nothing is installed yet. To actually have a working system, we need to install a few essential components:

base – The minimal set of packages required for Arch Linux to function.

linux – The Linux kernel, which is the core of the operating system.

linux-firmware – Firmware required for hardware components like Wi-Fi, Bluetooth, and graphics.

Since these packages are not included in the mounted partitions, we download and install them using pacstrap.

### Prerequisites

You must have an active internet connection because the packages will be downloaded from Arch Linux repositories.
This process may take 5–10 minutes, depending on your internet speed.

The total size of the installation is around 500MB–1GB. Will take around 5-10 minutes to download. Might take less or more depending on your connection.

## Installing the Base System

### Run the following command to install the base system:
> pacstrap /mnt base linux linux-firmware

### What This Command Does
The pacstrap command installs packages onto a mounted system.

/mnt is the location where we mounted our root partition.

base installs the essential system components.

linux installs the latest Linux kernel.

linux-firmware installs firmware for hardware compatibility.

Once the installation is complete, Arch Linux is now technically installed, but it is not yet configured.

## Generating fstab

After installing the base system, we need to generate the fstab file, which keeps track of disk partitions and mount points.
### Run the following command:
> genfstab -U /mnt >> /mnt/etc/fstab

### What This Command Does

genfstab -U /mnt generates an fstab file with UUIDs (Universally Unique Identifiers) for partitions.

/mnt/etc/fstab saves the output to the fstab file.

### To verify that fstab was created correctly, run:

> cat /mnt/etc/fstab

This will display the contents of the fstab file. If everything looks correct, we can move on to configuring the system.

# Next Step

Now that the base system is installed, we need to chroot into it and start setting up essential system configurations like time, locale, and users.
