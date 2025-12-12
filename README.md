<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<!-- PROJECT LOGO -->
<a id="readme-top"></a>
<div align="center">
  <h1 align="center">Windows AI Wheelhouse</h1>

<img src="https://github.com/user-attachments/assets/3d63f337-b913-4246-9bd0-d0bfc1c871e2" alt="Windows AI Wheelhouse logo">

  <p align="center">
    面向 Windows 平台的 AI 预编译 Python 轮子合集
    <br />
    <br />
    <strong>⏱️ 最后自动更新（UTC）：<!-- START_LAST_UPDATED -->2025-12-12T02:52:39.442022+00:00<!-- END_LAST_UPDATED --></strong>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary><strong>📑 目录</strong></summary>
  <ol>
    <li><a href="#-项目愿景">项目愿景</a></li>
    <li><a href="#-致敬与启发">致敬与启发</a></li>
    <li>
      <a href="#-快速开始">快速开始</a>
      <ul>
        <li><a href="#环境准备">环境准备</a></li>
        <li><a href="#安装示例">安装示例</a></li>
      </ul>
    </li>
    <li><a href="#-cxx11-abi-说明">CXX11 ABI 说明</a></li>
    <li><a href="#-可用轮子">可用轮子</a>
      <ul>
        <li><a href="#pytorch">PyTorch</a></li>
        <li><a href="#torchaudio">Torchaudio</a></li>
        <li><a href="#️-flash-attention">Flash Attention</a></li>
        <li><a href="#️-xformers">xformers</a></li>
        <li><a href="#️-sageattention">SageAttention</a></li>
        <li><a href="#️-sageattention-22-sageattention2">SageAttention 2.2</a></li>
        <li><a href="#️-sageattention3">SageAttention 3</a></li>        
        <li><a href="#️-spargeattn">SpargeAttn</a></li>
        <li><a href="#️-nunchaku">Nunchaku</a></li>
        <li><a href="#️-natten">NATTEN</a></li>
        <li><a href="#️-tritonwindows-fork">Triton</a></li>
        <li><a href="#️-bitsandbytes">bitsandbytes</a></li>
        <li><a href="#️-radialattention-for-comfyui">RadialAttention</a></li>
      </ul>
    </li>
    <li><a href="#-贡献-contributing">贡献</a></li>
    <li><a href="#-致谢-acknowledgments">致谢</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
<a id="-项目愿景"></a>
## 🟦 项目愿景

