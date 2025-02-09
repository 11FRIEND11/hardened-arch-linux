# Setting Up the Virtual Machine

Now that we have downloaded the Arch Linux ISO and installed VirtualBox, it's time to set up our virtual machine (VM). This section will guide you through creating the VM and allocating the right resources for a smooth experience.

---

## **1️ Creating the Virtual Machine**
1. Open **VirtualBox** and click **New**.
2. Set the **Name** whatever you like! I named it **Hardened Arch**
3. Choose **Type:** `Linux`  
4. Choose **Version:** `Arch Linux (x86_64)`

---

## **2️ Allocating System Resources**
**Memory (RAM):**  
- I have **16GB RAM**, so I allocated **8GB (8192MB)** to the VM.  
- If you have less RAM, consider allocating **4GB (4096MB) minimum**.

**Processor Allocation:**  
- My CPU: **Intel i5 10th Gen H (4 Cores, 8 Threads)**  
- Allocated: **3 processors** (you can allocate more if your system allows).

**Storage:**  
- Selected **50GB of dynamically allocated storage** (I have a **512GB SSD**).  
- 50GB is more than enough for a hacking setup, but you can go higher.

---

## **3️ Mounting the ISO**
1. After setting up the VM, click **Settings** > **Storage**.
2. Under "Controller: IDE," click **Empty**.
3. On the right panel, click **Choose a disk file**.
4. Select the **Arch Linux ISO** that you downloaded earlier.
5. Press **OK** to save changes.

## EFI
we will be using EFI so navigate to settings > system> motherboard and enable EFI
---

## **4️ Launching the Virtual Machine**
1. Click **Start** to boot into the **Arch Linux ISO**.
2. If everything is set up correctly, you should see the **Arch Linux installation menu**.

Congratulations! You are now ready to install Arch Linux. In the next section, we will begin the actual installation process. 

---
