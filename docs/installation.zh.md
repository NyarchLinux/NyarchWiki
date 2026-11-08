# 安装 Nyarch Linux

如果你已经安装过其他 Linux 发行版，那么 Nyarch Linux 的安装过程也类似。

如果你从未安装过 Linux 发行版，建议先考虑安装其他发行版喵～
当然，如果你仍想继续，可以选择在以下环境中安装 Nyarch：

1. [你的电脑](#在你的电脑上安装-nyarch)
2. [虚拟机](#install-nyarch-on-a-virtual-machine)
3. [在现有的 Linux 发行版上](/nyarcher)

## 在你的电脑上安装 Nyarch

### 先决条件

- 一台符合[建议配置](https://nyarchlinux.moe/#requirements)的猫猫电脑喵～
- 容量至少为 4GB 的 U 盘
- 一台可正常工作的电脑（如果你使用 [Etchdroid](https://etchdroid.app/)，安卓设备也可以喵～）
- 已下载正确的 Nyarch ISO 文件。ISO 文件可在 [https://nyarchlinux.moe/](https://nyarchlinux.moe/#download) 找到。如果你使用 **NVIDIA GPU**，请[在此](https://wiki.nyarchlinux.moe/nvidia)查看支持情况
- 备份电脑上所有重要文件

### 创建可启动驱动器

1. 下载 [Balena Etcher](https://etcher.balena.io/) 或任何你更熟悉的类似程序
2. 将 U 盘插入电脑
3. 打开 Balena Etcher

    ![图片](https://github.com/user-attachments/assets/0fe6d643-86ac-4f37-980d-ca82e74e5484)

    然后点击“从文件刷写”。

4. 选择你之前下载的 Nyarch Linux ISO 文件。
5. 点击“选择目标”

    ![图片](https://github.com/user-attachments/assets/c17a0629-e35f-4523-a21a-638bdbc0c4c3)

    并选择你的 U 盘。

    **注意：务必选择正确的驱动器，因为该驱动器上的所有文件都会丢失。**

6. 点击“刷写”并等待完成。

    ![图片](https://github.com/user-attachments/assets/8a0f4a68-c36a-4f8f-968d-0b2c59d442dd)

### 使用Ventoy ###

按照 Ventoy 官方说明制作好 Ventoy 启动盘，将 Nyarch 镜像放入你的移动猫盘，随后在 Ventoy 启动菜单中选择 ISO 镜像喵～

### 选择安装方法

你可以选择以下方式安装 Nyarch：

1. 清空整个磁盘并安装 Nyarch
2. 在同一磁盘上与 Windows 共存安装 Nyarch
3. 在另一块磁盘上与 Windows 共存安装 Nyarch

如果选择第 1 或第 3 种方式，请跳到下一节。
如果选择第 2 种方式，则必须**缩小 Windows 分区**。

#### 缩小 Windows 分区

1. 启动 Windows。
2. 哭哭喵～
3. 在“创建并格式化硬盘分区”下找到并打开 `磁盘管理` 工具。
4. 右键单击主 Windows 分区，选择 `压缩卷...`。

    ![图片](https://github.com/user-attachments/assets/01cb1a7c-7881-4d41-848d-fbf52240124f)

5. 将分区容量缩小至少 30GB。这部分空间将留给 Linux。

    ![图片](https://github.com/user-attachments/assets/ee2077d3-9ff8-4375-bf31-2c7234855bf2)

### 从 Live USB 启动

1. 将 U 盘连接到设备。
2. 进入设备的 BIOS/UEFI 设置。进入方式因设备而异。
   如果你不知道如何进入 BIOS，可以在设备启动时狂按 F 键，并大喊 *欧拉欧拉欧拉欧拉欧拉！！！*，直到按对为止。
3. 禁用安全启动（Secure Boot）。
4. 找到启动顺序设置，将 U 盘设为第一启动项。或者，如果你能打开启动菜单，也可以直接从那里选择 U 盘启动。
5. 保存设置并退出。
6. 希望 Nyarch Live 能顺利启动。如果无法启动，请检查是否确实将 U 盘设为第一启动项，然后到 Nyarch Support 频道（或任意 Linux 社区支持渠道）化身猫娘求助喵～。

### Nyarch Live 环境

你 *但愿* 已成功启动 Nyarch 喵～
现在你正处于 **Live 环境** 中。

安装 Linux 发行版时，Live 环境就像一种“先试后买”的体验。
它是一个**临时操作系统**，你可以从 U 盘或 CD 运行，而无需实际安装到电脑硬盘上。

这样，**你可以测试该 Linux 发行版的运行情况**，尤其是 **Wi-Fi、硬件设备、声音等**。你还可以探索 Nyarch 的一些功能，但请注意，由于 U 盘的 I/O 速度限制，**其性能不如已安装的系统**。

如果你在 Live 环境中需要执行需要输入用户密码的操作，密码是 `live` 哦喵～

#### Nyarch 安装程序

安装程序会在系统启动时自动启动。

![图片](https://github.com/user-attachments/assets/d294db49-5fd7-4844-9083-59790998dcc7)

随后，它会提示你填写本地化设置。按照你的偏好填写即可喵～

##### 分区

**注意**：这部分操作需要格外小心，因为出错可能导致数据丢失！

![图片](https://github.com/user-attachments/assets/dea978b0-b0fd-4d23-b05d-e6a4e59c6f94)

在这里，你可以选择以下安装方式：

- 擦除整个磁盘，并在其上安装 Nyarch。你可以在窗口上部选择不同的磁盘。
- 用 Nyarch 替换某个现有分区进行安装（图片中未显示）。
- 与另一个操作系统共存安装 Nyarch（图片中未显示）。
- 手动选择分区（如果你清楚自己在做什么）。

你还可以选择：

- **Swap**：相当于存放在磁盘上的额外内存。强烈建议启用。
- **文件系统**：你可以从以下选项中选择文件系统：
    - **ext4**：Linux 发行版的标准文件系统。在许多情况下速度更快，也被认为更稳定。
    - **btrfs**：支持**即时快照**，对数据损坏和冗余提供更多保护。某些情况下稍慢（Intel 用户请不要选择，见 [Issues #62](https://github.com/NyarchLinux/NyarchLinux/issues/62)）。
    - **xfs**：除非你清楚自己在做什么，否则不要安装它喵～

##### 完成安装

选择你的猫猫，等待安装完成，然后重启！

![图片](https://github.com/user-attachments/assets/9a9b4116-dc34-4b18-9b9f-b85b40f27ed6)

![图片](https://github.com/user-attachments/assets/6115a3d3-e75c-4028-b71f-3b0a35109f4b)

## Install Nyarch on a Virtual Machine

- 推荐用于安装 Nyarch 的虚拟机软件：VMware Workstation、QEMU、GNOME Boxes
- 不推荐用于安装 Nyarch 的虚拟机软件：VirtualBox（因为 3D 加速性能较差）

Nyarch 大量使用动画，让你的猫猫电脑用起来更顺畅，所以请务必**在虚拟机中启用 3D 加速**。否则它会卡得特别厉害喵～。相信我，猫猫你肯定不想看到比《蓝色监狱》第二季更差的动画。

使用以下规格创建虚拟机：

- CPU：越多越好，或按你的偏好分配
- 内存：至少 3GB，建议 6GB，以获得流畅体验
- 存储：至少 30GB，用于安装操作系统
- UEFI/BIOS 均受支持

创建并启动虚拟机后，跳到[Nyarch Live 环境](#nyarch-live-environment) 喵～

