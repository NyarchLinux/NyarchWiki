# Nyarch Assistant
<div style="text-align: center;">
<img src="https://raw.githubusercontent.com/NyarchLinux/NyarchAssistant/refs/heads/master/data/icons/hicolor/scalable/apps/moe.nyarchlinux.assistant.svg" alt="nyarchassistant" width="192" height="192"/>
</div>
<div style="text-align: center;">

Nyarch Assistant は Nyarch Linux の公式 <b>AI Waifu Assistantです</b>。
</div>

![screenshot](https://raw.githubusercontent.com/NyarchLinux/NyarchAssistant/refs/heads/master/screenshots/1b.png)

## Nyarch Assistant と Newelle

Nyarch Assistant は [Newelle](https://github.com/qwersyk/Newelle) のフォークです。

Newelle は [Flathub](https://flathub.org/apps/io.github.qwersyk.Newelle) で利用可能で、一般的な Linux ユーザー向けの AI チャットボットとされていますが、Nyarch Assistant には一般ユーザーには意味を成さないアニメや Nyarch Linux 関連の要素がいくつかあります。

Newelle と Nyarch Linux は常に相互に最新の状態であり、Newelle 拡張機能は常に Nyarch Assistant 拡張機能と互換性があります。

## 機能

- **あなたの夢のワイフが指示に従う**: 豊富なTTS音声ライブラリとLive2DまたはLivePNGモデルから選択し、完璧なバーチャルコンパニオンを作成できます。

- **ターミナルコマンド実行**: AIを通じてターミナルコマンドを直接実行します。

- **高度なカスタマイズ**: 幅広い設定でアプリケーションをカスタマイズできます。

- **柔軟なモデルサポート**: 複数のAIモデルから選択し、特定のニーズに合わせることができます。

- **拡張機能サポート**: カスタムLLM、TTS、STT、アバター、プロンプト、および追加機能を最小限のPythonプログラミングで追加します。

- **プロフィールサポート**: プロフィール機能を使用して、全く異なる設定に素早く切り替えることができます。
  
## 推奨されるLLMとモデル

Nyarch Assistant を使用するモデルやプロバイダーは、自由に選択できます。

デフォルトでは、Nyarch Assistant は当社のデモ API（1日 10req に制限）を使用し、他のすべてには `gemini-flash-2.0` を使用します。これらのAPIはNyarch Assistantを紹介するだけのものであり、APIキーを持つ別のプロバイダーを使用するか、Ollamaまたは当社の組み込みローダーを使用したローカルモデルを使用する必要があります。

ご希望のプロバイダーがサポートされていない場合は、[拡張機能を作成](https://github.com/qwersyk/Newelle/wiki/Developing-extensions) または[既存の拡張機能を確認](https://github.com/qwersyk/Newelle/wiki/User-guide-to-Extensions#finding-extensions)を行ってください。

- 一般的な目的、一般的な知識、コーディング、ロールプレイのために、`Llama3.1-70B+`モデルが推奨されます。
- プログラミングやITの作業が多い場合は、`qwen3-8b`+、`deepseek-r1`、`deepseek-v3`、`Mixtral8x22B`、`claude-3.5-sonnet` モデル（基本的に任意のサイズ）が推奨されます。
- ロールプレイのみの場合、`qwen3-4b`+、`mythomax-l2-13b`、`llama3.1-7B`、`gemma3`モデル、または`wizardlm-2-8x22b` をご好みになるかもしれません。

異なるプロバイダーの設定方法の詳細については、[Newelle の LLM ユーザーガイド](https://github.com/qwersyk/Newelle/wiki/User-guide-to-the-available-LLMs) をご覧ください。
## Nyarch Assistant 設定の提案
### 最大限のプライバシー
これらの設定では、すべてがローカルで実行され、あなたに関するデータはどこにも送信されません。

これらの計算には相当量のリソースが必要であるため、優れたパフォーマンスを発揮するには適切なGPUが推奨されます。

#### ローカルLLM
2つのオフラインモデルプロバイダーがサポートされています：GPT4All（または「ローカルモデル」）とOllama（推奨）。設定方法の手順については、[Newelle Wiki - Local Models](https://github.com/qwersyk/Newelle/wiki/User-guide-to-the-available-LLMs#local-models-1)をご覧ください。

**Ollama を使用したモデルを使用することが推奨されます。これは、より多くのファチュアがあり、一般的に性能が優れているからです。**

提案されたモデルについては、[推奨されるLLMとモデル](#推奨されるllmとモデル) をご覧ください。
#### TTS

自然な音声でサポートされているローカルTTSは、`Vits` と `VoiceVox` が最もサポートされています。もしNvidiaの良いGPU（RTXシリーズ）をお持ちであれば、TTSはほぼ瞬時に実行できるはずです。その他の場合、ロード時間が必要になることがあります。

##### VoiceVox

[VoiceVox](https://voicevox.hiroshiba.jp/) は、オープンソースのTTSエンジンで、日本語にとって非常に自然な音です。

日本語のみ対応しているため、日本語が分からない場合は、翻訳を有効にし、Avatarで翻訳プログラムを有効にし、翻訳言語として日本語を選択できます。(このWikiを日本語で読んでる人はほとんどが日本人だろうから、多分ここは必要ないけどね笑)

![immagine](https://imgbed.bil-misaka.eu.org/file/nyarch/1771345969461_image.png)

###### VoiceVox のインストールと使用

Smartプロンプトが有効になっている場合、Arch-chanにこれらの手順を案内してもらうことができます！もし彼女のお喋りを信用できない場合は、この指示に従ってください。

**Step 1**: Dockerのインストール
```bash
sudo pacman -S docker
sudo systemctl enable --now docker
```

もし **Nvidia GPU** をお持ちで、使用したい場合は、`nvidia-container-toolkit` もインストールしてください。また、**Nvidia の専用ドライバーをインストールする必要があります。**
```bash
sudo pacman -S nvidia-container-toolkit
sudo systemctl restart docker.service
```
**Step 2**: Docker コンテナのインストール

**CPUのみ** を使用したい場合:
```bash
sudo docker pull voicevox/voicevox_engine:cpu-ubuntu20.04-latest
```

**Nvidia GPU** を使用したい場合:
```bash
sudo docker pull voicevox/voicevox_engine:nvidia-ubuntu20.04-latest
```
**Step 3**: コンテナを開始する

**CPU上** の場合：
```bash
sudo docker run --rm -it -p '127.0.0.1:50021:50021' voicevox/voicevox_engine:cpu-ubuntu20.04-latest
```

**GPU上** の場合：
```bash
sudo docker run --rm --gpus all -p '127.0.0.1:50021:50021' voicevox/voicevox_engine:nvidia-ubuntu20.04-latest
```

**Voicevox を使用したいときは、毎回コンテナを起動しなければなりません。**

**Step 4**: Nyarch Assistant の設定を構成する
![immagine](https://github.com/user-attachments/assets/426e73d7-b2ca-4f05-9674-fd43d06ff647)

###### 効果

<video src="https://imgbed.bil-misaka.eu.org/file/nyarch/1771345775402_voicevoxtest.mp4" controls=true></video>

エンドポイントとして `http://localhost:50021` を設定してください（別の場所でホストする場合は、選択した IP/ポートにしてください）。

次に、設定を閉じて再度開き、音声を再読み込みし、好きな音声を選択してください。

##### 音声クローン作成

[この拡張機能](https://github.com/FrancescoCaracciolo/Newelle-Voice-Cloning) を使用して、TTSで音声クローンを実行できます。
