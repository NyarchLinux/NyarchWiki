# Installing Applications

On Nyarch Linux you can install an application in multiple ways, that are called "Packaging Formats".
This page explains the differences between the packages format and how to install and manage them.

Supported packages:

1. [Arch Linux Packages](#arch-linux-packages) (pacman, .tar.zst)
2. [Flatpaks](#flatpaks) (Store, .flatpakref, .flatpak)
3. AppImages (.appimage)
4. Arch User Repository (nyay)

## Arch Linux Packages 
(Almost) Every Linux distribution has a package manager: it helps you to install, remove and update packages
on your computer. 

On Arch Linux, the package manager is `pacman`. 

Because of multiple reasons, pacman is supposed to be only used via terminal and with admin privileges.

Here is some basic usage for `pacman`, if you want more detailed instructions, check [pacman on the Arch Wiki](https://wiki.archlinux.org/title/Pacman)

### How to install a package
```bash
sudo pacman -S package
```

For example, to install `firefox`, you can type
```bash
sudo pacman -S firefox
```

### How to remove a package
```bash
sudo pacman -R package
```
In case you also want to remove its dependencies, you can use `-Rns`.

### How to update every package
```bash
sudo pacman -Syu
```
### How to search for a package
```bash
sudo pacman -Ss package
```

## Flatpaks
Flatpak is a special packaging format that allows you to install applications in a **sandboxed** envirnomnet.

This means you can easily manage what permissions an application has, like you do on smartphones.

Flatpaks have some pros and cons:
- Pros:
    - They work on *every* Linux distribution
    - You can control their permissions
    - Easy to install through the store
    - You can install applications without admin rights
- Cons:
    - They take more disk space compared to native pacakges
    - They are sometimes problematic with some software that is not made to run inside a sandbox
    - Use for terminal programs often require doing some extra steps
### When should I install a flatpak?
- When the software is supposed to be primarly run as Flatpak (for example Bottles)
- When you are installing a software that you don't trust (you can control its permissions)
- Whent it's a GTK/Gnome application (because Nyarch ships their runtimes and they install fast)
- When the software does not run in the terminal
### Installing a Flatpak
#### Gnome Software
You can use **Gnome Software** to find, install, uninstall and update flatpak applications.

![immagine](https://github.com/user-attachments/assets/34132dbc-f032-475b-90f9-1eec75f1eabd)
![immagine](https://github.com/user-attachments/assets/e2da8b38-7de6-44d3-a045-7a1b5fd4291a)
#### From Flathub
You can find flatpaks on [Flathub](https://flathub.org/). Installing an application from there makes your 
browser download a `.flatpakref` file, clicking it opens the application on Gnome Software

**Note**: every application on flathub is also in Gnome Software
#### Command Line
```bash
flatpak install application.id
```
For example, to install firefox via Flatpak
```bash
flatpak install org.mozilla.firefox
```
With command line, you can also install `.flatpak` files.

To do that, you can just run
```bash
flatpak install file.flatpak
```

Also, duble clicking on `.flatpak` file opens Gnome Software to install it.

### Managing Flatpak permissions
You can manage flatpak permissions using Flatseal.


## Appimages
**Appimages** are a special format that can be run on every linux distribution.
- Pros:
    - They work on *every* Linux distribution
- Cons:
    - They do not share libraries with other applications
    - They are generally slower
    - Often they don't support theming

It is generally not suggested to use appimages if there are other packaging formats available. 
Use appimages **only if there is no alternative**.
### Installing and managing Appimages
After downloading an appimage, you can double click on it and it will launch **GearLever**.

GearLever is a simple software that helps you install and uninstall appimages. 
You can choose if run the appimage once without installing or add it to the app menu.

#### Running appimages from command line
You can also straight up run an appimage from the command line by:
1. Giving it the permission to be executed
```bash
chmod +x application.appimage
```
2. Running it
```bash
./application.appimage
```



