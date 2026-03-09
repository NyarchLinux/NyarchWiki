如果你已经安装了 Linux 发行版，Nyarch Linux 的安装程序是相同的。

如果你尚未安装 Linux 发行版，请考虑安装其他发行版喵～。
如果你仍然想继续，那么你可以决定在哪里安装 Nyarch：

1. [你的电脑](#installing-nyarch-on-your-computer)
2. [虚拟机](#install-nyarch-on-a-virtual-machine)
3. [在现有的 Linux 发行版上](/nyarcher)

## Installing Nyarch on your Computer
   在你的电脑上安装 Nyarch

### 先决条件
- 一台符合[建议配置](https://nyarchlinux.moe/#requirements )的猫猫
- 至少 4GB 容量的 U 盘
- 一台已能正常工作的电脑（或者如果你使用 [Etchdroid](https://etchdroid.app/ )，安卓设备也可以）
- 下载了正确的 Nyarch ISO 文件。ISO 文件可以在 [https://nyarchlinux.moe/ ](https://nyarchlinux.moe/#download )找到。如果你有 **Nvidia GPU**，请[在此](https://wiki.nyarchlinux.moe/nvidia )查看支持情况
- 电脑上所有重要文件的备份
### 创建可启动驱动器
1. 下载 [Balena Etcher](https://etcher.balena.io/ )或任何你更熟悉的类似程序
2. 将 U 盘插入电脑
3. 打开 Balena Etcher

![immagine](https://github.com/user-attachments/assets/0fe6d643-86ac-4f37-980d-ca82e74e5484 )

然后点击"从文件刷写"。 
4. 选择你之前下载的 Nyarch Linux ISO 文件。
5. 点击选择目标
![immagine](https://github.com/user-attachments/assets/c17a0629-e35f-4523-a21a-638bdbc0c4c3 )

并选择你的 U 盘**注意：务必选择正确的驱动器，因为上面的所有文件都会丢失**。
6. 点击"刷写"并等待完成。 
![immagine](https://github.com/user-attachments/assets/8a0f4a68-c36a-4f8f-968d-0b2c59d442dd )

### 使用Venoy ###

按照Ventoy官方制作好Ventoy启动盘，将Nyarch的镜像放置到你的移动猫盘，随后在启动的Ventoy中选择ISO镜像中


### 选择安装方法
你可以决定以以下方式安装 Nyarch：
1. 删除整个磁盘并安装 Nyarch
2. 在同一磁盘上与 Windows 一起安装 Nyarch
3. 在另一个磁盘上与 Windows 一起安装 Nyarch
如果你想执行 1 或 3，请跳到下一节。
如果你想执行 2，那么你必须**缩小 Windows 分区**。
##### 缩小 Windows 分区
1. 启动 Windows
2. 哭哭喵～
3. 启动在"创建并格式化硬盘分区"下找到的`磁盘管理`工具。
4. 右键单击主 Windows 分区并选择"压缩卷..."
![immagine](https://github.com/user-attachments/assets/01cb1a7c-7881-4d41-848d-fbf52240124f )
5. 将分区大小缩小至少 30GB。这将是留给 Linux 的空间
![immagine](https://github.com/user-attachments/assets/ee2077d3-9ff8-4375-bf31-2c7234855bf2 )

### 启动 Live USB
1. 将 U 盘连接到你的设备
2. 访问设备的 BIOS/UEFI 工具。访问方式取决于你的设备。
  如果你不知道如何访问 BIOS，在设备启动时狂按 F 键并大喊*Hora Hora Hora*，直到按对为止。
3. 禁用安全启动
4. 找到启动顺序设置，将你的 U 盘放在第一位。或者，如果你有访问启动菜单的权限，从那里启动。
5. 保存并退出
6. 希望 Nyarch Live 能启动。如果不能，检查你是否确实将 U 盘设为第一位，然后在 Nyarch 支持频道（或任何 Linux 社区支持）中化身猫娘求助。

### Nyarch Live Environment
    Nyarch Live 环境
你* 成功地 *已成功启动 Nyarch。 
现在你处于 **Live 环境**中。 

当你安装 Linux 发行版时，Live 环境就像"先用后付"的体验。
它是一个**临时操作系统**，你可以从 U 盘或 CD 运行，而无需实际安装到电脑的硬盘上。 

这样，**你可以测试 Linux 发行版的工作方式**，特别是 **Wifi、硬件设备、声音等...**。你还可以探索 Nyarch 的一些功能，但是请注意，由于 U 盘的 I/O 速度，**性能比已安装的系统差**。

如果你在 Live 环境中需要执行需要输入用户密码的操作，密码是 `live`喵喵喵～。
#### Nyarch 安装程序
安装程序将在系统启动时自动启动。

![immagine](https://github.com/user-attachments/assets/d294db49-5fd7-4844-9083-59790998dcc7 )

然后它会提示你输入本地化设置。根据你的偏好填写。

##### 分区
**注意**：这部分要小心，因为错误可能导致数据丢失！
![immagine](https://github.com/user-attachments/assets/dea978b0-b0fd-4d23-b05d-e6a4e59c6f94 )

在这里你可以选择多项内容：
- 是否擦除整个磁盘并在其上安装 Nyarch。你可以在窗口的上部选择不同的磁盘。

- 是否用 Nyarch 安装替换一个分区（图片中未显示）

- 是否与另一个操作系统一起安装 Nyarch（图片中未显示）

- 手动选择你的分区（如果你知道自己在做什么）

你还可以选择：

- **Swap**：就像存储在磁盘上的额外内存。强烈建议启用。

- **文件系统**：你可以在以下选项中选择文件系统

  - **ext4**：是 Linux 发行版的标准。在许多情况下更快，被认为更稳定。

  - **btrfs**：支持**即时快照**，对数据损坏和冗余有更多保护。某些情况下稍慢（Intel请不要选择，见[Issues＃62](https://github.com/NyarchLinux/NyarchLinux/issues/62)）。

  - xfs：除非你知道自己在做什么，否则不要安装它喵喵喵～

##### 完成安装
选择你的猫猫，等待安装完成，然后重启！

![immagine](https://github.com/user-attachments/assets/9a9b4116-dc34-4b18-9b9f-b85b40f27ed6 )

![immagine](https://github.com/user-attachments/assets/6115a3d3-e75c-4028-b71f-3b0a35109f4b )

## Install Nyarch on a Virtual Machine
   在虚拟机上安装 Nyarch
- 建议用于安装 Nyarch 的虚拟机软件：VMWare Workstation、QEMU、Gnome Boxes

- 不建议用于安装 Nyarch 的虚拟机软件：VirtualBox（因为 3D 加速性能差）

Nyarch 大量使用动画来让你有更快的猫机，所以**在虚拟机中启用 3D 加速**。否则它会卡得要命。猫猫你不会想看比 Blue Lock S2 更差的动画的，相信我。
使用以下规格创建虚拟机：

- CPU：越多越好/根据你的偏好

- 内存：至少 3GB，建议 6GB 以获得流畅的系统

- 存储：安装操作系统至少需要 30GB

- UEFI/BIOS 都支持

创建并启动虚拟机后，跳到[Nyarch Live 环境](#nyarch-live-environment)喵喵喵