# 未来项目
本页面包含未来和正在开发的项目及其详细信息喵～。

如果您想为 Nyarch 开发做出贡献，您可以提出新项目，或为此处列出的项目做出贡献。要做出贡献，您可以在 [Discord](https://discord.gg/xuw6BNXXE7) 或 [GitHub](https://github.com/NyarchLinux/NyarchLinux) 上联系我们喵～。

## 项目概览

| 项目 | 项目类型 | 开发状态 | 所需技能 | 更多信息 |
|---|---|---|---|---|
| [KDE Plasma Spin](#kde-plasma-spin) | 桌面 Spin | 开发中 | 编程、Kirigami、ISO 构建 | 已完成并发布 |
| [Hyprland Spin](#hyprland-spin) | 桌面 Spin | 构思中 | 编程、gtk-layer-shell、ISO 构建 | 初始阶段 |
| [Nyarch Assistant 桌面宠物](#nyarch-assistant-desktop-puppet) | 桌面应用 | 开发中 | 编程、Python、GTK Layer Shell | Acchan 作为桌面宠物，并集成 AI |
| [Nyarch Tuner](#nyarch-tuner) | 桌面应用 | 构思中 | 编程、GTK | 用户友好的实用工具，用于配置内核、zram、预加载等 |
| [AI 壁纸生成器](#ai-wallpaper-generator) | 桌面应用 | 构思中 | 编程、GTK | 基于 AI 的简易动漫壁纸生成器 |
| Calamares 应用选择 | 改进 | 构思中 | Calamares | 添加配置页面，让您可在 Calamares 安装程序中选择启用/禁用某些 Nyarch 功能 |
| [新主页](#new-website) | 网站 | 开发中 | HTML、CSS、JS | Nyarch 的全新现代滚动式网站。目前分配给 Wawa |
| [更好的 AI 集成](#better-ai-intergation) | 桌面应用 | 构思中（已拒绝） | 编程、Python | 添加写作助手、OCR 等功能，并与 Nyarch Assistant 集成 |

## 项目描述

在本节中，您可以了解一些项目探索，以及可能正在开发的软件、库等。

对于每个项目，列出以下内容：

- **目标**：项目希望实现的目标
- **要求**：项目发布前必须具备的条件。标注为 `(次要)` 的要求可在发布后通过更新实现。
- **探索**：可能加速开发的软件、实验等……
- **任务**：创建项目所需完成的任务

### KDE Plasma Spin

#### 目标

1. 提供遵循 Nyarch 原则的新桌面 Spin
2. 使 Nyarch 成为讨厌 GNOME 的用户也会考虑的发行版
3. 借助 KDE 的自定义能力，满足更广泛的桌面偏好
4. 将 Nyarch 应用迁移到 Kirigami，以保持一致性喵～

#### 要求

1. 必须遵循 Material UwU 原则
2. Nyarch 的额外应用应在 KDE 版本中保持整体连贯，可能需要用 Kirigami 重写
3. 发行版必须包含桌面使用所需的全部重要 KDE 软件包，但不应过于臃肿
#### 探索

**R1** 可以通过 [KDE Material You colors](https://github.com/luisbocanegra/kde-material-you-colors) 和 [Adwaita Material You](https://github.com/FrancescoCaracciolo/adwaita-material-you/) 用于 GTK 应用程序主题来实现。

以下截图可以作为此实现的参考点：

![image](https://github.com/user-attachments/assets/20a855e8-2718-4ca4-8fb6-370ce04f5e2f)
![image](https://github.com/user-attachments/assets/c1e4bea4-8978-49d6-9f9f-da93fcbc155e)
![image](https://github.com/user-attachments/assets/a5530f89-0fc9-46b5-bf05-c80c8e1578d4)

虽然 GTK 应用程序和 KDE 应用程序仍然不完全连贯，但是它们不会感觉格格不入。可以发布一个带有 GTK 应用的早期版本。

因为很酷，我们还将添加 [Geometry Change](https://store.kde.org/p/2136283/) 。

#### 任务

| 任务 | 描述 | 状态 | 复杂度 | 更多信息 | 关键性 |
|---|---|---|---|---|---|
| 创建带 KDE 的 ISO | 创建一个包含必要 Plasma 软件包的 Nyarch ISO，并使其可启动、可安装 | 已完成 | 简单 |  | 关键 |
| 寻找 KDE 替代品 | 为部分臃肿软件寻找 KDE 替代方案（例如 Komikku 等） | 已完成 | 简单 |  | 可选 |
| 安装 `kde-material-you` | 安装 KDE Material You，用于主题定制 | 已完成 | 简单 |  | 关键 |
| KDE 配置文件 | 寻找相关配置文件并添加到发行版中 | 已完成 | 简单 |  | 关键 |
| 确保 GTK 支持与主题化配置正确 | 自定义配置文件，以确保 GTK 支持与主题化正常 | 已完成 | 简单 |  | 关键 |
| Catgirl 下载器的 Kirigami 版本 | 使用 Kirigami 重写 Catgirl 下载器 | 已完成 | 简单 |  | 关键 |
| Nyarch 向导 Kirigami 版本 | 使用 Kirigami 重写 Nyarch 向导 | 已完成 | 中等 |  | 可选 |
| Nyarch 脚本 Kirigami 版本 | 使用 Kirigami 重写 Nyarch 脚本 | 已完成 | 中等 |  | 可选 |
| Nyarch 导览 Kirigami 版本 | 使用 Kirigami 重写 Nyarch 导览 | 已完成 | 简单 |  | 可选 |
| Nyarch 助手 Kirigami 版本 | 使用 Kirigami 重写 Nyarch 助手 | 不予修复 | 复杂 |  | 可选 |
| 主页更新 | 更新网站，以支持多个分支版本 | 已完成 | 中等 |  | 关键 |

### Hyprland Spin

#### 目标

1. 提供一个遵循 Nyarch 原则的新桌面 Spin
2. 使 Nyarch 成为喜欢平铺式窗口管理器（WM）的用户也会考虑的发行版
3. Hyprland 非常酷，所以 Nyarch 的版本也要很酷喵～
4. 提供一个动画和视觉效果更酷的 Nyarch Spin
5. 更深入地集成御宅系软件

#### 要求

1. 必须遵循 Material UwU 原则
2. 必须足够稳定，不能频繁出问题
3. 为非高级用户提供布局切换器（可选）
4. 对非高级用户而言必须简单易用（可选）
5. 寻找或创建合适的 dotfiles

#### 探索

**R1** 可以通过 [Adwaita Material You](https://github.com/FrancescoCaracciolo/adwaita-material-you/) 用于 GTK 应用程序主题来实现。此外，使用 pywal 等，我们可以主题化 UI 的其他元素。

对于可能的 dotfiles，我们有多种可能性：

##### dots-hyprland

![315949766-711f5475-93ca-4097-a960-8047acc85cc7](https://github.com/user-attachments/assets/f3c3c6de-d0f3-443e-a846-df7cd46f9de3 )


[end-4's dots-hyprland](https://github.com/end-4/dots-hyprland) 目前有几个备选的 Hyprland 配置方案，各有特点：

- Material You 主题风格（R1）
- 外观精美
- 功能丰富
- 御宅元素
- 集成 AI 聊天功能

然而，存在以下问题：

- 依赖项众多
- 需要构建自定义软件包
- 随着时间推移很容易出现问题

##### HyprYou

![](https://github.com/koeqaife/hyprland-material-you/blob/v2/assets/screenshot.png?raw=true)

[HyprYou](https://github.com/koeqaife/hyprland-material-you) 是一个相当完整的配置，遵循 **R1** 原则，且依赖项不多。
此外，它在打包时不会改动用户主目录，因此更易于部署。

##### Custom dotfiles

这是最复杂的选项，基本上相当于从零开发一个桌面环境。`gtk-layer-shell` 可能会很有帮助。

如果有猫猫愿意做并且能做好，我会很高兴的喵～

#### 任务

| 任务 | 描述 | 状态 | 复杂度 | 更多信息 | 关键程度 |
|---|---|---|---|---|---|
| 创建 Hyprland ISO | 创建一个包含必要 Hyprland 软件包的 Nyarch ISO，并使其可启动、可安装 | 已完成 | 简单 |  | 关键 |
| 添加 Plymouth 主题 | 使用 Plymouth 主题定制启动画面 | 学习中 | 中等 |  | 关键 |
| 完成其他所有工作 | 其他各种尚未完成的事项喵～ | 待办 | 复杂 |  | 关键 |
| 网站更新 | 更新网站，以支持多个衍生版本 | 待办 | 复杂 |  | 关键 |

更多所需信息，请访问 [Nyarch Hyprland's readme](https://github.com/TotallyDIO/NyarchHyprland/blob/main/README.md)

### Nyarch Assistant Desktop Puppet
#### 目标

1. 在桌面上显示 Live2D 模型（默认使用 arch-chan）
2. 与 Nyarch Assistant 轻松交互
3. 陪伴孤独的 Nyarch 用户
4. 看起来很酷喵～
5. 拥有一个桌面伙伴，为 Linux 创建 Desktop Mate 的替代品
#### 需求 

1. 模型与 Nyarch Assistant 集成
2. 可以与模型交互和移动
3. 通过某些交互触发动画（可选）
4. 模型眼睛跟随鼠标移动
5. 可以轻松调整模型所在的图层
6. 与 Nyarch 桌面衍生版本兼容
7. 可以轻松地在 Nyarch 之外的发行版运行
#### 探索

已使用 `gtk_layer_shell` 编写了少量代码来验证这是否可行。
结果如下：

<video src="https://github.com/user-attachments/assets/16018382-5134-45c7-9c64-02f4922dc152" controls=true></video>


这使用 `gtk_layer_shell` 显示一个带有模型的透明 webview。之后，将点击区域调整为模型的位置和大小。

光标跟随通过轮询鼠标位置实现（演示中为 10FPS），并让 Live2D 模型聚焦于此。当前实现仅在 Hyprland 上有效，但也可以在 KDE Plasma 上实现。
GTK Layer shell 目前**不支持 Gnome**，但很可能可以通过扩展用几乎相同的代码实现。

#### 任务
| 任务 | 描述 | 状态 | 复杂度 | 更多信息 | 关键程度 |
|---|---|---|---|---|---|
| 正确调整模型大小 | 目前模型大小处理不够完善，无法适应任何显示器分辨率 | 部分完成 | 简单 |  | 关键 |
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

<video src="https://github.com/user-attachments/assets/37cee779-694f-459f-a49d-8892abc46eae" controls=true></video>

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
该网站正作为一个滚动式网站进行开发。

![image](https://github.com/user-attachments/assets/e9cb45b2-f469-4969-ad6e-ef247f622ec5 )

#### 任务

待定
