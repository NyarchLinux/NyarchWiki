# 未来项目
本页面包含未来和正在开发的项目及其详细信息喵～。

如果您想为 Nyarch 开发做出贡献，您可以提出新项目，或为此处列出的项目做出贡献。要做出贡献，您可以在 [Discord](https://discord.gg/xuw6BNXXE7) 或 [GitHub](https://github.com/NyarchLinux/NyarchLinux) 上联系我们喵～。

## 项目概览
| 项目 | 项目类型 | 开发状态 | 所需技能 | 更多信息 |
|---|---|---|---|---|
| [KDE Plasma Spin](#kde-plasma-spin) | 桌面 Spin | 开发中 | 编程、Kirigami、ISO 构建 |  |
| [Hyprland Spin](#hyprland-spin)  | 桌面 Spin | 思考中  | 编程、gtk-layer-shell、ISO 构建 |   |
| [Nyarch Assistant 桌面宠物](#nyarch-assistant-desktop-puppet)  | 桌面应用程序 | 开发中 | 编程、Python、GTK Layer Shell  | Acchan 作为桌面宠物，集成 AI |
| [Nyarch Tuner](#nyarch-tuner)  | 桌面应用程序 | 思考中 | 编程、GTK  | 用户友好的实用程序，用于配置内核、zram、预加载... |
| [AI 壁纸生成器](#ai-wallpaper-generator)  | 桌面应用程序 | 思考中 | 编程、GTK  | 使用 AI 的简单动漫壁纸生成器 |
| 应用程序选择 Calamares  | 改进 | 思考中 | Calamares  | 添加配置页面，让您选择在 Calamares 安装程序上禁用/启用某些 Nyarch 功能 |
| [新主页](#new-website)  | 网站 | 开发中 | HTML、CSS、JS  | Nyarch 的新现代滚动网站。目前分配给 Wawa。 |
| [更好的 AI 集成](#better-ai-intergation)  | 桌面应用程序 | 思考中（已拒绝） | 编程、Python  | 添加写作助手、OCR 等...并与 Nyarch Assistant 集成  |

## 项目描述
在本节中，您可以找到有关项目的一些探索以及可能加速开发的软件、库等。

对于每个项目，列出了以下内容：

- **目标**：项目想要实现的目标
- **要求**：项目必须具备才能发布的要求。`(次要)` 要求可以在发布后通过更新实现。
- **探索**：可能加速开发的软件、实验...
- **任务**：创建项目所需的任务

### KDE Plasma Spin
#### 目标

1. 提供仍然遵循 Nyarch 原则的新桌面 spin
2. 使 Nyarch 成为那些讨厌 Gnome 的人的可考虑发行版
3. 由于 KDE 自定义，覆盖更大的桌面偏好分布
4. 将 Nyarch 应用程序转换为 Kirigami 以保持一致性
#### 要求

1. 必须遵循 Material UwU 原则
2. Nyarch 额外应用程序应该在 KDE 版本中感觉连贯，可能用 Kirigami 重写
3. 发行版必须具有桌面使用的所有重要 KDE 软件包，但不要太多臃肿喵～

#### 探索

**R1** 可以通过 [KDE Material You colors](https://github.com/luisbocanegra/kde-material-you-colors) 和 [Adwaita Material You](https://github.com/FrancescoCaracciolo/adwaita-material-you/) 用于 GTK 应用程序主题来实现。

以下截图可以作为此实现的参考点：

![image](https://github.com/user-attachments/assets/20a855e8-2718-4ca4-8fb6-370ce04f5e2f)
![image](https://github.com/user-attachments/assets/c1e4bea4-8978-49d6-9f9f-da93fcbc155e)
![image](https://github.com/user-attachments/assets/a5530f89-0fc9-46b5-bf05-c80c8e1578d4)

GTK 应用程序和 KDE 应用程序仍然感觉不完全连贯，但它们不会感觉格格不入。可以使用 GTK 应用程序进行早期发布。

因为很酷，我们还将添加 [Geometry Change](https://store.kde.org/p/2136283/)喵～

#### Tasks

| 任务 | 描述 | 状态 | 复杂度 | 更多信息 | 关键性 |
|---|---|---|---|---|---|
| 创建带KDE的ISO | 创建一个包含所需Plasma软件包的Nyarch ISO，并使其可启动和可安装 | 已完成 | 简单 |  | 关键 |
| 寻找KDE替代品 | 	
为部分臃肿软件寻找KDE替代方案（例如Komikku...） | 代办 | 简单 |  | 可选 |
| 安装 `kde-material-you` | 安装KDE Material You用于主题化 | 已完成 | 简单 |  | 关键 |
| KDE配置文件 | 寻找并添加相关的配置文件到发行版中 | 进行中 | 简单 |  | 关键 |
| 确保正确的GTK支持和主题化 | 自定义配置文件以确保GTK支持 | 可选 | 简单 |  | 关键 |
| Catgirl下载器Kirigami版本 | 	
使用Kirigami重写Catgirl下载器 | 可选 | 简单 |  | 关键 |
| Nyarch向导Kirigami版本 | 	
使用Kirigami重写Nyarch向导 | 可选 | 中等 |  | 可选 |
| Nyarch脚本Kirigami版本 | 使用Kirigami重写Nyarch脚本 | 可选 | 中等 |  | 可选 |
| Nyarch导览Kirigami版本 | 使用Kirigami重写Nyarch导览 | 可选 | 简单 |  | 可选 |
| Nyarch助手Kirigami版本 | 使用Kirigami重写Nyarch助手 | 可选 | 关系 |  | 可选 |
| 主页更新 | 	
更新网站以支持多个分支版本 | 可选 | 中等 |  | 关键 |


### Hyprland spin
#### 目标

1. 提供仍然遵循 Nyarch 原则的新桌面 spin
2. 使 Nyarch 成为喜欢平铺 WM 的用户的可考虑发行版
3. Hyprland 非常酷，所以 Nyarch 版本也要很酷喵～
4. 提供具有更酷动画和视觉效果的 Nyarch Spin
5. 更深入集成的 weeb 软件

#### 要求

1. 必须遵循 Material UwU 原则
2. 它必须足够稳定，不会太多破坏
3. 为不太高级的用户提供布局切换器（可选）
4. 对不太高级的用户来说必须简单（可选）
5. 查找或创建合适的 dotfiles

#### 探索

**R1** 可以通过 [Adwaita Material You](https://github.com/FrancescoCaracciolo/adwaita-material-you/) 用于 GTK 应用程序主题来实现。此外，使用 pywal 等，我们可以主题化 UI 的其他元素。

对于可能的 dotfiles，我们有多种可能性：

##### dots-hyprland

![315949766-711f5475-93ca-4097-a960-8047acc85cc7](https://github.com/user-attachments/assets/f3c3c6de-d0f3-443e-a846-df7cd46f9de3 )


[end-4's dots-hyprland](https://github.com/end-4/dots-hyprland ) 目前有几个备选的 Hyprland 配置方案，各有特点：

- Material You 主题风格 (**R1**)
- 外观精美
- 功能丰富
- 二次元元素
- 集成 AI 聊天

然而，存在以下问题：

- 依赖项众多
- 需要构建自定义软件包
- 非常容易随时间出现问题

##### HyprYou


![](https://github.com/koeqaife/hyprland-material-you/blob/v2/assets/screenshot.png?raw=true )

[HyprYou](https://github.com/koeqaife/hyprland-material-you ) 是一个非常完整的配置，遵循 **R1** 原则且依赖项不多。
此外，它在不触及用户主目录的情况下进行打包，这使得它更易于实现。

##### LinkFRG Dotfiles

![](https://github.com/linkfrg/dotfiles/raw/main/assets/4.png )

[linkfrg dotfiles](https://github.com/linkfrg/dotfiles/ ) 是一个非常不错的选择。与前者不同，它使用 Ignis 而非旧版本的 AGS，因此更易于维护、功能更强大且易于扩展。同时，依赖项也不多。不过目前相比上述方案缺少一些功能。

##### Custom dotfiles
最复杂的选项。这基本上相当于编程开发一个桌面环境。gtk_layer_shell 可能会是个好帮手。

如果有猫猫想做并且能做好，我会很高兴的喵～

#### Tasks

| 任务 | 描述 | 状态 | 复杂度 | 更多信息 | 关键程度 |
|---|---|---|---|---|---|
| 创建 Hyprland ISO | 创建包含所需 Hyprland 软件包的 Nyarch ISO，并使其可启动和安装 | 待办 | 简单 |  | 关键 |
| 完成其他所有工作 | 还没决定好，哈哈 | 待办 | 复杂 |  | 关键 |
| 网站更新 | 更新网站以支持多个衍生版本 | 待办 | 复杂 |  | 关键 |

### Nyarch Assistant Desktop Puppet
#### 目标

1. 在桌面上显示 Live2D 模型（默认使用 arch-chan）
2. 与 Nyarch Assistant 轻松交互
3. 陪伴孤独的 Nyarch 用户
4. 看起来很酷
5. 拥有一个桌面伙伴，为 Linux 创建 Desktop Mate 的替代品
#### 需求 
1. 模型与 Nyarch Assistant 集成
2. 可以与模型交互，移动它
3. 通过某些交互触发动画（可选）
4. 模型眼睛跟随鼠标移动
5. 可以轻松调整模型所在的图层
6. 与 Nyarch 桌面衍生版本兼容
7. 可以轻松地在 Nyarch 之外运行
#### 探索
已使用 gtk_layer_shell 编写了少量代码来验证这是否可行。
结果如下：

<video src="https://github.com/user-attachments/assets/16018382-5134-45c7-9c64-02f4922dc152 " controls=true></video>


这使用 gtk_layer_shell 显示一个带有模型的透明 webview。之后，将点击区域调整为模型的位置和大小。

光标跟随通过轮询鼠标位置实现（演示中为 10FPS），并让 Live2D 模型聚焦于此。当前实现仅在 Hyprland 上有效，但也可以在 KDE Plasma 上实现。
GTK Layer shell 目前**不支持 Gnome**，但很可能可以通过扩展用几乎相同的代码实现。

#### 任务
| 任务 | 描述 | 状态 | 复杂度 | 更多信息 | 关键程度 |
|---|---|---|---|---|---|
| 正确调整模型大小 | 目前模型大小处理不够完善，无法适应任何显示器分辨率 | 待办 | 简单 |  | 关键 |
| 支持 KDE Plasma | 支持 KDE 鼠标移动和 KDE 显示器 | 部分完成 | 简单  | | 关键 |
| 更好的 Hyprland 支持 | 支持 Hyprland 显示器 | 已完成 | 简单 |  | 关键 |
| 支持 Gnome | 添加 Gnome 支持，需要自定义扩展 | 部分完成 | 中等 |  | 关键 |
| 添加模型交互 | 添加与模型交互和显示动画的功能 | 待办 | 中等 |  | 关键 |
| 与 Nyarch Assistant 集成 | 模型必须连接 Nyarch Assistant | 已完成 | 中等 |  | 关键 |
| 添加 Nyarch Assistant 截图功能 | 模型可以截取屏幕截图来帮助用户（当然需要在提示和允许的情况下） | 已完成 | 简单 |  | 关键 |
| 添加一些空闲动画 | 模型在桌面上移动并执行操作 | 待办 | 复杂 |  | 可选 |
| 网站更新 | 更新网站以列出此功能 | 待办 | 简单 |  | 关键 |

开发阶段：在早期开发阶段，我们可以发布 Nyarch Assistant 扩展以接收用户反馈

### Better AI Intergation

此功能已通过投票拒绝。将不会实施。

#### 目标

1. 简化与 Nyarch Assistant AI 的交互
2. 使用 LLM 添加生活质量改进

欢迎其他目标。 
#### 需求

待定

#### 探索

##### 快速聊天访问
我们可以 fork 或与 [Penguin AI Chatbot for Gnome](https://gitlab.com/martijara/Penguin-AI-Chatbot-for-GNOME ) 合作，为 Nyarch Assistant 提供即时聊天访问。
对于 Hyprland 和 KDE 版本，可以采用类似的方法。

##### 写作助手
我们可以实现一个写作助手来简化摘要、重写和类似任务。

<video src="https://github.com/user-attachments/assets/37cee779-694f-459f-a49d-8892abc46eae " controls=true></video>

**注意**：延迟是由录制造成的

#### 任务
待定。

### Nyarch Tuner
#### 目标

1. 让初学者更容易进行 Nyarch/Arch 性能调优
2. 提供简单的 UI 来配置 zram
3. 提供简单的 UI 来配置 swapfile
4. 提供简单的 UI 来配置 preload
5. 提供简单的 UI 来配置内核
5. 提供简单的 UI 来配置电源级别（可选）
#### 需求
1. 应用程序不能破坏系统（你知道，如果它不会破坏系统就很酷）
2. 应用程序必须对用户简单易用
3. 应用程序必须解释技术和配置的作用
4. 必须根据硬件资源提供建议配置（可选）
5. 至少第一个版本必须用 GTK 编写
6. 应用程序必须在通用 Arch Linux 上工作（可选）
#### 探索
无
#### 任务
待定，整个项目估计需要约 80 小时。

### AI Wallpaper generator
    AI 壁纸生成器
#### 目标
1. 使用 AI 快速生成用作壁纸的图像
2. 提供一些提示模板（用户选择）以生成高质量图像
3. 为 AI 图像生成创建良好的软件基础设施
4. 与 Nyarch Assistant 集成（可选）
5. 支持放大
#### 需求
1. 应用程序必须使用 GTK 工具包编写
2. 应用程序必须提供一些带有下拉选项的提示模板，以生成高质量图像（可选）
3. 应用程序必须支持多个图像生成提供商
4. 应用程序必须支持多个图像放大器
5. 应用程序必须检测用户分辨率，以找到最合适的分辨率来生成和自动放大图像（可选）
6. 应用程序必须支持完全自定义的提示生成
7. 应用程序必须提供直接设置为壁纸或保存的选项
#### 任务
| 任务 | 描述 | 状态 | 复杂度 | 更多信息 | 关键程度 |
|---|---|---|---|---|---|
| 设计图像生成处理器 | 为图像生成工具设计通用属性 | 待办 | 简单 |  | 关键 |
| 设计通用界面 | 设计应用程序的通用界面，提供提示模板、放大、自定义提示等选项 | 待办 | 复杂  | | 关键 |
| 设计放大处理器 | 为放大工具设计通用属性 | 待办 | 简单 |  | 关键 |
| 添加图像生成处理器 | 添加通用图像生成处理器，例如 OpenAI 和 Stablediffusion | 待办 | 简单 |  | 关键 |
| 添加图像放大 | 添加图像放大工具支持 | 待办 | 简单 |  | 关键 |
| 与 Nyarch Assistant 集成 | 允许 Nyarch Assistant 用它生成图像 | 待办 | 中等 |  | 可选 |

### New Website
#### 目标

1. 为 Nyarch 设计一个更现代的新网站
2. 网站必须对已了解 Nyarch 并只想下载 ISO 或获取快速信息的用户实用
3. 网站必须展示和宣传 Nyarch 的主要功能

#### 需求
1. 网站必须容纳 1-3 个桌面衍生版本，展示其功能并引导用户做出正确选择
2. 安装 Nyarch 仍然需要向用户展示一些关于他正在下载的内容的信息
3. 网站必须容纳社交媒体链接，特别是宣传 Discord
4. 网站必须容纳 Wiki、源代码和捐赠链接喵喵～ 

#### 探索
网站正在开发为一个滚动式网站。 

![image](https://github.com/user-attachments/assets/e9cb45b2-f469-4969-ad6e-ef247f622ec5 )

#### 任务

待定
