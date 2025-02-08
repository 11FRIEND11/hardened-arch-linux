#  Partitioning and Mounting Disks for Arch Installation

## In this guide, we will create and mount the necessary partitions to install Arch Linux. When you start the machine, you will be thrown right into the terminal without any GUI. Here we need to first partition the storage.

---

##  Step 1: Creating Partitions

We need to create two partitions:

**EFI System Partition (ESP)** – **512MB** (Required for UEFI boot)  
**Root Partition (`/`)** – **Rest of the space** (Where the OS will be installed)

### Open the Partition Tool
Run the following command:
```console
cfdisk /dev/sda
```

What it does:

Opens the cfdisk partitioning tool for /dev/sda.
This tool allows us to create and modify partitions easily.

Steps Inside cfdisk:
Select "gpt" as the partition table type (GPT is required for UEFI).

Create a 512MB partition and set it as EFI System.

Use the remaining space for the root partition (/).

Select Write → Type yes → Press Enter.

Select Quit.

## Step 2: Formatting Partitions

Once partitions are created, we need to format them.

Format the EFI Partition (sda1)

Run:
```console
mkfs.fat -F32 /dev/sda1
```
What it does:

Formats /dev/sda1 as FAT32, which is required for UEFI boot.

Format the Root Partition (sda2)

Run:
```console
mkfs.ext4 /dev/sda2
```
What it does:

Formats /dev/sda2 as ext4, a common Linux filesystem.

## Step 3: Mounting the Partitions

Now, we mount these partitions so we can install Arch Linux.

### Mount the Root Partition (sda2)

Run:
```console
mount /dev/sda2 /mnt
```
What it does

Mounts the root partition (sda2) to /mnt.

This will act as the main filesystem for the new OS.

Mount the EFI Partition (sda1)

Run:
```console
mkdir -p /mnt/boot
```
mount /dev/sda1 /mnt/boot

What it does:

mkdir -p /mnt/boot → Creates a boot directory inside /mnt.

mount /dev/sda1 /mnt/boot → Mounts the EFI partition to /boot.

## Step 4: Verify Everything

Run:
```console
lsblk
```
Expected Output:
```console
sda      
├─sda1    512M  part  /mnt/boot 
└─sda2    49.5G part  /mnt 
```
What it does:

lsblk shows all disks and partitions along with their mount points.

If you see /mnt for sda2 and /mnt/boot for sda1, everything is correct.

# Next Step: Installing the Base System!