本项目作为一个**学习和实践的项目**，在延续 wildminder [AI-windows-whl](https://github.com/wildminder/AI-windows-whl) 优秀理念的基础上，尝试通过以下方式提供一些补充：

- 🤖 **自动化更新**：通过 GitHub Actions 定期自动抓取和更新 wheel 链接
- 📊 **多源聚合**：整合来自不同社区贡献者的预编译资源
- 📖 **结构化呈现**：按版本和依赖关系分类展示，便于查找
- 🔍 **智能解析**：自动识别版本号、CXX11 ABI 等元数据

这些尝试完全出于个人学习目的，也希望能够为社区提供一个不同角度的资讯汇整。如果本项目能为更多 Windows AI 爱好者节省一点点时间，让大家能够更专注于创作和探索，那便这个项目最大的荣幸。

<a id="-致敬与启发"></a>
## 🟦 致敬与启发

本项目深受 wildminder [AI-windows-whl](https://github.com/wildminder/AI-windows-whl) 项目的启发，我们旨在延续其精神，为更广泛的 Windows AI 社区提供稳定可靠的预编译资源。

特别感谢 [Eddy](https://github.com/eddyhhlure1Eddy) 孜孜不倦的精神和无私的指导。从接触他的 [Palingenesis 模型](https://huggingface.co/eddy1111111/WAN22.XX_Palingenesis) 开始，是他的热情感召，让我这样一个影视从业者，能够开始尝试撰写自己需要的代码。

### 我的 Palingenesis AIGC 作品
使用 Eddy 的 Palingenesis 模型创作的 MV：

<div align="center">
  <a href="https://www.youtube.com/watch?v=WdxTmXfplho">
    <img src="https://img.youtube.com/vi/WdxTmXfplho/maxresdefault.jpg" alt="My First AIGC MV" style="width:80%; max-width:720px;">
  </a>
  <p><em>点击图片观看视频</em></p>
</div>

<!-- GETTING STARTED -->
<a id="-快速开始"></a>
## 🟦 快速开始

按照以下步骤即可使用仓库中的 wheel：

<a id="环境准备"></a>
### 环境准备

1.  **Windows 版 Python**：请确认本地安装的 Python 版本与 PyTorch 支持范围一致（当前为 **3.9 - 3.14**）。可前往 [Python 官网](https://www.python.org/downloads/windows/) 下载。


<a id="安装示例"></a>
### 安装示例

通过 `pip` 搭配 `.whl` 直链进行安装，建议给 URL 加上引号，防止 shell 解析问题。

```sh
# 以安装特定 flash-attention 轮子为例
pip install "https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4.post1+cu128torch2.7.0cxx11abiFALSE-cp312-cp312-win_amd64.whl"
```

> [!TIP]
> 在下方 <a href="#-可用轮子">可用轮子</a> 区域按 Python/PyTorch/CUDA 版本找到匹配行，然后复制下载链接放入 `pip install` 命令即可。

<p align="right">(<a href="#readme-top">返回顶部</a>)</p>

<!-- CXX11 ABI GUIDE -->
<a id="-cxx11-abi-说明"></a>
## 🟦 CXX11 ABI 说明

部分表格包含 **CXX11 ABI** 列，这是 C++ 编译器的两种不兼容模式。表格中使用以下符号标注：

- **`✓`** 或 **`TRUE`**：启用 CXX11 ABI（新版，适用于新版 PyTorch，通常 2.7.0 及以上）
- **`✗`** 或 **`FALSE`**：禁用 CXX11 ABI（Pre-CXX11 ABI，旧版）
- **`—`**（横线或未标注）：未明确标注（大多数 Windows 用户应优先选择此版本）

> [!IMPORTANT]
> **PyTorch 和扩展库的 CXX11 ABI 必须一致**，否则会导致崩溃或链接错误。

### 如何检测你的 PyTorch 使用哪种 ABI？

运行以下 Python 代码：

```python
import torch
print(f"PyTorch 版本: {torch.__version__}")
print(f"CXX11 ABI: {torch._C._GLIBCXX_USE_CXX11_ABI}")
```

**结果解读**：
- **输出 `0` 或 `False`** → 使用 Pre-CXX11 ABI，选择 CXX11 ABI 列为 `—`、`✗` 或 `FALSE` 的 wheel
- **输出 `1` 或 `True`** → 使用 CXX11 ABI，选择 CXX11 ABI 列为 `✓` 或 `TRUE` 的 wheel

### 快速选择指南

**对于大多数 Windows 用户**（使用 PyTorch 官方版本）：

1. ✅ **优先选择** CXX11 ABI 列显示为 `—` 的 wheel（最兼容）
2. ✅ **次选** CXX11 ABI 列显示为 `✗` 或 `FALSE` 的 wheel（明确兼容）
3. ⚠️ **仅在确认后选择** CXX11 ABI 列显示为 `✓` 或 `TRUE` 的 wheel

> [!TIP]
> 如果不确定，优先选择未标注 CXX11 ABI（显示 `—`）的版本，这些版本通常与官方 PyTorch 兼容。

<p align="right">(<a href="#readme-top">返回顶部</a>)</p>

<!-- AVAILABLE WHEELS -->
<a id="-可用轮子"></a>
## 🟦 可用轮子

以下是当前收录的轮子

<a id="pytorch"></a>
### ⚙️ PyTorch
深度学习框架的基石，强烈建议优先通过官方渠道安装以确保兼容性。
*   **官方安装页面**： [https://pytorch.org/get-started/locally/](https://pytorch.org/get-started/locally/)

为了方便，在 Linux/WSL（NVIDIA GPU）环境下列出常用命令；其他配置（CPU、macOS、ROCm）请参考官网指引。

#### 稳定版（2.9.1）
多数用户推荐使用该版本

| CUDA Version | Pip Install Command                                                                                      |
|:-------------|:---------------------------------------------------------------------------------------------------------|
| **CUDA 13.0**  | `pip install torch torchvision --index-url https://download.pytorch.org/whl/cu130` |
| **CUDA 12.8**  | `pip install torch torchvision --index-url https://download.pytorch.org/whl/cu128` |
| **CUDA 12.6**  | `pip install torch torchvision --index-url https://download.pytorch.org/whl/cu126` |

<details>
  <summary>历史稳定版 2.7.1 / 2.8.0</summary>

##### 历史稳定版（2.8.0）  
| CUDA Version | Pip Install Command                                                              |
|:-------------|:---------------------------------------------------------------------------------|
| **CUDA 12.9**  | `pip install "torch>=2.8.0.dev,<2.9.0" torchvision --index-url https://download.pytorch.org/whl/cu129`           |
| **CUDA 12.8**  | `pip install "torch>=2.8.0.dev,<2.9.0" torchvision --index-url https://download.pytorch.org/whl/cu128`           |
| **CUDA 12.6**  | `pip install "torch>=2.8.0.dev,<2.9.0" torchvision --index-url https://download.pytorch.org/whl/cu126`           |

##### 历史稳定版（2.7.1）
| CUDA Version | Pip Install Command                                                                                      |
|:-------------|:---------------------------------------------------------------------------------------------------------|
| **CUDA 12.8**  | `pip install torch==2.7.1 torchvision==0.22.1 torchaudio==2.7.1 --index-url https://download.pytorch.org/whl/cu128` |
| **CUDA 12.6**  | `pip install torch==2.7.1 torchvision==0.22.1 torchaudio==2.7.1 --index-url https://download.pytorch.org/whl/cu126` |
| **CUDA 11.8**  | `pip install torch==2.7.1 torchvision==0.22.1 torchaudio==2.7.1 --index-url https://download.pytorch.org/whl/cu118` |
| **CPU only**   | `pip install torch==2.7.1 torchvision==0.22.1 torchaudio==2.7.1 --index-url https://download.pytorch.org/whl/cpu`      |

</details>

#### Nightly 版本
适合追新特性，但可能存在不稳定。

**PyTorch 2.10（Nightly）**
| CUDA Version | Pip Install Command                                                                                      |
|:-------------|:---------------------------------------------------------------------------------------------------------|
| **CUDA 13.0**  | `pip install --pre torch torchvision --index-url https://download.pytorch.org/whl/nightly/cu130` |
| **CUDA 12.8**  | `pip install --pre torch torchvision --index-url https://download.pytorch.org/whl/nightly/cu128` |
| **CUDA 12.6**  | `pip install --pre torch torchvision --index-url https://download.pytorch.org/whl/nightly/cu126` |

<hr />

<a id="torchaudio"></a>
### ⚙️ Torchaudio
PyTorch 官方音频处理库，提供音频 I/O、转换和特征提取等功能。
*   **官方仓库**： [https://github.com/pytorch/audio](https://github.com/pytorch/audio)
*   **预编译来源**： <!-- START_TORCHAUDIO_SOURCES -->[Wildminder](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)<!-- END_TORCHAUDIO_SOURCES -->

<details>
  <summary>展开已收录的 Torchaudio</summary>

<!-- START_TORCHAUDIO_TABLE -->
| Package Version | Python Ver | PyTorch Ver | CUDA Ver | CXX11 ABI | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `2.8.0a0` | `3.12` | `2.9.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/torchaudio-2.8.0a0%2Bcu128torch2.9.0cxx11abi1-cp312-cp312-win_amd64.whl) |
| `2.8.0a0` | `3.13` | `2.10.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/torchaudio-2.8.0a0%2Bcu130torch2.10.0cxx11abi1-cp313-cp313-win_amd64.whl) |
<!-- END_TORCHAUDIO_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-flash-attention"></a>
### ⚙️ Flash Attention
高性能注意力机制的先驱实现，通过分块计算和重计算策略大幅降低显存并提速。
*   **官方仓库**： [Dao-AILab/flash-attention](https://github.com/Dao-AILab/flash-attention)
*   **预编译来源**： <!-- START_FLASHATTENTION_SOURCES -->[Wildminder](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)、[lldacing](https://huggingface.co/lldacing/flash-attention-windows-wheel/tree/main)、[mjun0812](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases)、[BradPita](https://huggingface.co/BradPita/Win-AI-Wheelhouse/tree/main)、[Kijai](https://huggingface.co/Kijai/PrecompiledWheels/tree/main)<!-- END_FLASHATTENTION_SOURCES -->

<details>
  <summary>展开已收录的 Flash Attention</summary>
  
> **📝 CXX11 ABI 说明：**  
> - `✓` = 启用 CXX11 ABI（适用于新版 PyTorch，通常 2.7.0 及以上）
> - `✗` = 禁用 CXX11 ABI（Pre-CXX11 ABI，适用于旧版或特定配置）
> - `—` = 未明确标注（请根据您的 PyTorch 版本选择，或参考 [CXX11 ABI 说明](#-cxx11-abi-说明)）

<!-- START_FLASHATTENTION_TABLE -->
| Package Version | Python Ver | PyTorch Ver | CUDA Ver | CXX11 ABI | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `2.5.9` | `3.10` | `2.4` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.4-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `3.10` | `2.4` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.4-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `3.10` | `2.5` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.5-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `3.10` | `2.5` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.5-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `3.10` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.6-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `3.10` | `2.6` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.6-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `3.10` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.7-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `3.10` | `2.7` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.7-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `3.11` | `2.4` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.4-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `3.11` | `2.4` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.4-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `3.11` | `2.5` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.5-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `3.11` | `2.5` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.5-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `3.11` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.6-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `3.11` | `2.6` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.6-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `3.11` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.7-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `3.11` | `2.7` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.7-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `3.12` | `2.4` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.4-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `3.12` | `2.4` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.4-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `3.12` | `2.5` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.5-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `3.12` | `2.5` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.5-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `3.12` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.6-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `3.12` | `2.6` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.6-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `3.12` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.7-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `3.12` | `2.7` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.7-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `3.10` | `2.4` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.4-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `3.10` | `2.4` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.4-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `3.10` | `2.5` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.5-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `3.10` | `2.5` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.5-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `3.10` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.6-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `3.10` | `2.6` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.6-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `3.10` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.7-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `3.10` | `2.7` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.7-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `3.11` | `2.4` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.4-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `3.11` | `2.4` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.4-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `3.11` | `2.5` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.5-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `3.11` | `2.5` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.5-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `3.11` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.6-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `3.11` | `2.6` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.1/flash_attn-2.6.3%2Bcu126torch2.6-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `3.11` | `2.6` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.6-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `3.11` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.7-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `3.11` | `2.7` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.7-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `3.12` | `2.4` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.4-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `3.12` | `2.4` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.4-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `3.12` | `2.5` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.5-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `3.12` | `2.5` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.5-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `3.12` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.6-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `3.12` | `2.6` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.6-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `3.12` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.7-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `3.12` | `2.7` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.7-cp312-cp312-win_amd64.whl) |
| `2.7.0.post2` | `3.10` | `2.4.0` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.0.post2%2Bcu124torch2.4.0cxx11abiFALSE-cp310-cp310-win_amd64.whl) |
| `2.7.0.post2` | `3.10` | `2.4.1` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.0.post2%2Bcu124torch2.4.1cxx11abiFALSE-cp310-cp310-win_amd64.whl) |
| `2.7.0.post2` | `3.11` | `2.4.0` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.0.post2%2Bcu124torch2.4.0cxx11abiFALSE-cp311-cp311-win_amd64.whl) |
| `2.7.0.post2` | `3.11` | `2.4.1` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.0.post2%2Bcu124torch2.4.1cxx11abiFALSE-cp311-cp311-win_amd64.whl) |
| `2.7.0.post2` | `3.11` | `2.5.0` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.0.post2%2Bcu124torch2.5.0cxx11abiFALSE-cp311-cp311-win_amd64.whl) |
| `2.7.0.post2` | `3.11` | `2.5.1` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.0.post2%2Bcu124torch2.5.1cxx11abiFALSE-cp311-cp311-win_amd64.whl) |
| `2.7.0.post2` | `3.12` | `2.4.0` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.0.post2%2Bcu124torch2.4.0cxx11abiFALSE-cp312-cp312-win_amd64.whl) |
| `2.7.0.post2` | `3.12` | `2.4.1` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.0.post2%2Bcu124torch2.4.1cxx11abiFALSE-cp312-cp312-win_amd64.whl) |
| `2.7.0.post2` | `3.12` | `2.5.0` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.0.post2%2Bcu124torch2.5.0cxx11abiFALSE-cp312-cp312-win_amd64.whl) |
| `2.7.0.post2` | `3.12` | `2.5.1` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.0.post2%2Bcu124torch2.5.1cxx11abiFALSE-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `3.10` | `2.4` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.4-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `3.10` | `2.5` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.5-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `3.10` | `2.5` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.5-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `3.10` | `2.5.1` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu124torch2.5.1cxx11abiFALSE-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `3.10` | `2.6.0` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu124torch2.6.0cxx11abiFALSE-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `3.10` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.6-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `3.10` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.6-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `3.10` | `2.6.0` | `12.6` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu126torch2.6.0cxx11abiFALSE-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `3.10` | `2.6` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.6-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `3.10` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.7-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `3.10` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.7-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `3.10` | `2.7.0` | `12.8` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4.post1%2Bcu128torch2.7.0cxx11abiFALSE-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `3.10` | `2.7` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.7.4%2Bcu128torch2.7-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `3.10` | `2.8` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.8-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `3.10` | `2.8.0` | `12.8` | ✓ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4.post1%2Bcu128torch2.8.0cxx11abiTRUE-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `3.10` | `2.8` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.7.4%2Bcu128torch2.8-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `3.10` | `2.9` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.9-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `3.10` | `2.9` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.9-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `3.11` | `2.5` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.5-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `3.11` | `2.5` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.5-cp311-cp311-win_amd64.whl) |
| `2.7.4` | `3.11` | `2.6.0` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu124torch2.6.0cxx11abiFALSE-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `3.11` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.6-cp311-cp311-win_amd64.whl) |
| `2.7.4` | `3.11` | `2.6.0` | `12.6` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu126torch2.6.0cxx11abiFALSE-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `3.11` | `2.6` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.6-cp311-cp311-win_amd64.whl) |
| `2.7.4` | `3.11` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.7-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `3.11` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.7-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `3.11` | `2.7` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.7-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `3.11` | `2.7.0` | `12.8` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4.post1%2Bcu128torch2.7.0cxx11abiFALSE-cp311-cp311-win_amd64.whl) |
| `2.7.4` | `3.11` | `2.7` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.7.4%2Bcu128torch2.7-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `3.11` | `2.8` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.8-cp311-cp311-win_amd64.whl) |
| `2.7.4` | `3.11` | `2.8` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.7.4%2Bcu128torch2.8-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `3.11` | `2.9` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.9-cp311-cp311-win_amd64.whl) |
| `2.7.4` | `3.12` | `2.4` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.4-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `3.12` | `2.5` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.5-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `3.12` | `2.6.0` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu124torch2.6.0cxx11abiFALSE-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `3.12` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.6-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `3.12` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.6-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `3.12` | `2.6.0` | `12.6` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu126torch2.6.0cxx11abiFALSE-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `3.12` | `2.6` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.6-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `3.12` | `2.6.0` | `12.8` | ✗ | Kijai | [Link](https://huggingface.co/Kijai/PrecompiledWheels/blob/main/flash_attn-2.7.4%2Bcu128torch2.6.0cxx11abiFALSE-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `3.12` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.7-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `3.12` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.7-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `3.12` | `2.7` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.7-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `3.12` | `2.7.0` | `12.8` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4.post1%2Bcu128torch2.7.0cxx11abiFALSE-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `3.12` | `2.7` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.7.4%2Bcu128torch2.7-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `3.12` | `2.8` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.8-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `3.12` | `2.8.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.7.4.post1%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `3.12` | `2.8` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.7.4%2Bcu128torch2.8-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `3.12` | `2.9` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.9-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `3.12` | `2.9` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.9-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `3.13` | `2.6` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.6-cp313-cp313-win_amd64.whl) |
| `2.7.4.post1` | `3.13` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.7-cp313-cp313-win_amd64.whl) |
| `2.7.4.post1` | `3.13` | `2.7` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.7-cp313-cp313-win_amd64.whl) |
| `2.7.4.post1` | `3.13` | `2.8` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.8-cp313-cp313-win_amd64.whl) |
| `2.7.4.post1` | `3.13` | `2.8` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.8-cp313-cp313-win_amd64.whl) |
| `2.7.4.post1` | `3.13` | `2.9` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.9-cp313-cp313-win_amd64.whl) |
| `2.7.4.post1` | `3.13` | `2.9` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.9-cp313-cp313-win_amd64.whl) |
| `2.8.0.post2` | `3.12` | `2.8.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.0.post2%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.1` | `3.12` | `2.8.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.1%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.2` | `3.10` | `2.7` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.8.2%2Bcu128torch2.7-cp310-cp310-win_amd64.whl) |
| `2.8.2` | `3.10` | `2.8` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.8.2%2Bcu128torch2.8-cp310-cp310-win_amd64.whl) |
| `2.8.2` | `3.11` | `2.7` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.8.2%2Bcu128torch2.7-cp311-cp311-win_amd64.whl) |
| `2.8.2` | `3.11` | `2.8` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.8.2%2Bcu128torch2.8-cp311-cp311-win_amd64.whl) |
| `2.8.2` | `3.12` | `2.7` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.8.2%2Bcu128torch2.7-cp312-cp312-win_amd64.whl) |
| `2.8.2` | `3.12` | `2.8.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.2%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.2` | `3.12` | `2.8` | `12.8` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.8.2%2Bcu128torch2.8-cp312-cp312-win_amd64.whl) |
| `2.8.2` | `3.12` | `2.9.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.2%2Bcu128torch2.9.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.2` | `3.13` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.12/flash_attn-2.8.2%2Bcu124torch2.6-cp313-cp313-win_amd64.whl) |
| `2.8.2` | `3.13` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.12/flash_attn-2.8.2%2Bcu124torch2.7-cp313-cp313-win_amd64.whl) |
| `2.8.2` | `3.13` | `2.7` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.12/flash_attn-2.8.2%2Bcu126torch2.7-cp313-cp313-win_amd64.whl) |
| `2.8.2` | `3.13` | `2.8` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.12/flash_attn-2.8.2%2Bcu124torch2.8-cp313-cp313-win_amd64.whl) |
| `2.8.2` | `3.13` | `2.8` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.12/flash_attn-2.8.2%2Bcu126torch2.8-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.10` | `2.5` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.5-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `3.10` | `2.5` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.5-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `3.10` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.6-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `3.10` | `2.6` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.6-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `3.10` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.7-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `3.10` | `2.7` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.7-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `3.10` | `2.8` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.8-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `3.10` | `2.8` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.8-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `3.10` | `2.9` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.9-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `3.10` | `2.9` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.9-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `3.11` | `2.5` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.5-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `3.11` | `2.5` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.5-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `3.11` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.6-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `3.11` | `2.6` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.6-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `3.11` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.7-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `3.11` | `2.7` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.7-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `3.11` | `2.8` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.8-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `3.11` | `2.8` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.8-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `3.11` | `2.9` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.9-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `3.11` | `2.9` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.15/flash_attn-2.8.3%2Bcu126torch2.9-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `3.11` | `2.9` | `13.0` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu130torch2.9-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.5` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.5-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.5` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.5-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.6-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.6` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.6-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.7-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.7` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.7-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.8` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.8-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.8` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.8-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.8.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.9` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.9-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.9` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.15/flash_attn-2.8.3%2Bcu126torch2.9-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.9.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu128torch2.9.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.9.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.9.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.9.1` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.9.1cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.10.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.10.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.6` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.6-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.6` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.6-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.7` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.7-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.7` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.7-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.8` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.8-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.8` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.8-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.8.0` | `12.8` | ✓ | BradPita | [Link](https://huggingface.co/BradPita/Win-AI-Wheelhouse/blob/main/flash_attn-2.8.3%2Bcu128torch2.8.0cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.9` | `12.4` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.9-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.9` | `12.6` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.15/flash_attn-2.8.3%2Bcu126torch2.9-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.9.0` | `12.9` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu129torch2.9.0cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.9.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.9.0cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.9` | `13.0` | — | mjun0812 | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu130torch2.9-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.9.1` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu128torch2.9.1cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.9.1` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.9.1cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.10.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu128torch2.10.0cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.10.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.10.0cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
<!-- END_FLASHATTENTION_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-xformers"></a>
### ⚙️ xformers
Meta 开发的内存高效注意力库，提供多种优化算子，广泛应用于图像生成和 LLM 推理。
*   **官方仓库**： [facebookresearch/xformers](https://github.com/facebookresearch/xformers/releases)
*   **预编译来源**： <!-- START_XFORMERS_SOURCES -->[PyTorch](https://download.pytorch.org/whl/xformers/)、[Wildminder](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)<!-- END_XFORMERS_SOURCES -->
> [!NOTE]
> 安装 PyTorch 后通常可以直接 `pip install xformers`。若失败，可在预编译来源中寻找与环境匹配的 wheel。

ABI3 版本可兼容 Python 3.9-3.12。

<details>
  <summary>展开已收录的 xformers</summary>

<!-- START_XFORMERS_TABLE -->
| Package Version | Python Ver | PyTorch Ver | CUDA Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|
| `0.0.29.post3` | `3.9` | `2.5-2.6` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp39-cp39-win_amd64.whl) |
| `0.0.29.post3` | `3.10` | `2.5-2.6` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp310-cp310-win_amd64.whl) |
| `0.0.29.post3` | `3.11` | `2.5-2.6` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp311-cp311-win_amd64.whl) |
| `0.0.29.post3` | `3.12` | `2.5-2.6` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp312-cp312-win_amd64.whl) |
| `0.0.30` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.30-cp39-cp39-win_amd64.whl) |
| `0.0.30` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp39-cp39-win_amd64.whl) |
| `0.0.30` | `3.10` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.30-cp310-cp310-win_amd64.whl) |
| `0.0.30` | `3.10` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp310-cp310-win_amd64.whl) |
| `0.0.30` | `3.11` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.30-cp311-cp311-win_amd64.whl) |
| `0.0.30` | `3.11` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp311-cp311-win_amd64.whl) |
| `0.0.30` | `3.12` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.30-cp312-cp312-win_amd64.whl) |
| `0.0.30` | `3.12` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp312-cp312-win_amd64.whl) |
| `0.0.31` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.31-cp39-abi3-win_amd64.whl) |
| `0.0.31.post1` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.31.post1-cp39-abi3-win_amd64.whl) |
| `0.0.31` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.31-cp39-abi3-win_amd64.whl) |
| `0.0.31.post1` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.31.post1-cp39-abi3-win_amd64.whl) |
| `0.0.32.post1` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.32.post1-cp39-abi3-win_amd64.whl) |
| `0.0.32.post2` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.32.post2-cp39-abi3-win_amd64.whl) |
| `0.0.32.post1` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.32.post1-cp39-abi3-win_amd64.whl) |
| `0.0.32.post2` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.32.post2-cp39-abi3-win_amd64.whl) |
| `0.0.32.post1` | `3.9` | `2.8-2.9` | `12.9` | PyTorch | [Link](https://download.pytorch.org/whl/cu129/xformers-0.0.32.post1-cp39-abi3-win_amd64.whl) |
| `0.0.32.post2` | `3.9` | `2.8-2.9` | `12.9` | PyTorch | [Link](https://download.pytorch.org/whl/cu129/xformers-0.0.32.post2-cp39-abi3-win_amd64.whl) |
| `0.0.33` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.33-cp39-abi3-win_amd64.whl) |
| `0.0.33.post1` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.33.post1-cp39-abi3-win_amd64.whl) |
| `0.0.33.post2` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.33.post2-cp39-abi3-win_amd64.whl) |
| `0.0.33` | `3.9` | `2.9+` | `13.0` | PyTorch | [Link](https://download.pytorch.org/whl/cu130/xformers-0.0.33-cp39-abi3-win_amd64.whl) |
| `0.0.33.post1` | `3.9` | `2.9+` | `13.0` | PyTorch | [Link](https://download.pytorch.org/whl/cu130/xformers-0.0.33.post1-cp39-abi3-win_amd64.whl) |
| `0.0.33.post2` | `3.9` | `2.9+` | `13.0` | PyTorch | [Link](https://download.pytorch.org/whl/cu130/xformers-0.0.33.post2-cp39-abi3-win_amd64.whl) |
| `0.0.33` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.33-cp39-abi3-win_amd64.whl) |
| `0.0.33.post1` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.33.post1-cp39-abi3-win_amd64.whl) |
| `0.0.33.post2` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.33.post2-cp39-abi3-win_amd64.whl) |
| `0.0.33` | `3.9` | `2.9` | `13.0` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/xformers-0.0.33%2Bcu130torch2.9-cp39-abi3-win_amd64.whl) |
| `0.0.33` | `3.9` | `2.10` | `13.0` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/xformers-0.0.33%2Bcu130torch2.10-cp39-abi3-win_amd64.whl) |
<!-- END_XFORMERS_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-sageattention"></a>
### ⚙️ SageAttention
精准且高效的注意力机制，通过平滑量化大幅降低显存占用，同时保持精度。
*   **官方仓库**： [thu-ml/SageAttention](https://github.com/thu-ml/SageAttention)
*   **预编译来源**： <!-- START_SAGEATTENTION_SOURCES -->[woct0rdho](https://github.com/woct0rdho/SageAttention/releases)、[sdbds](https://github.com/sdbds/SageAttention-for-windows/releases)<!-- END_SAGEATTENTION_SOURCES -->

<details>
  <summary>展开已收录的 SageAttention</summary>

<!-- START_SAGEATTENTION2_TABLE -->
| Package Version | Python Ver | PyTorch Ver | CUDA Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|
| `2.0.1` | `3.10` | `2.5.1` | `12.4` | sdbds | [Link](https://github.com/sdbds/SageAttention-for-windows/releases/download/2.0.1/sageattention-2.0.1%2Bcu124torch2.5.1-cp310-cp310-win_amd64.whl) |
| `2.1.1` | `3.9` | `2.5.1` | `12.4` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu124torch2.5.1-cp39-cp39-win_amd64.whl) |
| `2.1.1` | `3.9` | `2.6.0` | `12.6` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu126torch2.6.0-cp39-cp39-win_amd64.whl) |
| `2.1.1` | `3.9` | `2.7.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.0-cp39-cp39-win_amd64.whl) |
| `2.1.1` | `3.9` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.1-cp39-cp39-win_amd64.whl) |
| `2.1.1` | `3.9` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.8.0-cp39-cp39-win_amd64.whl) |
| `2.1.1` | `3.10` | `2.5.1` | `12.4` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu124torch2.5.1-cp310-cp310-win_amd64.whl) |
| `2.1.1` | `3.10` | `2.6.0` | `12.6` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu126torch2.6.0-cp310-cp310-win_amd64.whl) |
| `2.1.1` | `3.10` | `2.7.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.0-cp310-cp310-win_amd64.whl) |
| `2.1.1` | `3.10` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.1-cp310-cp310-win_amd64.whl) |
| `2.1.1` | `3.10` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.8.0-cp310-cp310-win_amd64.whl) |
| `2.1.1` | `3.11` | `2.5.1` | `12.4` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu124torch2.5.1-cp311-cp311-win_amd64.whl) |
| `2.1.1` | `3.11` | `2.6.0` | `12.6` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu126torch2.6.0-cp311-cp311-win_amd64.whl) |
| `2.1.1` | `3.11` | `2.7.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.0-cp311-cp311-win_amd64.whl) |
| `2.1.1` | `3.11` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.1-cp311-cp311-win_amd64.whl) |
| `2.1.1` | `3.11` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.8.0-cp311-cp311-win_amd64.whl) |
| `2.1.1` | `3.12` | `2.5.1` | `12.4` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu124torch2.5.1-cp312-cp312-win_amd64.whl) |
| `2.1.1` | `3.12` | `2.6.0` | `12.6` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu126torch2.6.0-cp312-cp312-win_amd64.whl) |
| `2.1.1` | `3.12` | `2.7.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.0-cp312-cp312-win_amd64.whl) |
| `2.1.1` | `3.12` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.1-cp312-cp312-win_amd64.whl) |
| `2.1.1` | `3.12` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.8.0-cp312-cp312-win_amd64.whl) |
| `2.1.1` | `3.13` | `2.6.0` | `12.6` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu126torch2.6.0-cp313-cp313-win_amd64.whl) |
| `2.1.1` | `3.13` | `2.7.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.0-cp313-cp313-win_amd64.whl) |
| `2.1.1` | `3.13` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.1-cp313-cp313-win_amd64.whl) |
| `2.1.1` | `3.13` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.8.0-cp313-cp313-win_amd64.whl) |
<!-- END_SAGEATTENTION2_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-sageattention-22-sageattention2"></a>
### ⚙️ SageAttention 2.2 (SageAttention2++)
SageAttention 的升级版本，引入更先进的量化策略和优化算法，显存节省更多，速度更快。
*   **官方仓库**： [thu-ml/SageAttention](https://github.com/thu-ml/SageAttention)
*   **预编译来源**： <!-- START_SAGEATTENTION22_SOURCES -->[woct0rdho](https://github.com/woct0rdho/SageAttention/releases)、[sdbds](https://github.com/sdbds/SageAttention-for-windows/releases)、[Wildminder](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)、[Eddy](https://huggingface.co/eddy1111111/sageattention-2.2.0-cp312-270-cu128-cp312-win_amd64/tree/main)<!-- END_SAGEATTENTION22_SOURCES -->
> [!NOTE]
> 仅支持 CUDA ≥ 12.8，因此需搭配 PyTorch ≥ 2.7。

<details>
  <summary>展开已收录的 SageAttention 2++</summary>

<!-- START_SAGEATTENTION22_TABLE -->
| Package Version | Python Ver | PyTorch Ver | CUDA Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|
| `2.2.0.post1` | `3.9` | `2.5.1` | `12.4` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post1/sageattention-2.2.0%2Bcu124torch2.5.1.post1-cp39-abi3-win_amd64.whl) |
| `2.2.0.post2` | `3.9` | `2.5.1` | `12.4` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post2/sageattention-2.2.0%2Bcu124torch2.5.1.post2-cp39-abi3-win_amd64.whl) |
| `2.2.0.post3` | `3.9` | `2.5.1` | `12.4` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post3/sageattention-2.2.0%2Bcu124torch2.5.1.post3-cp39-abi3-win_amd64.whl) |
| `2.2.0.post1` | `3.9` | `2.6.0` | `12.6` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post1/sageattention-2.2.0%2Bcu126torch2.6.0.post1-cp39-abi3-win_amd64.whl) |
| `2.2.0.post2` | `3.9` | `2.6.0` | `12.6` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post2/sageattention-2.2.0%2Bcu126torch2.6.0.post2-cp39-abi3-win_amd64.whl) |
| `2.2.0.post3` | `3.9` | `2.6.0` | `12.6` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post3/sageattention-2.2.0%2Bcu126torch2.6.0.post3-cp39-abi3-win_amd64.whl) |
| `2.2.0.post1` | `3.9` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post1/sageattention-2.2.0%2Bcu128torch2.7.1.post1-cp39-abi3-win_amd64.whl) |
| `2.2.0.post2` | `3.9` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post2/sageattention-2.2.0%2Bcu128torch2.7.1.post2-cp39-abi3-win_amd64.whl) |
| `2.2.0.post3` | `3.9` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post3/sageattention-2.2.0%2Bcu128torch2.7.1.post3-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `3.9` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.7.1-cp39-cp39-win_amd64.whl) |
| `2.2.0.post1` | `3.9` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post1/sageattention-2.2.0%2Bcu128torch2.8.0.post1-cp39-abi3-win_amd64.whl) |
| `2.2.0.post2` | `3.9` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post2/sageattention-2.2.0%2Bcu128torch2.8.0.post2-cp39-abi3-win_amd64.whl) |
| `2.2.0.post3` | `3.9` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post3/sageattention-2.2.0%2Bcu128torch2.8.0.post3-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `3.9` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.8.0-cp39-cp39-win_amd64.whl) |
| `2.2.0.post3` | `3.9` | `2.9.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post3/sageattention-2.2.0%2Bcu128torch2.9.0.post3-cp39-abi3-win_amd64.whl) |
| `2.2.0.post4` | `3.9` | `2.9.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post4/sageattention-2.2.0%2Bcu128torch2.9.0andhigher.post4-cp39-abi3-win_amd64.whl) |
| `2.2.0.post3` | `3.9` | `2.9.0` | `13.0` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post3/sageattention-2.2.0%2Bcu130torch2.9.0.post3-cp39-abi3-win_amd64.whl) |
| `2.2.0.post4` | `3.9` | `2.9.0` | `13.0` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post4/sageattention-2.2.0%2Bcu130torch2.9.0andhigher.post4-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `3.10` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.7.1-cp310-cp310-win_amd64.whl) |
| `2.2.0` | `3.10` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.8.0-cp310-cp310-win_amd64.whl) |
| `2.2.0` | `3.11` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.7.1-cp311-cp311-win_amd64.whl) |
| `2.2.0` | `3.11` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.8.0-cp311-cp311-win_amd64.whl) |
| `2.2.0` | `3.11` | `2.9.0` | `13.0` | sdbds | [Link](https://github.com/sdbds/SageAttention-for-windows/releases/download/torch290%2Bcu130/sageattention-2.2.0%2Bcu130torch2.9.0-cp311-cp311-win_amd64.whl) |
| `2.2.0` | `3.11` | `2.9.1` | `13.0` | sdbds | [Link](https://github.com/sdbds/SageAttention-for-windows/releases/download/torch291%2Bcu130/sageattention-2.2.0%2Bcu130torch2.9.1-cp311-cp311-win_amd64.whl) |
| `2.2.0` | `3.12` | `2.7.0` | `12.8` | Eddy | [Link](https://huggingface.co/eddy1111111/sageattention-2.2.0-cp312-270-cu128-cp312-win_amd64/blob/main/sageattention-2.2.0-cp312-270-cu128-cp312-win_amd64.whl) |
| `2.2.0` | `3.12` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.7.1-cp312-cp312-win_amd64.whl) |
| `2.2.0` | `3.12` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.8.0-cp312-cp312-win_amd64.whl) |
| `2.2.0` | `3.12` | `2.9.0` | `12.8` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0%2Bcu128torch2.9.0cxx11abi1-cp312-cp312-win_amd64.whl) |
| `2.2.0.post3` | `3.12` | `2.10.0` | `12.8` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0.post3%2Bcu128torch2.10.0-cp312-cp312-win_amd64.whl) |
| `2.2.0.post3` | `3.12` | `2.10.0` | `13.0` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0.post3%2Bcu130torch2.10.0-cp312-cp312-win_amd64.whl) |
| `2.2.0` | `3.13` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.7.1-cp313-cp313-win_amd64.whl) |
| `2.2.0` | `3.13` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.8.0-cp313-cp313-win_amd64.whl) |
| `2.2.0.post3` | `3.13` | `2.8.0` | `12.8` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0.post3%2Bcu128torch2.8.0-cp313-cp313-win_amd64.whl) |
| `2.2.0.post3` | `3.13` | `2.8.0` | `12.9` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0.post3%2Bcu129torch2.8.0-cp313-cp313-win_amd64.whl) |
| `2.2.0.post3` | `3.13` | `2.9.0` | `12.8` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0.post3%2Bcu128torch2.9.0-cp313-cp313-win_amd64.whl) |
| `2.2.0.post3` | `3.13` | `2.9.0` | `12.9` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0.post3%2Bcu129torch2.9.0-cp313-cp313-win_amd64.whl) |
| `2.2.0.post3` | `3.13` | `2.9.0` | `13.0` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0.post3%2Bcu130torch2.9.0-cp313-cp313-win_amd64.whl) |
| `2.2.0.post3` | `3.13` | `2.10.0` | `12.8` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0.post3%2Bcu128torch2.10.0-cp313-cp313-win_amd64.whl) |
| `2.2.0.post3` | `3.13` | `2.10.0` | `13.0` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0.post3%2Bcu130torch2.10.0-cp313-cp313-win_amd64.whl) |
<!-- END_SAGEATTENTION22_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-sageattention3"></a>
### ⚙️ SageAttention 3
用于推理的微缩放 FP4 注意力机制 和 8 位训练的探索，目前仅支持 Blackwell 架构。
*   **官方仓库**： [thu-ml/SageAttention](https://github.com/thu-ml/SageAttention/tree/main/sageattention3_blackwell)
*   **预编译来源**： <!-- START_SAGEATTENTION3_SOURCES -->[sdbds](https://github.com/sdbds/SageAttention-for-windows/releases)、[Eddy](https://huggingface.co/eddy1111111/sageattention-2.2.0-cp312-270-cu128-cp312-win_amd64/tree/main)<!-- END_SAGEATTENTION3_SOURCES -->
> [!NOTE]
> SageAttention3 不保證所有型號的無損加速。對於其他影片產生模型,我們建議在某些圖層或時間步長中選擇性地使用 SageAttention2++

<details>
  <summary>展开已收录的 SageAttention 3</summary>

<!-- START_SAGEATTENTION3_TABLE -->
| Package Version | Python Ver | PyTorch Ver | CUDA Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|
| `1.0.0` | `3.11` | `2.8.0` | `12.8` | sdbds | [Link](https://github.com/sdbds/SageAttention-for-windows/releases/download/SA3-1.0.0/sageattn3-1.0.0%2Bcu128torch2.8.0-cp311-cp311-win_amd64.whl) |
| `1.0.0` | `3.12` | `2.8.0` | `12.8` | Eddy | [Link](https://huggingface.co/eddy1111111/sageattention-2.2.0-cp312-270-cu128-cp312-win_amd64/resolve/main/sageattn3-1.0.0-cp312-cp312-win_amd64.whl) |
<!-- END_SAGEATTENTION3_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-spargeattn"></a>
### ⚙️ SpargeAttn
稀疏注意力机制，通过智能跳过不重要的计算来加速推理，适用于长上下文场景。
*   **官方仓库**： [thu-ml/SpargeAttn](https://github.com/thu-ml/SpargeAttn)
*   **预编译来源**： <!-- START_SPARGEATTN_SOURCES -->[woct0rdho](https://github.com/woct0rdho/SpargeAttn/releases)<!-- END_SPARGEATTN_SOURCES -->

<details>
  <summary>展开已收录的 SpargeAttn</summary>
  
<!-- START_SPARGEATTN_TABLE -->
| Package Version | PyTorch Ver | CUDA Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|
| `0.1.0.post2` | `2.5.1` | `12.4` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post2/spas_sage_attn-0.1.0%2Bcu124torch2.5.1.post2-cp39-abi3-win_amd64.whl) |
| `0.1.0.post3` | `2.5.1` | `12.4` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post3/spas_sage_attn-0.1.0%2Bcu124torch2.5.1.post3-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.5.1` | `12.4` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows/spas_sage_attn-0.1.0%2Bcu124torch2.5.1-cp39-abi3-win_amd64.whl) |
| `0.1.0.post2` | `2.6.0` | `12.6` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post2/spas_sage_attn-0.1.0%2Bcu126torch2.6.0.post2-cp39-abi3-win_amd64.whl) |
| `0.1.0.post3` | `2.6.0` | `12.6` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post3/spas_sage_attn-0.1.0%2Bcu126torch2.6.0.post3-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.6.0` | `12.6` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows/spas_sage_attn-0.1.0%2Bcu126torch2.6.0-cp39-abi3-win_amd64.whl) |
| `0.1.0.post1` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post1/spas_sage_attn-0.1.0%2Bcu128torch2.7.1.post1-cp39-abi3-win_amd64.whl) |
| `0.1.0.post2` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post2/spas_sage_attn-0.1.0%2Bcu128torch2.7.1.post2-cp39-abi3-win_amd64.whl) |
| `0.1.0.post3` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post3/spas_sage_attn-0.1.0%2Bcu128torch2.7.1.post3-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.7.1` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows/spas_sage_attn-0.1.0%2Bcu128torch2.7.1-cp39-abi3-win_amd64.whl) |
| `0.1.0.post1` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post1/spas_sage_attn-0.1.0%2Bcu128torch2.8.0.post1-cp39-abi3-win_amd64.whl) |
| `0.1.0.post2` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post2/spas_sage_attn-0.1.0%2Bcu128torch2.8.0.post2-cp39-abi3-win_amd64.whl) |
| `0.1.0.post3` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post3/spas_sage_attn-0.1.0%2Bcu128torch2.8.0.post3-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.8.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows/spas_sage_attn-0.1.0%2Bcu128torch2.8.0-cp39-abi3-win_amd64.whl) |
| `0.1.0.post2` | `2.9.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post2/spas_sage_attn-0.1.0%2Bcu128torch2.9.0.post2-cp39-abi3-win_amd64.whl) |
| `0.1.0.post3` | `2.9.0` | `12.8` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post3/spas_sage_attn-0.1.0%2Bcu128torch2.9.0.post3-cp39-abi3-win_amd64.whl) |
| `0.1.0.post3` | `2.9.0` | `13.0` | woct0rdho | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post3/spas_sage_attn-0.1.0%2Bcu130torch2.9.0.post3-cp39-abi3-win_amd64.whl) |
<!-- END_SPARGEATTN_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-nunchaku"></a>
### ⚙️ Nunchaku
MIT 开发的 Transformer 推理加速库，专注于提升解码速度和吞吐量。
*   **官方仓库**： [mit-han-lab/nunchaku](https://github.com/mit-han-lab/nunchaku/releases)
*   **预编译来源**： <!-- START_NUNCHAKU_SOURCES -->[nunchaku-tech](https://github.com/nunchaku-tech/nunchaku/releases)、[Wildminder](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)<!-- END_NUNCHAKU_SOURCES -->

<details>
  <summary>展开已收录的 Nunchaku</summary>

<!-- START_NUNCHAKU_TABLE -->
| Package Version | Python Ver | PyTorch Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|
| `0.2.0` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `0.2.0` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `0.2.0` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `0.2.0` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `0.2.0` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `0.2.0` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `0.2.0` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `0.2.0` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `0.2.0` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `0.2.0` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `0.2.0` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `0.2.0` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `0.2.0` | `3.13` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `0.2.0` | `3.13` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `0.2.0` | `3.13` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `0.3.0` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `0.3.0` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `0.3.0` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `0.3.0` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `0.3.0` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `0.3.0` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `0.3.0` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `0.3.0` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `0.3.0` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `0.3.0` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `0.3.0` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `0.3.0` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `0.3.1` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `0.3.1` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `0.3.1` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `0.3.1` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `0.3.1` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `0.3.1` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `0.3.1` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `0.3.1` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `0.3.1` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `0.3.1` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `0.3.1` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `0.3.1` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `0.3.2` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `0.3.2` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `0.3.2` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `0.3.2` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `0.3.2` | `3.10` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `0.3.2` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `0.3.2` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `0.3.2` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `0.3.2` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `0.3.2` | `3.11` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `0.3.2` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `0.3.2` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `0.3.2` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `0.3.2` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `0.3.2` | `3.12` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.0` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250820` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250820/nunchaku-1.0.0.dev20250820%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.0` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.0` | `3.10` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250820` | `3.10` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250820/nunchaku-1.0.0.dev20250820%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.10` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.10` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.10` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.10` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.10` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250820` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250820/nunchaku-1.0.0.dev20250820%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.0` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.0` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.0` | `3.11` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.11` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.11` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.11` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.11` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.11` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.0` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.0` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.0` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.0` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.0` | `3.12` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250823` | `3.12` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250830` | `3.12` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250902` | `3.12` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.12` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.12` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0` | `3.13` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.13` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.13` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.0` | `3.13` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.13` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.13` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.0` | `3.13` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.13` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.13` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.0` | `3.13` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.9-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250903` | `3.13` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.9-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250904` | `3.13` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.9-cp313-cp313-win_amd64.whl) |
| `1.0.1` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.10` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.1` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.10` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.1` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.1` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.1` | `3.10` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.10` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.10` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.10` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.10` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.10` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.1` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.11` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.1` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.11` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.1` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.1` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.1` | `3.11` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.11` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.11` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.11` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.11` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.11` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.1` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.12` | `2.5` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.12` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `3.12` | `2.9` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/nunchaku-1.0.1%2Bcu128torch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `3.12` | `2.9` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/nunchaku-1.0.1%2Bcu130torch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `3.12` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.12` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.12` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.12` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.12` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.12` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `3.13` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.13` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.13` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.13` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.13` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.13` | `2.6` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.1` | `3.13` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.13` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.13` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.13` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.13` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.13` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.1` | `3.13` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.13` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.13` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.13` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.13` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.13` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.1` | `3.13` | `2.9` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/nunchaku-1.0.1%2Bcu128torch2.9-cp313-cp313-win_amd64.whl) |
| `1.0.1` | `3.13` | `2.9` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/nunchaku-1.0.1%2Bcu130torch2.9-cp313-cp313-win_amd64.whl) |
| `1.0.1` | `3.13` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250923` | `3.13` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250924` | `3.13` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250926` | `3.13` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250929` | `3.13` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250930` | `3.13` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.2` | `3.10` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.2` | `3.10` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.2` | `3.10` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.2` | `3.10` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.2` | `3.11` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.2` | `3.11` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.2` | `3.11` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.2` | `3.11` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.2` | `3.12` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.2` | `3.12` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.2` | `3.12` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.2` | `3.12` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.2` | `3.13` | `2.7` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.2` | `3.13` | `2.8` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.2` | `3.13` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.9-cp313-cp313-win_amd64.whl) |
| `1.0.2` | `3.13` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.1.0.dev20251111` | `3.10` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.1.0.dev20251111` | `3.10` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.1.0.dev20251111` | `3.11` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.1.0.dev20251111` | `3.11` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.1.0.dev20251111` | `3.12` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.1.0.dev20251111` | `3.12` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.1.0.dev20251111` | `3.13` | `2.9` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.9-cp313-cp313-win_amd64.whl) |
| `1.1.0.dev20251111` | `3.13` | `2.10` | nunchaku-tech | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.10-cp313-cp313-win_amd64.whl) |
<!-- END_NUNCHAKU_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-natten"></a>
### ⚙️ NATTEN (Neighborhood Attention Transformer)
局部邻域注意力实现，在视觉任务中表现出色。
*   **官方仓库**： [SHI-Labs/NATTEN](https://github.com/SHI-Labs/NATTEN)
*   **预编译来源**： <!-- START_NATTEN_SOURCES -->[lldacing](https://huggingface.co/lldacing/NATTEN-windows/tree/main)<!-- END_NATTEN_SOURCES -->

<details>
  <summary>展开已收录的 NATTEN</summary>

<!-- START_NATTEN_TABLE -->
| Package Version | Python Ver | PyTorch Ver | CUDA Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|
| `0.17.3` | `3.10` | `2.4.0` | `12.4` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.3%2Btorch240cu124-cp310-cp310-win_amd64.whl) |
| `0.17.3` | `3.10` | `2.4.1` | `12.4` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.3%2Btorch241cu124-cp310-cp310-win_amd64.whl) |
| `0.17.3` | `3.10` | `2.5.0` | `12.4` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.3%2Btorch250cu124-cp310-cp310-win_amd64.whl) |
| `0.17.3` | `3.10` | `2.5.1` | `12.4` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.3%2Btorch251cu124-cp310-cp310-win_amd64.whl) |
| `0.17.3` | `3.11` | `2.4.0` | `12.4` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.3%2Btorch240cu124-cp311-cp311-win_amd64.whl) |
| `0.17.3` | `3.11` | `2.4.1` | `12.4` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.3%2Btorch241cu124-cp311-cp311-win_amd64.whl) |
| `0.17.3` | `3.11` | `2.5.0` | `12.4` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.3%2Btorch250cu124-cp311-cp311-win_amd64.whl) |
| `0.17.3` | `3.11` | `2.5.1` | `12.4` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.3%2Btorch251cu124-cp311-cp311-win_amd64.whl) |
| `0.17.3` | `3.12` | `2.4.0` | `12.4` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.3%2Btorch240cu124-cp312-cp312-win_amd64.whl) |
| `0.17.3` | `3.12` | `2.4.1` | `12.4` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.3%2Btorch241cu124-cp312-cp312-win_amd64.whl) |
| `0.17.3` | `3.12` | `2.5.0` | `12.4` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.3%2Btorch250cu124-cp312-cp312-win_amd64.whl) |
| `0.17.3` | `3.12` | `2.5.1` | `12.4` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.3%2Btorch251cu124-cp312-cp312-win_amd64.whl) |
| `0.17.5` | `3.10` | `2.6.0` | `12.6` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.5%2Btorch260cu126-cp310-cp310-win_amd64.whl) |
| `0.17.5` | `3.10` | `2.7.0` | `12.8` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.5%2Btorch270cu128-cp310-cp310-win_amd64.whl) |
| `0.17.5` | `3.11` | `2.6.0` | `12.6` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.5%2Btorch260cu126-cp311-cp311-win_amd64.whl) |
| `0.17.5` | `3.11` | `2.7.0` | `12.8` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.5%2Btorch270cu128-cp311-cp311-win_amd64.whl) |
| `0.17.5` | `3.12` | `2.6.0` | `12.6` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.5%2Btorch260cu126-cp312-cp312-win_amd64.whl) |
| `0.17.5` | `3.12` | `2.7.0` | `12.8` | lldacing | [Link](https://huggingface.co/lldacing/NATTEN-windows/blob/main/natten-0.17.5%2Btorch270cu128-cp312-cp312-win_amd64.whl) |
<!-- END_NATTEN_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-tritonwindows-fork"></a>
### ⚙️ Triton（Windows Fork）
用于编写高效深度学习算子的语言与编译器，官方不支持 Windows，这是社区维护的 Fork 版本。
*   **Windows Fork**： <!-- START_TRITON_SOURCES -->[woct0rdho](https://github.com/woct0rdho/triton-windows/releases)<!-- END_TRITON_SOURCES -->
*   **安装命令**： `pip install -U "triton-windows<3.6"`

<details>
  <summary>展开已收录的 Triton</summary>

<!-- START_TRITON_TABLE -->
| Package Version | Python Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|
| `3.0.0` | `3.8` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.1.0-windows.post5/triton-3.0.0-cp38-cp38-win_amd64.whl) |
| `3.0.0` | `3.9` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.1.0-windows.post5/triton-3.0.0-cp39-cp39-win_amd64.whl) |
| `3.0.0` | `3.10` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.0.0-windows.post1/triton-3.0.0-cp310-cp310-win_amd64.whl) |
| `3.0.0` | `3.11` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.0.0-windows.post1/triton-3.0.0-cp311-cp311-win_amd64.whl) |
| `3.0.0` | `3.12` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.0.0-windows.post1/triton-3.0.0-cp312-cp312-win_amd64.whl) |
| `3.1.0` | `3.8` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.1.0-windows.post5/triton-3.1.0-cp38-cp38-win_amd64.whl) |
| `3.1.0` | `3.9` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.1.0-windows.post5/triton-3.1.0-cp39-cp39-win_amd64.whl) |
| `3.1.0` | `3.10` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.1.0-windows.post4/triton-3.1.0-cp310-cp310-win_amd64.whl) |
| `3.1.0` | `3.11` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.1.0-windows.post4/triton-3.1.0-cp311-cp311-win_amd64.whl) |
| `3.1.0` | `3.12` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.1.0-windows.post4/triton-3.1.0-cp312-cp312-win_amd64.whl) |
| `3.2.0` | `3.9` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.2.0-windows.post10/triton-3.2.0-cp39-cp39-win_amd64.whl) |
| `3.2.0` | `3.10` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.2.0-windows.post10/triton-3.2.0-cp310-cp310-win_amd64.whl) |
| `3.2.0` | `3.11` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.2.0-windows.post10/triton-3.2.0-cp311-cp311-win_amd64.whl) |
| `3.2.0` | `3.12` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.2.0-windows.post10/triton-3.2.0-cp312-cp312-win_amd64.whl) |
| `3.2.0` | `3.13` | woct0rdho | [Link](https://github.com/woct0rdho/triton-windows/releases/download/v3.2.0-windows.post10/triton-3.2.0-cp313-cp313-win_amd64.whl) |
<!-- END_TRITON_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-bitsandbytes"></a>
### ⚙️ bitsandbytes
轻量级 CUDA 算子库，提供 8-bit 优化器和 LLM 量化支持，大幅降低显存需求。
*   **官方仓库**： [bitsandbytes-foundation/bitsandbytes](https://github.com/bitsandbytes-foundation/bitsandbytes)
*   **预编译来源**： <!-- START_BITSANDBYTES_SOURCES -->[jllllll](https://github.com/jllllll/bitsandbytes-windows-webui/releases)、[bitsandbytes-foundation](https://github.com/bitsandbytes-foundation/bitsandbytes/releases)<!-- END_BITSANDBYTES_SOURCES -->

<details>
  <summary>展开已收录的 bitsandbytes</summary>

<!-- START_BITSANDBYTES_TABLE -->
| Package Version | Source | Download Link |
|:---:|:---:|:---:|
| `0.35.0` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.35.0-py3-none-win_amd64.whl) |
| `0.35.4` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.35.4-py3-none-win_amd64.whl) |
| `0.37.2` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.37.2-py3-none-win_amd64.whl) |
| `0.38.1` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.38.1-py3-none-win_amd64.whl) |
| `0.39.0` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.39.0-py3-none-win_amd64.whl) |
| `0.39.1` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.39.1-py3-none-win_amd64.whl) |
| `0.40.0` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.40.0-py3-none-win_amd64.whl) |
| `0.40.0.post4` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.40.0.post4-py3-none-win_amd64.whl) |
| `0.40.1.post1` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.40.1.post1-py3-none-win_amd64.whl) |
| `0.40.2` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.40.2-py3-none-win_amd64.whl) |
| `0.41.0` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.41.0-py3-none-win_amd64.whl) |
| `0.41.1` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.41.1-py3-none-win_amd64.whl) |
| `0.41.2.post2` | jllllll | [Link](https://github.com/jllllll/bitsandbytes-windows-webui/releases/download/wheels/bitsandbytes-0.41.2.post2-py3-none-win_amd64.whl) |
| `1.0.0` | bitsandbytes-foundation | [Link](https://github.com/bitsandbytes-foundation/bitsandbytes/releases/download/continuous-release_multi-backend-refactor/bitsandbytes-1.0.0-py3-none-win_amd64.whl) |
| `1.33.7.preview` | bitsandbytes-foundation | [Link](https://github.com/bitsandbytes-foundation/bitsandbytes/releases/download/continuous-release_main/bitsandbytes-1.33.7.preview-py3-none-win_amd64.whl) |
<!-- END_BITSANDBYTES_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-radialattention-for-comfyui"></a>
### ⚙️ RadialAttention（ComfyUI 节点）
用于长视频生成的径向注意力机制，在保持质量的同时大幅减少内存占用。
*   **官方仓库**： [mit-han-lab/radial-attention](https://github.com/mit-han-lab/radial-attention)
*   **ComfyUI 节点**： [ComfyUI-RadialAttn](https://github.com/woct0rdho/ComfyUI-RadialAttn)

> **💡 安装说明**：  
> RadialAttention 不是独立的 wheel 包，而是通过 ComfyUI 自定义节点使用。安装步骤：
> 1. 先安装 [SpargeAttn](#️-spargeattn)（见上方，我们已收录其 Windows wheels）
> 2. 将 [ComfyUI-RadialAttn](https://github.com/woct0rdho/ComfyUI-RadialAttn) clone 到 `ComfyUI/custom_nodes/` 目录
> 3. （可选）安装 [SageAttention](#️-sageattention) 并使用 `--use-sage-attention` 参数启动 ComfyUI，作为备用加速方案
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<!-- CONTRIBUTING -->
<a id="-贡献-contributing"></a>
## 🟦 贡献 (Contributing)

贡献让开源社区成为一个令人惊叹的学习、启发和创造的地方。我们**非常感激**您做出的任何贡献。

如果您发现了新的预编译 wheel 文件或可靠的来源，请 pull request，或者直接开一个 issue 附上链接。

<!-- ACKNOWLEDGMENTS -->
<a id="-致谢-acknowledgments"></a>
## 🟦 致谢 (Acknowledgments)

本仓库仅仅是一个链接集合。衷心感谢那些为社区辛勤构建和托管这些 wheel 文件的个人和团队。

<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<!-- MARKDOWN LINKS & IMAGES -->











