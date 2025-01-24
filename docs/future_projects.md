![315949766-711f5475-93ca-4097-a960-8047acc85cc7](https://github.com/user-attachments/assets/3970cbc8-fa73-49a9-ae9f-1aa20bb91bba)# Future Projects
This page contains future and in development projects with their details.  

If you want to contribute to Nyarch Development, you can propose new projects, or contributing to the projects listed here. For contribution you can contact us on [Discord](https://discord.gg/xuw6BNXXE7) or [GitHub](https://github.com/NyarchLinux/NyarchLinux).

## Projects Overview
| Project | Project Type | Development Status | Required Skills | Further information |
|---|---|---|---|---|
| [KDE Plasma Spin](#kde-plasma-spin) | Desktop Spin | Idea | Programming, Kirigami, ISO Building |  |
| [Hyprland Spin](#hyprland-spin)  | Desktop Spin | Idea  | Programming, gtk-layer-shell, ISO Building |   |
| [Better AI Integration](#better-ai-intergation)  | Desktop Application | Idea | Programming, Python  | Add writing assistant, OCR etc... and integrate with Nyarch Assistant  |
| [Nyarch Assistant Desktop Puppet](#nyarch-assistant-desktop-puppet)  | Desktop Application | Idea | Programming, Python, GTK Layer Shell  | Acchan as a desktop pet with AI integration |
| [Nyarch Tuner](#nyarch-tuner)  | Desktop Application | Idea | Programming, GTK  | User friendly utility to configure kernels, zram, preoload... |
| [AI Wallpaper generator](#ai-wallpaper-generator)  | Desktop Application | Idea | Programming, GTK  | Simple anime wallpaper generator with AI |
| Application Selection Calamares  | Improvement | Idea | Calamares  | Add a configuration page that makes you choose to disable/enable some Nyarch Features on Calamares installer |
| [New Website](#new-website)  | Website | Development | HTML, CSS, JS  | New modern scrolling website for Nyarch. Currently assigned to Wawa. |

## Projects description
In this section you can find some exploration about the projects and some software, library etc. that might accelerate development.

For every project, this is listed:

- **Goals**: what the project wants to achieve
- **Requiremets**: the requirements the project must have to be released. `(secondary)` requirements can be implemented with updates after release.
- **Exploration**: software that might accelerate the development, experiments... 
- **Tasks**: Required tasks to create the project 

### KDE Plasma Spin
#### Goals

1. Offer a new desktop spin that still follows Nyarch Principles
2. Make Nyarch a considerable distribution for those who hate Gnome
3. Cover a bigger distribution of desktop preference thanks to KDE customization
4. Convert Nyarch applications to Kirigami in order to keep consistency
#### Requirements

1. Material UwU principle must be followed
2. Nyarch extra applications should feel coherent in KDE version, likely be rewritten with Kirigami
3. The distro must have all the important KDE packages for desktop use, but not too much bloat

#### Exploration

**R1** can be followed thanks to [KDE Material You colors](https://github.com/luisbocanegra/kde-material-you-colors) and to [Adwaita Material You](https://github.com/FrancescoCaracciolo/adwaita-material-you/) for GTK application theming.

The following screenshots can be a point of reference for this implementation:

![image](https://github.com/user-attachments/assets/20a855e8-2718-4ca4-8fb6-370ce04f5e2f)
![image](https://github.com/user-attachments/assets/c1e4bea4-8978-49d6-9f9f-da93fcbc155e)
![image](https://github.com/user-attachments/assets/a5530f89-0fc9-46b5-bf05-c80c8e1578d4)

GTK applications and KDE applications still doesn't feel perfectly coherent, but they don't feel out of place. An early release with GTK applications is possible.

Because it's cool, we will also add [Geometry Change](https://store.kde.org/p/2136283/)

#### Tasks

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
| Website update | Update the website to support multiple spins | TODO | Medium |  | Critical |

### Hyprland spin
#### Goals

1. Offer a new desktop spin that still follows Nyarch Principles
2. Make Nyarch a considerable distribution for users who love tiling WM
3. Hyprland is very cool so Nyarch version cool
4. Offer a Nyarch Spin with more cool animations and eyecandy
5. Deeper integrated weeb software

#### Requirements

1. Material UwU principle must be followed
2. It must be stable enough, without too much breaking
3. Layout switcher for not so advanced users (optional)
3. Must be simple for not so advanced users (optional)
4. Find or create suitable dotfiles

#### Exploration

**R1** can be followed thanks to [Adwaita Material You](https://github.com/FrancescoCaracciolo/adwaita-material-you/) for GTK application theming. Also with pywal etc we can theme other elements of the UI.

For possible dotfiles, we have multiple possibilities:
##### dots-hyprland

![315949766-711f5475-93ca-4097-a960-8047acc85cc7](https://github.com/user-attachments/assets/f3c3c6de-d0f3-443e-a846-df7cd46f9de3)


[end-4's dots-hyprland](https://github.com/end-4/dots-hyprland) has a lot of features that perfectly align with Nyarch principles:

- Material You theming (**R1**)
- Good looking
- A ton of features
- Weeb stuff
- AI chat integrated

However, there are these issues:

- Ton of dependencies
- Custom packages to build
- Very likely to break over time

##### Hyprland material you


![](https://github.com/koeqaife/hyprland-material-you/raw/main/screenshots/screenshot1.png)

[Hyprland Material You](https://github.com/koeqaife/hyprland-material-you) is a very complete configuration that respect **R1** and doesn't have a lot of dependencies.
##### LinkFRG Dotfiles

![](https://github.com/linkfrg/dotfiles/raw/main/assets/4.png)

[linkfrg dotfiles](https://github.com/linkfrg/dotfiles/) are a very good options. Unlike the previous, it uses Ignis and not some old version of AGS, thus making it easier to maintain, more powerful, and easy to extend. Also, dependencies aren't many. It does lack some features compared to those above for now.

##### Custom dotfiles
Most complex option. This requires basically programming a DE. gtk_layer_shell might be a good friend for this. 

If anyone wants to do it and can do it well I'm not stopping him.

#### Tasks

| Task | Description | Status | Complexity | Further information | Criticality |
|---|---|---|---|---|---|
| Creating a ISO with Hyprland | Create a Nyarch ISO with required Hyprland packages and make it bootable and installable | TODO | Simple |  | Critical |
| Do everything else | Idk decision still have to be made lol | TODO | Complex |  | Critical |
| Website update | Update the website to support multiple spins | TODO | Complex |  | Critical |

### Nyarch Assistant Desktop Puppet
#### Goals

1. Display a Live2D model (arch-chan by default) on the desktop
2. Easy interaction with Nyarch Assistant
3. Keep company for alone Nyarch users
4. Look cool
5. Having a desktop mate and create a substitution for Desktop Mate for Linux
#### Requirements 
1. The model integrates with Nyarch Assistant
2. You can interact with the model, move it around
3. With some interactions with the model, some animations play (optional)
4. The model follows the mouse movement with the eyes
5. You can easily adjust the layer in which the model is
6. Working with Nyarch desktop spins
7. It can be run easily out of Nyarch
#### Exploration
A small amount of code has been written using gtk_layer_shell to check that this is actually possible.
This is the result:

<video src="https://github.com/user-attachments/assets/16018382-5134-45c7-9c64-02f4922dc152" controls=true></video>


This uses gtk_layer_shell to display a transparent webview with the model. After that, it resizes the click area to the model position and size.

The following of the cursor is done by polling the mouse position (10FPS in the demo) and making the live2d model focus it. The current implementation only works on Hyprland, but can also be done on KDE Plasma.
GTK Layer shell currently is **not supported on Gnome**, but it can likely be implemented with almost same code with an extension.

#### Tasks
| Task | Description | Status | Complexity | Further information | Criticality |
|---|---|---|---|---|---|
| Correctly resize the model | At the moment the model size is not handled perfectly and does not adapt to any monitor resolution | TODO | Simple |  | Critical |
| Support for KDE Plasma | Support KDE mouse movement and KDE monitors | TODO | Simple  | | Critical |
| Better Hyprland support | Support for hyprland monitors | TODO | Simple |  | Critical |
| Support Gnome | Add Gnome support, which require a custom extension | TODO | Medium |  | Critical |
| Add model interactions | Add abilities to interact with the model and show animations | TODO | Medium |  | Critical |
| Integration with Nyarch Assistant | The model must connect with Nyarch Assistant | TODO | Medium |  | Critical |
| Add screenshot capability with Nyarch Assistant | The model can take a screenshot of the screen to help the user (obv if prompted and allowed) | TODO | Simple |  | Critical |
| Add some idle animations | The model moves around and does thing on your desktop | TODO | Complex |  | Optional |
| Website update | Update the website to list this feature | TODO | Simple |  | Critical |

Development phase: in an early development phase, we can ship a Nyarch Assistant extension in order to receive feedback from users

### Better AI Intergation
#### Goals

1. Simplify interaction with Nyarch Assistant AI
2. Add quality of life improvements using LLM

Other goals are welcome. 
#### Requirements

TBD

#### Exploration

##### Quick Chat access
We can fork or collaborate with [Penguin AI Chatbot for Gnome](https://gitlab.com/martijara/Penguin-AI-Chatbot-for-GNOME) to provide on the fly chat access with Nyarch Assistant. 
For Hyprland and KDE version, similar approaches can be done.

##### Writing assistant
We can implement a writing assistant to simplify Summaries, Rewrites and similar tasks.

<video src="https://github.com/user-attachments/assets/37cee779-694f-459f-a49d-8892abc46eae" controls=true></video>

**Note**: Lag is caused by recording

#### Tasks
TBD.

### Nyarch Tuner
#### Goals

1. Make Nyarch/Arch performance tuning easier for beginners
2. Provide easy UI to configure zram
3. Provide easy UI to configure swapfile
4. Provide easy UI to configure preload
5. Provide easy UI to configure kernels
5. Provide easy UI to configure power levels (optional)
#### Requirements
1. The application must not break the system (yk it would be cool if it doesn't)
2. The application must be simple to use for users
3. The application must explain what the technologies and the configurations do
4. There must be e suggested configuration based on hardware resource (optional)
5. At least the first version must be writter in GTK
6. The application must work on Arch Linux in general (optional)
#### Exploration
Nothing
#### Tasks
TBD, the overall project is extimated to require ~80 total hours.

### AI Wallpaper generator
#### Goals
1. Quickly generate images to use as wallpaper with AI
2. Provide some prompts template (user choice) to generate good quality images
3. Create a good softwware infrastructure for AI image generation
4. Integration with Nyarch Assistant (optional)
5. Support upscaling
#### Requirements
1. The application must be written with GTK toolkit
2. The application must provide some prompts template with dropdown options in order to generate good quality images (optional)
3. The application must support multiple image generation providers
4. The application must support multiple image upscalers
5. The application must detect the user resolution to find the most appropriate resolution to generate and upscale the image automatically (optional)
6. The application must provide support for totally custom prompt generation
7. The application must give the possibility to directly set as wallpaper or save it
#### Tasks
| Task | Description | Status | Complexity | Further information | Criticality |
|---|---|---|---|---|---|
| Design handlers for Image generation | Design common properties for image generation tools | TODO | Simple |  | Critical |
| Design the general interface | Design the general interface of the application, offering options for prompt templates, upscaling, custom prompts etc | TODO | Complex  | | Critical |
| Design handlers for Upscaling | Design common properties for upscaling tools | TODO | Simple |  | Critical |
| Add image generation handlers | Add common image generation handlers f.e. OpenAI and Stablediffusion ones | TODO | Simple |  | Critical |
| Add image upscaling | Add image upscaling tools support | TODO | Simple |  | Critical |
| Integration with Nyarch Assistant | Allow Nyarch assistant to generate images with it | TODO | Medium |  | Optional |

### New website
#### Goals

1. Design a new more modern looking website for Nyarch
2. The website must be pratical for users that already know Nyarch and just want to download the ISO or get quick info
3. The website must show and advertise Nyarch main features

#### Requirements
1. The website must accomodate 1-3 desktop spins, showing their features and guiding the user to the right choice
2. Installing Nyarch must still require to show the user a bit of information about what he is downloading
3. The website must accomodate social media links, and specially advertise Discord
4. The website must accomodate Wiki, Source code and Donations link 

#### Exploration
The website is being developed as a scorlling website. 

![image](https://github.com/user-attachments/assets/e9cb45b2-f469-4969-ad6e-ef247f622ec5)

#### Tasks

TBD
