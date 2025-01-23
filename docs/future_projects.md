# Future Projects
This page contains future and in development projects with their details.  

If you want to contribute to Nyarch Development, you can propose new projects, or contributing to the projects listed here. For contribution you can contact us on [Discord](https://discord.gg/xuw6BNXXE7) or [GitHub](https://github.com/NyarchLinux/NyarchLinux).

## Projects Overview
| Project | Project Type | Development Status | Required Skills | Further information |
|---|---|---|---|---|
| KDE Plamsa Spin | Desktop Spin | Idea | Programming, Kirigami, ISO Building |  |
| Hyprland Spin  | Desktop Spin | Idea  | Programming, gtk-layer-shell, ISO Building |   |
| Better AI Integration  | Desktop Application | Idea | Programming, Python  | Add writing assistant, OCR etc... and integrate with Nyarch Assistant  |
| Nyarch Assistant Desktop Puppet  | Desktop Application | Idea | Programming, Python, GTK Layer Shell  | Acchan as a desktop pet with AI integration |
| Nyarch Tuner  | Desktop Application | Idea | Programming, GTK  | User friendly utility to configure kernels, zram, preoload... |
| AI Wallpaper generator  | Desktop Application | Idea | Programming, GTK  | Simple anime wallpaper generator with AI |
| AI Wallpaper generator  | Desktop Application | Idea | Programming, GTK  | Simple anime wallpaper generator with AI |
| Application Selection Calamares  | Improvement | Idea | Calamares  | Add a configuration page that makes you choose to disable/enable some Nyarch Features on Calamares installer |
| New Website  | Website | Development | HTML, CSS, JS  | New modern scrolling website for Nyarch. Currently assigned to Wawa. |

### Projects description
In this section you can find some exploration about the projects and some software, library etc. that might accelerate development.

For every project, this is listed:
- **Goals**: what the project wants to achieve
- **Requiremets**: the requirements the project must have to be released. `(secondary)` requirements can be implemented with updates after release.
- **Exploration**: software that might accelerate the development, experiments... 
- **Tasks**: Required tasks to create the project 

#### KDE Plasma Spin
##### Goals
1. Offer a new desktop spin that still follows Nyarch Principles
2. Make Nyarch a considerable distribution for those who hate Gnome
3. Cover a bigger distribution of desktop preference thanks to KDE customization
4. Convert Nyarch applications to Kirigami in order to keep consistency
##### Requirements
1. Material UwU principle must be followed
2. Nyarch extra applications should feel coherent in KDE version, likely be rewritten with Kirigami
3. The distro must have all the important KDE packages for desktop use, but not too much bloat
##### Exploration

**R1** can be followed thanks to [KDE Material You colors](https://github.com/luisbocanegra/kde-material-you-colors) and to [Adwaita Material You](https://github.com/FrancescoCaracciolo/adwaita-material-you/) for GTK application theming.

The following screenshots can be a point of reference for this implementation:

![image](https://github.com/user-attachments/assets/20a855e8-2718-4ca4-8fb6-370ce04f5e2f)
![image](https://github.com/user-attachments/assets/c1e4bea4-8978-49d6-9f9f-da93fcbc155e)
![image](https://github.com/user-attachments/assets/a5530f89-0fc9-46b5-bf05-c80c8e1578d4)

GTK applications and KDE applications still doesn't feel perfectly coherent, but they don't feel out of place. An early release with GTK applications is possible.

Because it's cool, we will also add [Geometry Change](https://store.kde.org/p/2136283/)

##### Tasks

| Task | Description | Status | Complexity | Further information | Criticality |
|---|---|---|---|---|---|
| Creating a ISO with KDE | Create a Nyarch ISO with required Plasma packages and make it bootable and installable | TODO | Simple |  | Critical |
| Find KDE alternatives | Find KDE alternatives for some of our bloat (Komikku ...) | TODO | Simple |  | Optional |
| Install `kde-material-you` | Install KDE Material You for theming | TODO | Simple |  | Critical |
| KDE Dotfiles | Find and add relevant dotfiles to the distribution. | TODO | Simple |  | Critical |
| Ensure correct GTK support and theming | Customize the dotfiles to ensure GTK support. | TODO | Simple |  | Critical |
| Catgirl Downloader Kirigami version | Rewrite Catgirl downloader in Kirigami. | TODO | Simple |  | Critical |
| Waifu Downloader Kirigami version | Rewrite Waifu downloader in Kirigami. | TODO | Simple |  | Critical |
| Nyarch Wizard Kirigami version | Rewrite Nyarch Wizard in Kirigami. | TODO | Medium |  | Optional |
| Nyarch Script Kirigami version | Rewrite Nyarch Script in Kirigami. | TODO | Medium |  | Optional |
| Nyarch Tour Kirigami version | Rewrite Nyarch Tour in Kirigami. | TODO | Simple |  | Optional |
| Nyarch Assistant Kirigami version | Rewrite Nyarch Assistant in Kirigami. | TODO | Complex |  | Optional |
| Website update | Update the website to support multiple spins | TODO | Complex |  | Critical |

