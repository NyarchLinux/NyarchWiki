If you have already installed a Linux Distribution, the installation procedure for Nyarch Linux is the same.

If you have not already installed a Linux Distribution, please consider installing another distribution.
If you still want to go on, then you can decide to install Nyarch on:

1. [Your Computer](#installing-nyarch-on-your-computer)
2. [Virtual Machine](#install-nyarch-on-a-virtual-machine)
3. [On an existing Linux Distro](/nyarcher)

## Installing Nyarch on your Computer

### Prerequisites
- A computer that respects the [Resource Requirements](https://nyarchlinux.moe/#requirements)
- A USB Stick of at least 4GB capacity
- Already a working computer (or android device if you use [Etchdroid](https://etchdroid.app/))
- Downloaded the correct Nyarch ISO file. The ISO file can be found at [https://nyarchlinux.moe/](https://nyarchlinux.moe/#download). If you have a **Nvidia GPU**, check the support [here](https://wiki.nyarchlinux.moe/nvidia)
- A backup of every important file you have on your computer
### Creating a Bootable Drive
1. Download [Balena Etcher](https://etcher.balena.io/) or any similar program if you are more familiar with them
2. Insert the USB Drive in your computer
3. Open Balena Etcher

![immagine](https://github.com/user-attachments/assets/0fe6d643-86ac-4f37-980d-ca82e74e5484)

And click on "Flash from file". 
4. Select Nyarch Linux ISO file you have downloaded before.
5. Click on select Target
![immagine](https://github.com/user-attachments/assets/c17a0629-e35f-4523-a21a-638bdbc0c4c3)

And choose your USB Drive **attention: be sure to choose the right drive since you will lose any file you have on it**.
6. Click "Flash" and wait for it to finish. 
![immagine](https://github.com/user-attachments/assets/8a0f4a68-c36a-4f8f-968d-0b2c59d442dd)

### Using Ventoy ###

Follow the official Ventoy instructions to create a Ventoy bootable drive, place the Nyarch ISO image on your mobile cat drive, then select the ISO image in the booted Ventoy menu.

### Choosing the installation method
You can decide to install Nyarch in these ways:
1. Deleting the whole disk and install Nyarch
2. Install Nyarch alongside Windows in the same disk
3. Install Nyarch alongside Windows in another disk
If you want to do 1 or 3, then skip to the next section.
If you want to do 2, then you have to **shrink your Windows partition**.
##### Shrinking Windows partition
1. Boot windows
2. Cry
3. Launch the `Disk Management` utility found under Create and format hard disk partitions.
4. Right-click the primary Windows partition and select Shrink Volume...
![immagine](https://github.com/user-attachments/assets/01cb1a7c-7881-4d41-848d-fbf52240124f)
5. Shrink the size of the partition by at least 30GB. This will be the space left to Linux
![immagine](https://github.com/user-attachments/assets/ee2077d3-9ff8-4375-bf31-2c7234855bf2)

### Booting the Live USB
1. Connect the USB drive to your device
2. Access to the BIOS/UEFI Utility of your device. The procedure to access depends on your device.
  If you can't figure out how to access your BIOS, Spam F keys shouting *Hora Hora Hora* at the boot of your device till you get the right one.
3. Disable Secure Boot
4. Find the setting for the boot order and put your USB Drive in the first place. Alternatively, if you have access to the boot menu, launch it from there.
5. Save and exit
6. Hope that Nyarch Live boots. If it doesn't, check that you have actually set your USB at first place and then cry for help in Nyarch support channels (or any Linux community support).

### Nyarch Live Environment
You have *hopefully* succesfully booted Nyarch. 
Now you are in the **Live Environment**. 

When you're installing a Linux distribution, a live environment is like a "try before you buy" experience.
It's a **temporary operating system** that you can run from a USB drive or CD, without actually installing it on your computer's hard drive. 

This way, **you can test how the Linux distribution works**, specially **Wifi, hardware device, sound etc...**. You can also explore some of Nyarch features, however consider that **the performances are worst compared to the installed system** due to USB drive I/O Speeds.

In case you need to do an operation that requires the user password to be put while you are in the live environment, the password is `live`.
#### Nyarch Installer
The installer will be launched automatically at the start of the system.

![immagine](https://github.com/user-attachments/assets/d294db49-5fd7-4844-9083-59790998dcc7)

It will then prompt you your localization settings. Compile them according to your preferences.

##### Partitioning
**Note**: Be careful in this part since an error might cause data loss!
![immagine](https://github.com/user-attachments/assets/dea978b0-b0fd-4d23-b05d-e6a4e59c6f94)

Here you can choose multiple things:
- If to erase the entire disk and install Nyarch on it. You can choose a different disk in the upper part of the window.

- If to replace a partition with Nyarch Install (not shown in the image)

- If to install Nyarch alongside another OS (not shown in the image)

- To manually choose your partitions (If you know what you are doing)

You can also choose:

- **Swap**: it's like extra ram that is stored on your disk. It is strongly suggested to enable it.

- **Filesystem**: You can choose you filesystem between these

  - **ext4**: is the standard for Linux distribution. It's faster in many cases and is considered to be more stable.

  - **btrfs**: supports **instant snapshots**, has more protection against data corruption and redundancy. a bit slower in some cases（Intel dont chose，the issue is repoetd in [Issues＃62](https://github.com/NyarchLinux/NyarchLinux/issues/62)）.

  - xfs: don't install it unless you know what you are doing

##### Finishing the install
Choose your name, and wait for the install to finish, and reboot!

![immagine](https://github.com/user-attachments/assets/9a9b4116-dc34-4b18-9b9f-b85b40f27ed6)

![immagine](https://github.com/user-attachments/assets/6115a3d3-e75c-4028-b71f-3b0a35109f4b)

## Install Nyarch on a Virtual Machine
- Suggested VM Softwares to install Nyarch: VMWare Workstation, QEMU, Gnome Boxes

- Not suggested VM Softwares to install Nyarch: VirtualBox (because of the bad 3D acceleration)

Nyarch makes a lot of use of animations to enhance the user experience, so **enable 3D acceleration in the VM**. Otherwise it will lag as fuck. Bro you don't want to see worst animation than Blue Lock S2, trust me.
Create a VM with these specifications:

- CPU: As much as you can/prefer

- Memory: at least 3GB, suggested 6GB for a fluid system

- Storage: 30GB minimum for installing the OS

- UEFI/BIOS are both supported

After you created and booted the VM, skip to [Nyarch Live Environment](#nyarch-live-environment)
