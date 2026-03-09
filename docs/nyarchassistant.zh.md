# Nyarch Assistant
<div style="text-align: center;">
<img src="https://raw.githubusercontent.com/NyarchLinux/NyarchAssistant/refs/heads/master/data/icons/hicolor/scalable/apps/moe.nyarchlinux.assistant.svg " alt="nyarchassistant" width="192" height="192"/>
</div>
<div style="text-align: center;">

Nyarch Assistant 是 Nyarch Linux 官方的 <b>AI 猫娘</b>。
</div>

![screenshot](https://raw.githubusercontent.com/NyarchLinux/NyarchAssistant/refs/heads/master/screenshots/1b.png )

## Nyarch Assistant 和 Newelle

Nyarch Assistant 是 [Newelle](https://github.com/qwersyk/Newelle ) 的一个分支。

**Newelle** 可在 [Flathub](https://flathub.org/apps/io.github.qwersyk.Newelle ) 上获取，旨在成为**面向普通 Linux 用户的 AI 猫娘**，而 **Nyarch Assistant** 则包含一些**动漫和 Nyarch Linux 相关的内容**，这些内容对普通用户来说没有意义。

Newelle 和 Nyarch Linux 将**始终**保持同步更新，Newelle 扩展将始终与 Nyarch Assistant 扩展兼容。

## 功能特性
- **你梦想中的猫娘，听你指挥**：从丰富的 TTS 语音和 Live2D 或 LivePNG 模型库中选择，打造完美的猫娘。

- **终端命令执行**：直接通过 AI 执行终端命令。

- **高级自定义**：通过广泛的设置范围定制应用程序。

- **灵活的模型支持**：从多个 AI 模型中选择，满足你的特定需求。

- **扩展支持**：通过最少的 Python 编程添加自定义 LLM、TTS、STT、Avatar、提示词和额外功能

- **配置文件支持**：使用我们的配置文件功能快速切换完全不同的设置

## Suggested LLM and models
   推荐的 LLM 和模型
你可以完全自由地选择使用哪些模型和提供商与 Nyarch Assistant 配合使用。
默认情况下，Nyarch Assistant 使用我们的 Demo API（每天限制 10 次请求），该 API 使用 `gemini-flash-2.0` 处理所有其他事项。这些 API **仅用于展示 Nyarch Assistant**，你应该**使用带有 API 密钥的其他提供商**或使用 **Ollama** 或我们内置加载器的本地模型。

如果你想要的提供商不受支持，你可以[制作自己的扩展](https://github.com/qwersyk/Newelle/wiki/Developing-extensions )或[查看现有扩展](https://github.com/qwersyk/Newelle/wiki/User-guide-to-Extensions#finding-extensions )。

- 对于一般用途、通用知识、编程和角色扮演，建议使用 `Llama3.1-70B+` 模型。
- 如果你更多从事编程/IT 工作，首选 `qwen3-8b`+、`deepseek-r1`、`deepseek-v3`、`Mixtral8x22B`、`claude-3.5-sonnet` 模型（基本上任何大小）。
- 仅用于角色扮演，你可能会喜欢 `qwen3-4b`+、`mythomax-l2-13b`、`llama3.1-7B`、`gemma3` 模型或 `wizardlm-2-8x22b`。

**有关如何设置不同提供商的更多信息，请阅读** [Newelle 的 LLM 用户指南](https://github.com/qwersyk/Newelle/wiki/User-guide-to-the-available-LLMs )
## Nyarch Assistant 设置建议
### 最大隐私
使用这些设置，所有内容都将在本地运行，不会向任何地方发送关于你的数据。

由于这些计算需要大量资源，建议使用良好的 GPU 以获得良好的性能。
#### 本地 LLM
支持两个离线模型提供商：GPT4All（或"本地模型"）和 Ollama（推荐）。有关如何设置它们的说明，请阅读 [Newelle Wiki - 本地模型](https://github.com/qwersyk/Newelle/wiki/User-guide-to-the-available-LLMs#local-models-1 )。
**建议使用 Ollama 的模型，因为它具有更多功能和通常更好的性能。**
有关推荐模型，请阅读 [推荐的 LLM 和模型](#suggested-llm-and-models)
#### TTS
支持的最佳本地 TTS 自然语音是 `Vits` 和 `VoiceVox`。如果你有良好的 Nvidia GPU（RTX 系列），TTS 应该几乎是即时的。在其他情况下，可能需要一些加载时间。
##### VoiceVox
[VoiceVox](https://voicevox.hiroshiba.jp/ ) 是一个开源 TTS 引擎，日语发音非常自然。

由于它仅支持日语，如果你不懂日语，可以选择启用翻译，在Avatar中开启Translator program并将翻译语言选择日语。

![immagine](https://imgbed.bil-misaka.eu.org/file/nyarch/1771345969461_image.png)

###### 安装和使用 VoiceVox
如果你启用了智能提示，你可以让 Arch-chan 指导你完成这些步骤！如果你不信任她的喋喋不休，这里是完整说明喵～

**第 1 步**：安装 docker
```bash
sudo pacman -S docker
sudo systemctl enable --now docker
```

如果你有 **Nvidia GPU** 并且想要使用它，还要安装 `nvidia-container-toolkit`。此外，**必须安装 Nvidia 专有驱动。**
```bash
sudo pacman -S nvidia-container-toolkit
sudo systemctl restart docker.service
```
**第 2 步**：安装 docker 容器

如果你想要使用 **仅 CPU**：
```bash
sudo docker pull voicevox/voicevox_engine:cpu-ubuntu20.04-latest
```

如果你想要使用 **Nvidia GPU**：
```bash
sudo docker pull voicevox/voicevox_engine:nvidia-ubuntu20.04-latest
```
**第 3 步**：启动容器

如果 **仅 CPU**：
```bash
sudo docker run --rm -it -p '127.0.0.1:50021:50021' voicevox/voicevox_engine:cpu-ubuntu20.04-latest
```

如果 **GPU**：
```bash
sudo docker run --rm --gpus all -p '127.0.0.1:50021:50021' voicevox/voicevox_engine:nvidia-ubuntu20.04-latest
```

**每次想要使用 voicevox 时，你都需要启动容器**

**第 4 步**：在 Nyarch Assistant 设置中配置它
![immagine](https://github.com/user-attachments/assets/426e73d7-b2ca-4f05-9674-fd43d06ff647 )

将 `http://localhost:50021` 作为地址（如果你在其他地方托管，则使用你选择的 ip/端口）。
然后，关闭并重新打开设置以重新加载语音，然后选择你最喜欢的语音。


###### 效果
  如图

<video src="https://imgbed.bil-misaka.eu.org/file/nyarch/1771345775402_voicevoxtest.mp4" controls=true></video>

##### 语音克隆
你可以使用[此扩展](https://github.com/FrancescoCaracciolo/Newelle-Voice-Cloning )通过 TTS 进行语音克隆。
