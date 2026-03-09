# Installing Applications

On Nyarch Linux, you can install applications in multiple ways, which are called "Packaging Formats".
This page explains the differences between package formats and how to install and manage them.

Supported package formats:

1. [Arch Linux Packages](#arch-linux-packages) (pacman, .tar.zst)
2. [Flatpaks](#flatpaks) (Store, .flatpakref, .flatpak)
3. [AppImages](#appimages) (.appimage)
4. [Arch User Repository](#arch-user-repository) (yay & paru)

## Arch Linux Packages 
(Almost) Every Linux distribution has a package manager: it helps you install, remove, and update packages on your computer.

On Arch Linux, the package manager is `pacman`.

Due to various reasons, pacman is supposed to be used only via terminal and with admin privileges.

Here is some basic usage for `pacman`. If you want more detailed instructions, check [pacman on the Arch Wiki](https://wiki.archlinux.org/title/Pacman )

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
If you also want to remove its dependencies, you can use `-Rns`.

### How to update all packages
```bash
sudo pacman -Syu
```
### How to search for a package
```bash
sudo pacman -Ss package
```

## Flatpaks
Flatpak is a special packaging format that allows you to install applications in a **sandboxed** environment.

This means you can easily manage what permissions an application has, like you do on smartphones.

Flatpaks have some pros and cons:
- Pros:
    - They work on *every* Linux distribution
    - You can control their permissions
    - Easy to install through the store
    - You can install applications without admin rights
- Cons:
    - They take more disk space compared to native packages
    - They are sometimes problematic with some software that is not made to run inside a sandbox
    - Use for terminal programs often require doing some extra steps
### When should I install a flatpak?
- When the software is supposed to be primarily run as Flatpak (for example Bottles)
- When you are installing software that you don't trust (you can control its permissions)
- When it's a GTK/Gnome application (because Nyarch ships their runtimes and they install fast)
- When the software does not run in the terminal
### Installing a Flatpak
#### Gnome Software
You can use **Gnome Software** to find, install, uninstall, and update flatpak applications.

![immagine](https://github.com/user-attachments/assets/34132dbc-f032-475b-90f9-1eec75f1eabd )
![immagine](https://github.com/user-attachments/assets/e2da8b38-7de6-44d3-a045-7a1b5fd4291a )
#### From Flathub
You can find flatpaks on [Flathub](https://flathub.org/ ). Installing an application from there makes your browser download a `.flatpakref` file; clicking it opens the application in Gnome Software

**Note**: Every application on Flathub is also in Gnome Software
#### Command Line
```bash
flatpak install application.id
```
For example, to install firefox via Flatpak
```bash
flatpak install org.mozilla.firefox
```
With the command line, you can also install `.flatpak` files.

To do that, you can just run
```bash
flatpak install file.flatpak
```

Also, double-clicking on a `.flatpak` file opens Gnome Software to install it.

### Managing Flatpak permissions
You can manage flatpak permissions using Flatseal.


## Appimages
**Appimages** are a special format that can be run on every Linux distribution.
- Pros:
    - They work on *every* Linux distribution
- Cons:
    - They do not share libraries with other applications
    - They are generally slower
    - Often they don't support theming

It is generally not suggested to use appimages if there are other packaging formats available. 
Use appimages **only if there is no alternative**.
### Installing and managing Appimages
After downloading an appimage, you can double-click on it and it will launch **GearLever**.

GearLever is a simple software that helps you install and uninstall appimages. 
You can choose to run the appimage once without installing or add it to the app menu.

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

## Arch User Repository
The [AUR](https://aur.archlinux.org/ ) (Arch User Repository) is a big community-driven store for packages that aren't officially supported by Arch Linux. **If an application exists, it's very likely that you will find it in the AUR.**

Nyarch Linux is fully compatible with the AUR, since it uses default Arch Linux repositories.

**Warning**: The packages on the AUR are uploaded by users, so they might not be safe. It's suggested to always check if they are trustable from the package builds.

### Installing a package
To install an AUR package, you need an [AUR Helper](https://wiki.archlinux.org/title/AUR_helpers ).

By default, Nyarch Linux ships `yay` as the default AUR helper. (Or `nyay` because lol nya)

To install an AUR package, you can run
```bash
yay -S package
```
For example,
```bash
yay -S zen-browser-bin
```

##### Updating packages
```bash
yay
```
Updates all packages from the AUR

### Using paru
`paru` is a feature-rich AUR helper written in Rust, the successor to `yay`, providing safer defaults and more active maintenance.

To install `paru`, you can run:
```bash
sudo pacman -S --needed base-devel git
git clone https://aur.archlinux.org/paru.git 
cd paru
makepkg -si
```

##### Installing packages with paru
`paru` uses syntax similar to `pacman`, making it easy to pick up.

To install an AUR package, you can run:
```bash
paru -S package
```
For example,
```bash
paru -S chrome
```

##### Updating packages
```bash
paru
```
or
```bash
paru -Syu
```
This updates all packages from both official repositories and the AUR.

##### paru tips
- **Exit review**: Press q to exit during review
- **View PKGBUILD**: `paru -Gp package` lets you view the package build script before installation
- **View AUR comments**: `paru -Gc package` lets you view comments from other users about the package
- **Interactive search**: Running `paru searchterm` directly lets you search interactively and select for installation
- **Skip review**: `paru -S package --skipreview` (not recommended for untrusted packages)

### Guide to Package names
You might encounter multiple packages for the same program. This is an example for Vesktop:
![immagine](https://github.com/user-attachments/assets/e38667d5-a46a-4d39-8205-ad3ee276d90b )

Based on the suffix:

- `-git`: This package is built from the latest code in the Git repository. It might not be stable, but you'll get the latest features and updates. Also, it will **compile the package**

- `-bin`: This package is a binary package, which means it's **pre-compiled** and ready to use. You don't need to build it from source
- If there's no suffix, it usually means that the package is the "release" version. In other words, it's the latest stable version of the software, without any suffixes or prefixes.
```