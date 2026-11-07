# Running Windows Games on Nyarch Linux

On Nyarch Linux there are three main ways to play Windows games: **Steam + Proton**, **Bottles** and **Lutris**. They are not mutually exclusive: each one covers a different need, and many users end up using two or all three of them.

This page only covers the options that actually work on Nyarch and how to install them. If your games are on Steam, use Steam first; if they come from GOG, Epic, itch.io or a standalone installer, Bottles or Lutris will fit better.

## Steam + Proton

If you mostly buy games on Steam, this is the least painful way. Proton is Valve's Wine-based compatibility layer, it ships inside the Steam client, so there is nothing to install separately.

### Installing Steam on Nyarch

Nyarch has Flathub enabled by default, so the most direct way is to install Steam from Flatpak:

```bash
flatpak install flathub com.valvesoftware.Steam
```

You can also use the `steam` package from the Arch repositories (the `multilib` repository must be enabled):

```bash
sudo pacman -S steam
```

You can also install **steam-native-runtime** (AUR) to launch Steam against your native system libraries, via `steam-native`.

**Note:** the Steam Flatpak ships its own patched glibc; when a game refuses to start with the native package, the Flatpak build may work instead.

### Enabling Proton

After installing Steam, open **Steam > Settings > Compatibility** and enable "**Enable Steam Play for all other titles**". Steam will then try to run even the games Valve has not marked as compatible.

For a single game you can also force a specific Proton version from the "Compatibility" tab of the game's properties.

## Bottles

Bottles is a Wine prefix manager: it fits non-Steam games, standalone installers, GOG offline installers, or any case where you want a separate Wine environment per game.

The Bottles developers **strongly recommend installing it from Flatpak**, because only the Flatpak build can use the sandbox for isolation.

```bash
flatpak install flathub com.usebottles.bottles
```

You can also install it from its Flathub page, or from GNOME Software / Bazaar. In fact, the Nyarch Flatpak guide already uses Bottles as its typical "good candidate for Flatpak" example.

The core concept of Bottles is the **Bottle**: every Bottle is an independent Wine prefix with its own Windows version, DXVK, VKD3D, dependencies and so on. You never "install Wine" system-wide, Bottles manages the Wine versions and runtimes it needs.

## Lutris

Lutris is a better fit when you want "one place to manage every launcher": GOG, Epic, Battle.net, emulators, standalone installers, and community-maintained install scripts.

On Nyarch you can install Lutris in two ways. From Flatpak:

```bash
flatpak install flathub net.lutris.Lutris
```

Or from the Arch repositories:

```bash
sudo pacman -S lutris
```

Keep in mind that if you mostly play GE-Proton games through Lutris, the **native Lutris package (Arch repositories) is probably the safer choice**; if you only use Lutris to manage Wine-GE or plain Wine games, the Flatpak build is usually fine.

## Compatibility Layer Managers: ProtonUp-Qt and ProtonPlus

Whichever of Steam, Bottles or Lutris you use, you will probably need community compatibility layers such as GE-Proton, Wine-GE or Luxtorpeda. Downloading and placing them by hand is tedious, so you can use the ProtonUp-Qt and ProtonPlus graphical managers instead.

If you only use Steam and Lutris, ProtonUp-Qt already covers everything you need.

### ProtonUp-Qt

ProtonUp-Qt supports Steam, Lutris and Heroic, and can install, update and remove Proton-GE, Wine-GE, Luxtorpeda and more. It is distributed through Flathub:

```bash
flatpak install flathub net.davidotek.pupgui2
```

### ProtonPlus

ProtonPlus is another modern compatibility layer manager with broader launcher support (Steam, Lutris, Heroic, Bottles, WineZGUI), and it is also available on Flathub:

```bash
flatpak install flathub com.vysp3r.ProtonPlus
```
