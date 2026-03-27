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
    <strong>⏱️ 最后自动更新（UTC）：<!-- START_LAST_UPDATED -->2026-03-27T03:50:00.403556+00:00<!-- END_LAST_UPDATED --></strong>
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
| `2.11.0a0` | `3.12` | `2.10.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/torchaudio-2.11.0a0%2Bd20260121.cu130torch2.10.0cxx11abi1-cp312-cp312-win_amd64.whl) |
| `2.11.0a0` | `3.13` | `2.10.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/torchaudio-2.11.0a0%2Bcu128torch2.10.0cxx11abi1-cp313-cp313-win_amd64.whl) |
| `2.11.0a0` | `3.13` | `2.10.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/torchaudio-2.11.0a0%2Bcu130torch2.10.0cxx11abi1-cp313-cp313-win_amd64.whl) |
| `2.11.0a0` | `3.13` | `2.11.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/torchaudio-2.11.0a0%2Bcu130torch2.11.0cxx11abi1-cp313-cp313-win_amd64.whl) |
<!-- END_TORCHAUDIO_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-flash-attention"></a>
### ⚙️ Flash Attention
高性能注意力机制的先驱实现，通过分块计算和重计算策略大幅降低显存并提速。
*   **官方仓库**： [Dao-AILab/flash-attention](https://github.com/Dao-AILab/flash-attention)
*   **预编译来源**： <!-- START_FLASHATTENTION_SOURCES -->[Wildminder](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)、[lldacing](https://huggingface.co/lldacing/flash-attention-windows-wheel/tree/main)、[BradPita](https://huggingface.co/BradPita/Win-AI-Wheelhouse/tree/main)、[Kijai](https://huggingface.co/Kijai/PrecompiledWheels/tree/main)<!-- END_FLASHATTENTION_SOURCES -->

<details>
  <summary>展开已收录的 Flash Attention</summary>
  
> **📝 CXX11 ABI 说明：**  
> - `✓` = 启用 CXX11 ABI（适用于新版 PyTorch，通常 2.7.0 及以上）
> - `✗` = 禁用 CXX11 ABI（Pre-CXX11 ABI，适用于旧版或特定配置）
> - `—` = 未明确标注（请根据您的 PyTorch 版本选择，或参考 [CXX11 ABI 说明](#-cxx11-abi-说明)）

<!-- START_FLASHATTENTION_TABLE -->
| Package Version | Python Ver | PyTorch Ver | CUDA Ver | CXX11 ABI | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
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
| `2.7.4` | `3.10` | `2.5.1` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu124torch2.5.1cxx11abiFALSE-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `3.10` | `2.6.0` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu124torch2.6.0cxx11abiFALSE-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `3.10` | `2.6.0` | `12.6` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu126torch2.6.0cxx11abiFALSE-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `3.10` | `2.7.0` | `12.8` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4.post1%2Bcu128torch2.7.0cxx11abiFALSE-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `3.10` | `2.8.0` | `12.8` | ✓ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4.post1%2Bcu128torch2.8.0cxx11abiTRUE-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `3.11` | `2.6.0` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu124torch2.6.0cxx11abiFALSE-cp311-cp311-win_amd64.whl) |
| `2.7.4` | `3.11` | `2.6.0` | `12.6` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu126torch2.6.0cxx11abiFALSE-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `3.11` | `2.7.0` | `12.8` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4.post1%2Bcu128torch2.7.0cxx11abiFALSE-cp311-cp311-win_amd64.whl) |
| `2.7.4` | `3.12` | `2.6.0` | `12.4` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu124torch2.6.0cxx11abiFALSE-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `3.12` | `2.6.0` | `12.6` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4%2Bcu126torch2.6.0cxx11abiFALSE-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `3.12` | `2.6.0` | `12.8` | ✗ | Kijai | [Link](https://huggingface.co/Kijai/PrecompiledWheels/blob/main/flash_attn-2.7.4%2Bcu128torch2.6.0cxx11abiFALSE-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `3.12` | `2.7.0` | `12.8` | ✗ | lldacing | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/blob/main/flash_attn-2.7.4.post1%2Bcu128torch2.7.0cxx11abiFALSE-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `3.12` | `2.8.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.7.4.post1%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.0.post2` | `3.12` | `2.8.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.0.post2%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.1` | `3.12` | `2.8.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.1%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.2` | `3.12` | `2.8.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.2%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.2` | `3.12` | `2.9.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.2%2Bcu128torch2.9.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.8.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.9.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu128torch2.9.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.9.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.9.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.9.1` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.9.1cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.10.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.10.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.12` | `2.11.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bd20260120.cu130torch2.11.0cxx11abiTRUE-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.8` | `12.8` | — | BradPita | [Link](https://huggingface.co/BradPita/Win-AI-Wheelhouse/blob/main/flash_attn-2.8.3%2Bcu128torch2.8-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.9.0` | `12.9` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu129torch2.9.0cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.9.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.9.0cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.9.1` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu128torch2.9.1cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.9.1` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.9.1cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.10.0` | `12.8` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu128torch2.10.0cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.10.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.10.0cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `3.13` | `2.11.0` | `13.0` | ✓ | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/flash_attn-2.8.3%2Bcu130torch2.11.0cxx11abiTRUE-cp313-cp313-win_amd64.whl) |
<!-- END_FLASHATTENTION_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-xformers"></a>
### ⚙️ xformers
Meta 开发的内存高效注意力库，提供多种优化算子，广泛应用于图像生成和 LLM 推理。
*   **官方仓库**： [facebookresearch/xformers](https://github.com/facebookresearch/xformers/releases)
*   **预编译来源**： <!-- START_XFORMERS_SOURCES -->[PyTorch](https://download.pytorch.org/whl/xformers/)<!-- END_XFORMERS_SOURCES -->
> [!NOTE]
> 安装 PyTorch 后通常可以直接 `pip install xformers`。若失败，可在预编译来源中寻找与环境匹配的 wheel。

ABI3 版本可兼容 Python 3.9-3.12。

<details>
  <summary>展开已收录的 xformers</summary>

<!-- START_XFORMERS_TABLE -->
| Package Version | Python Ver | PyTorch Ver | CUDA Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|
| `0.0.22.post2` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post2%2Bcu118-cp38-cp38-win_amd64.whl#sha256=f33381dea46e12c1432e252447572dd06cdba88cf44444fa2aa32e337c910899) |
| `0.0.22.post3` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp38-cp38-win_amd64.whl#sha256=f405360e0e6be837604b3ffa36b85d783262773cb90f25eae0bd6f97af53ae64) |
| `0.0.22.post4` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp38-cp38-win_amd64.whl#sha256=7363a0884dbaad3d73b3986525704464002202967b76352442e516344a262c17) |
| `0.0.22.post7` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp38-cp38-win_amd64.whl#sha256=fb5507d170232e201d75d53c888bc49a1f82835b61468c429a5f288220040374) |
| `0.0.22.post4` | `3.8` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp38-cp38-win_amd64.whl#sha256=b162a9a043bce9d27b715fe378f25c5756945976c430dea84a1de977ce0c0d09) |
| `0.0.22.post7` | `3.8` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp38-cp38-win_amd64.whl#sha256=0bf779c685c8d610d32850d886df9ae7f6c72dfa115b3fe375308bfe8e04effc) |
| `0.0.22.post2` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post2%2Bcu118-cp39-cp39-win_amd64.whl#sha256=5192b4da139ab8525d0330425878ca26b19050476af63bfd4a683c226b03ddc0) |
| `0.0.22.post3` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp39-cp39-win_amd64.whl#sha256=d1ae287c67cd14fd8f638b5a499db4b8348972b4ba09c2ee7ac91bd49525d622) |
| `0.0.22.post4` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp39-cp39-win_amd64.whl#sha256=eea9261c8fa3d036b7f1bc5fc11869a597b7b570115758955ec3b32a5040c6bb) |
| `0.0.22.post7` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp39-cp39-win_amd64.whl#sha256=532a2e71092b2770df6392387a69e1b65e53643308062ce30e0b018432c539da) |
| `0.0.22.post4` | `3.9` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp39-cp39-win_amd64.whl#sha256=242433f5eea7390779368e1d0d588c7dfb26cda6aa2d9743c64abda3884607eb) |
| `0.0.22.post7` | `3.9` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp39-cp39-win_amd64.whl#sha256=58af99cdec4399f57e4a77fe341bf17c26a3d65e5f526b87b5dc887ad70115ca) |
| `0.0.22.post2` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post2%2Bcu118-cp310-cp310-win_amd64.whl#sha256=43e13660b1dd3164fc8a64f474c1dd4a17e2997856013459b1233415701fe76c) |
| `0.0.22.post3` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp310-cp310-win_amd64.whl#sha256=0ec5a4b94604280ea77819acddc605204970e002553c6c3a47101e8b454d74e9) |
| `0.0.22.post4` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp310-cp310-win_amd64.whl#sha256=3b18c13a2f9543af7e89c60cc1dc09cf63408973162162d76243fde443a8464f) |
| `0.0.22.post7` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp310-cp310-win_amd64.whl#sha256=ed97fc004c16aa168004af5bee2d6b12fb33cac45a625482782812b2aefa84ec) |
| `0.0.22.post4` | `3.10` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp310-cp310-win_amd64.whl#sha256=7901a41141348dd389f6cca759ebaa5480d98ecf40bb1c8c1a6cfe7b7d81413e) |
| `0.0.22.post7` | `3.10` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp310-cp310-win_amd64.whl#sha256=fd3c88b4aa4cd5b6aa1ee162c42c649a6dd0555fd54eaed0d1158fe50f8b1517) |
| `0.0.22.post2` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post2%2Bcu118-cp311-cp311-win_amd64.whl#sha256=1849b9d0fe88104d1d2aea595ce8aa23c932f7c0774ccc560b8a111c61602f36) |
| `0.0.22.post3` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp311-cp311-win_amd64.whl#sha256=f5e2085c1487ce720ff4fbabb0eafef2932cd7890893fe19ed0bbb84b31122e2) |
| `0.0.22.post4` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp311-cp311-win_amd64.whl#sha256=86a566b8ba5e2579837dd4253fd0ce42ea7b19c03d58207b7b476befd805a00c) |
| `0.0.22.post7` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp311-cp311-win_amd64.whl#sha256=f5a4c0199cd9e893e97378102be89141e8f3fae01a5df48023c8b23d13c21b27) |
| `0.0.22.post4` | `3.11` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp311-cp311-win_amd64.whl#sha256=cee27b7e9ccc00d3d893cb293cab675624847ec022485c212c3ff85ddece15a6) |
| `0.0.22.post7` | `3.11` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp311-cp311-win_amd64.whl#sha256=5fcb0eb6eb0a6b78f6f866ea90ffbef955f8c903afd1e2fd934c1619eabb042e) |
| `0.0.23` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp38-cp38-win_amd64.whl#sha256=a7f335f6fb3d4ed6f693da8e08389c79274bef4181465f1435f6f5dd2d3615ab) |
| `0.0.23.post1` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp38-cp38-win_amd64.whl#sha256=6f3102134d300c59d31463cc12aae4864cb8dade2668bcd34198fcfd58ea08f8) |
| `0.0.23` | `3.8` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp38-cp38-win_amd64.whl#sha256=4408f2be58da163d598ff5496265c946f922269599cab45d36e65e9f42b37b5c) |
| `0.0.23.post1` | `3.8` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp38-cp38-win_amd64.whl#sha256=aad762aebfe7ea3f6b9132afbf5ae88cdaf87d0c377d199dfee193e1a72d0d24) |
| `0.0.23` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp39-cp39-win_amd64.whl#sha256=200173dcffb6aad82cdfe70a4948c778015898a2fa9a7434cdae4d340718978d) |
| `0.0.23.post1` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp39-cp39-win_amd64.whl#sha256=103820665654b3e21257b1d5711b9fdda34b4a272f9de4b7c047bc4af292e60c) |
| `0.0.23` | `3.9` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp39-cp39-win_amd64.whl#sha256=86e078606e6ec871efea38939ec20649ef78a58d062a66d0b5d6a6bd58b51702) |
| `0.0.23.post1` | `3.9` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp39-cp39-win_amd64.whl#sha256=e08e4ebbd9fbfe9545de4028b7f604d21dc4e301dc651b3fc1bb95ae6797524f) |
| `0.0.23` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp310-cp310-win_amd64.whl#sha256=a05811a355ce5ab5c25e964c78e9cc7fb9b03b674914c8df6d5db45a0bef3da0) |
| `0.0.23.post1` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp310-cp310-win_amd64.whl#sha256=bb845f1dfe21dec3ccaf2c94adabf46bd604ac5bbfb35379340816914b1ce00a) |
| `0.0.23` | `3.10` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp310-cp310-win_amd64.whl#sha256=518d866cc48fe91d055b5e89d86b4d2bec716d15f8a4babec8b2808bb4afb44a) |
| `0.0.23.post1` | `3.10` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp310-cp310-win_amd64.whl#sha256=ef0744c5d1abcad7f8692b5a30ee72a71215451cbde020e2fb37af20f46ba76f) |
| `0.0.23` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp311-cp311-win_amd64.whl#sha256=1e03af99f27612a0099045f835332c5ee4cb5c2df4c0dbcff73a91684a3ec8d4) |
| `0.0.23.post1` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp311-cp311-win_amd64.whl#sha256=8c232bccf88e19de91b545a2b29886c5684bf5d1f7014b6a3d126e481b5e01ee) |
| `0.0.23` | `3.11` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp311-cp311-win_amd64.whl#sha256=32203f4450470f5f16e719dac542f6b665f7111105dd543badf4ae5492de415e) |
| `0.0.23.post1` | `3.11` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp311-cp311-win_amd64.whl#sha256=372995c113c3505648f0c2d2daac53a6df60a22f30eae98e47daca5efd38fe71) |
| `0.0.24` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp38-cp38-win_amd64.whl#sha256=0cf379d0a88cd3abcc6e05221a5dc9cb1b7dfac1e5a3ab366e9d5ea624f648ca) |
| `0.0.24` | `3.8` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp38-cp38-win_amd64.whl#sha256=dd7d65307373fcec77974775980ecd110fdc06489c4d18278a5a923afdd8dde1) |
| `0.0.24` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp39-cp39-win_amd64.whl#sha256=c5ea36fd8e86ded344ccb82a3af92fd6e59082c1866fb30012188d62577f0654) |
| `0.0.24` | `3.9` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp39-cp39-win_amd64.whl#sha256=039f173608a37c1ff74dfd243671d0a12c9d507427f2b864373da838251fd374) |
| `0.0.24` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp310-cp310-win_amd64.whl#sha256=9a701ee428eb1f44f854a77d70f345650e9bfc91cc73be27026f13f4a1d03bdd) |
| `0.0.24` | `3.10` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp310-cp310-win_amd64.whl#sha256=2ebacd38644e4df6a74e14fae55d561acd6d642b62819c1b8c10e07428efdad7) |
| `0.0.24` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp311-cp311-win_amd64.whl#sha256=deb9ceac347f478e4b1ebaed969c0e0389107c268195023860d20b1504eeedbf) |
| `0.0.24` | `3.11` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp311-cp311-win_amd64.whl#sha256=7510268679d32475cb0f0c31d3f8b0a97ebfcd77fea2a1604516908eee0569bb) |
| `0.0.25` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp38-cp38-win_amd64.whl#sha256=53ae4768a53a256a11755f32c10d8d690e0692e103bc7360d3f3e008bf95b84c) |
| `0.0.25.post1` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp38-cp38-win_amd64.whl#sha256=f8c7b1a8e802d47cf833affcbf203acd62e111a656900e2b1b61d645b342c942) |
| `0.0.25` | `3.8` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp38-cp38-win_amd64.whl#sha256=b72fc7f7222184421b63c794e1896424482ee5579d9f1d088b582560eefc3f58) |
| `0.0.25.post1` | `3.8` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp38-cp38-win_amd64.whl#sha256=45646a9877c6376800cb5ed4124e2f3d7baf418f75d9e21840589cf1f4fe1f8e) |
| `0.0.25` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp39-cp39-win_amd64.whl#sha256=35ef134e776bb10afd635daca281bad2b8c3eb10e553595504f155679737683c) |
| `0.0.25.post1` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp39-cp39-win_amd64.whl#sha256=a6e43749a96663d6b69d2d801517b9d30c0931f689eafb2386e59033ef34a555) |
| `0.0.25` | `3.9` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp39-cp39-win_amd64.whl#sha256=669adb8955585f0c30d7c1b0f6d757216c9ea0c62d625f79ebea8aa17665c8f0) |
| `0.0.25.post1` | `3.9` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp39-cp39-win_amd64.whl#sha256=f48bbc04a916d1010b752a005d4a27c54fec181210b63d7879534455e3b53169) |
| `0.0.25` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp310-cp310-win_amd64.whl#sha256=45c4d515e852549be73ae23004fe9e0b78531908563f41f45ec798c8199d9774) |
| `0.0.25.post1` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp310-cp310-win_amd64.whl#sha256=8463057ab6c70828e7b0ef336598e8f56df90b0036549c5f560eef9d66cf25e9) |
| `0.0.25` | `3.10` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp310-cp310-win_amd64.whl#sha256=ef3dc7f65d0b25148570172647759eb3b6032c24d696b52dabd6b55164a4a1ab) |
| `0.0.25.post1` | `3.10` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp310-cp310-win_amd64.whl#sha256=ddc22273f2ff06b886d9e86f17997e4f1f3074fdeb5d46bcdf50b704430df528) |
| `0.0.25` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp311-cp311-win_amd64.whl#sha256=c96e2226a4e9b2fb68cacb579eca85ed568cf6585d5290aa5b61c82f0a5a8822) |
| `0.0.25.post1` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp311-cp311-win_amd64.whl#sha256=41d84b2dea18b50275edf0909a64c34b18b71ddc594971703db4704feb300afc) |
| `0.0.25` | `3.11` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp311-cp311-win_amd64.whl#sha256=a62666f27a10e4e2aff49edce369bbf1f5218ff8d7f9580d33706950ddb992d7) |
| `0.0.25.post1` | `3.11` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp311-cp311-win_amd64.whl#sha256=3eaf21f437c1e1a8aa126310e33b186cb6d90906b06f90759672ba9e1f61893c) |
| `0.0.26` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp38-cp38-win_amd64.whl#sha256=f177bbe3f2fe3eae73de22d18f0944089bfa8cfecf32c1fc606639899448288b) |
| `0.0.26.post1` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp38-cp38-win_amd64.whl#sha256=70d72d7b61dc02463b24140c637ad3dc7281e88d90c319b26d9a2ae2f49fe1ca) |
| `0.0.26` | `3.8` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp38-cp38-win_amd64.whl#sha256=aadca94d92803c4946a47df1eeac819dc7c5112d74c660886eda06e862a91268) |
| `0.0.26.post1` | `3.8` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp38-cp38-win_amd64.whl#sha256=e96e2c1a11e84a6aac8386a304e3e338057c95029c82b221bf6aa1658aeacdf0) |
| `0.0.26` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp39-cp39-win_amd64.whl#sha256=02f814323f70ce4359666dbca2f2f244dc4312acde3ad3839b2d6c0a331c1d96) |
| `0.0.26.post1` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp39-cp39-win_amd64.whl#sha256=2131fef2466cc4b3464113679aa6f701a7bc292bc623b08197fe4001369f8c40) |
| `0.0.26` | `3.9` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp39-cp39-win_amd64.whl#sha256=38199423eb78045a78ed68cf0f048e8d0c5f1dc6c12161b85b782bf5dc56f048) |
| `0.0.26.post1` | `3.9` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp39-cp39-win_amd64.whl#sha256=cf267bac8f4454db1056e4e6ff9e4df1e02b2b31d8116d50913af15fa6ae7132) |
| `0.0.26` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp310-cp310-win_amd64.whl#sha256=a9b3af3c33023096fb6db0b6164c8fac069ff25d5d1fd8c88c96fa845be8f87f) |
| `0.0.26.post1` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp310-cp310-win_amd64.whl#sha256=a8b401d4e5f3845bd277401506f62250702dedfc5cd7944e87d0bc9c30761281) |
| `0.0.26` | `3.10` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp310-cp310-win_amd64.whl#sha256=2261abce21e7100fc5249d0cdbb949d51863c6bc60e121bdc27c29ab6c2a41c1) |
| `0.0.26.post1` | `3.10` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp310-cp310-win_amd64.whl#sha256=e34b8dd6982077bee0c8eb2db8bc1513177201bfe0af890a4db42d8d31c966a5) |
| `0.0.26` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp311-cp311-win_amd64.whl#sha256=c121286fc5331d7929aeea4ca130ea7164149e17e23d935cb282e96b2cbf1a1d) |
| `0.0.26.post1` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp311-cp311-win_amd64.whl#sha256=2fd882d2dca2e5e814aede20819804041496c938fb395f00c511424ef76dd86e) |
| `0.0.26` | `3.11` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp311-cp311-win_amd64.whl#sha256=b3c46089a1b6248b162b3923244a3e0dcec8746883230014c0136300cf0c2ca1) |
| `0.0.26.post1` | `3.11` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp311-cp311-win_amd64.whl#sha256=d05c547b4ba603fc8e21fad03a342138eaaece35fe0a1692e6ee0d061ddd21ac) |
| `0.0.27` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp38-cp38-win_amd64.whl#sha256=a46f49ec62ce939ee1585bd8ab484be83328df5e3c64237dc22a314d46214868) |
| `0.0.27.post1` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp38-cp38-win_amd64.whl#sha256=366621048e45875d82da0e837d92e242ce42f4edd4403c7958e3435f471f8ff4) |
| `0.0.27.post2` | `3.8` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp38-cp38-win_amd64.whl#sha256=88ce8aaa16a1270f66201160649a6fd792bdb0463cc9a6b30fdb556737dc91bb) |
| `0.0.27` | `3.8` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp38-cp38-win_amd64.whl#sha256=d79457fd3d3b655527596e8de16787928b38ef21007bcd9fdb193c348a9516a4) |
| `0.0.27.post1` | `3.8` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp38-cp38-win_amd64.whl#sha256=301151d2ccd40ac6261ddf99fa29ff82b1f29b69f292251739cff28728786023) |
| `0.0.27.post2` | `3.8` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp38-cp38-win_amd64.whl#sha256=5a83aa75a7208c359b2755af318e97e70855dbae6cdf998227f6dee220a56203) |
| `0.0.27` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp39-cp39-win_amd64.whl#sha256=00d3e1e48cbfedf823113d9f43fc19aaa396d6ac7883c4b3fd1ce697d9f65d2d) |
| `0.0.27.post1` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp39-cp39-win_amd64.whl#sha256=fe2661ded39d1a5d8e499a08aa54a51861b668eecdfd7d4e14bb5343e82cf326) |
| `0.0.27.post2` | `3.9` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp39-cp39-win_amd64.whl#sha256=674273d49c86ef40af563a3bd0908fc266a154683ed039c16e1012a2e4859ca7) |
| `0.0.27` | `3.9` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp39-cp39-win_amd64.whl#sha256=67ab5341c7dbfeb96450778a1cd358710c4e71566dd1115246c766d01f2d5417) |
| `0.0.27.post1` | `3.9` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp39-cp39-win_amd64.whl#sha256=d6196c48b6196544c058b703ee51dfa7bd92021562f88b3afcebb35afe28ff3a) |
| `0.0.27.post2` | `3.9` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp39-cp39-win_amd64.whl#sha256=d555ef6d3722941cd785cf4b7c6039b06e8a0ca1360ff661200cf043393ca5a2) |
| `0.0.27` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp310-cp310-win_amd64.whl#sha256=70d3850e0d11a78fedfba1ddce5d248544890569f7cb55737e86677158173384) |
| `0.0.27.post1` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp310-cp310-win_amd64.whl#sha256=15bdfd7e8c3a57dc6fdd97ec9482c858acd32a14861f058c2a3062f662ce3b52) |
| `0.0.27.post2` | `3.10` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp310-cp310-win_amd64.whl#sha256=b6080d3f247972af194bfe0bb89908904c15c43ed4ab96bda3038f55cd8ac071) |
| `0.0.27` | `3.10` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp310-cp310-win_amd64.whl#sha256=bef8100b1c53cdb5f884414b7daea0cec83966d977a70cbb7947786e473a4a1b) |
| `0.0.27.post1` | `3.10` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp310-cp310-win_amd64.whl#sha256=4a7148f08a1d45bdb27ef0c965cfcd42d4284d2f39d3fe47aa0e08060028353e) |
| `0.0.27.post2` | `3.10` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp310-cp310-win_amd64.whl#sha256=cd476c23fea18aa7298753c031c4827a544d919ee542cec771c01bc824d0127d) |
| `0.0.27` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp311-cp311-win_amd64.whl#sha256=d4c1d6eeb9ecb7ecfab7747346f6e38b16c3d642fa67f44d038867c0419f2e3b) |
| `0.0.27.post1` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp311-cp311-win_amd64.whl#sha256=3bac6bf0160c3b01bda9589eac891a4b1012cf5e8e63f20516e9c906ddc4b52b) |
| `0.0.27.post2` | `3.11` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp311-cp311-win_amd64.whl#sha256=04225739672b3096dd137388d176370cb7e5e0b934ac0defd0031e4ad941bee7) |
| `0.0.27` | `3.11` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp311-cp311-win_amd64.whl#sha256=93a41717c6edbfda4ca55a583d6d0a3e0726262ffa7f7f26ab439d84a7c482b9) |
| `0.0.27.post1` | `3.11` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp311-cp311-win_amd64.whl#sha256=15ff2f6dedbe112cdd8afc6a0fc7f5addfc2c3ed6a2b3db77b9789141b5c2a7c) |
| `0.0.27.post2` | `3.11` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp311-cp311-win_amd64.whl#sha256=7a26febb550b642c7da9864b6a46ccb89461571d27cfef54f7a252f03060d07c) |
| `0.0.27` | `3.12` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp312-cp312-win_amd64.whl#sha256=be9d5e849e3249332f843a8c871177c540521b60d3265fb84f9215cde1f919c0) |
| `0.0.27.post1` | `3.12` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp312-cp312-win_amd64.whl#sha256=c78b510a6d8e575e37c32e333cc08938fe161e733a684dd927eeb4c38ba526b6) |
| `0.0.27.post2` | `3.12` | `2.0-2.4` | `11.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp312-cp312-win_amd64.whl#sha256=ffad418be192becf08413e3cd66d1c9ce20fecd8bdb61a05cddb4f0139165fa4) |
| `0.0.27` | `3.12` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp312-cp312-win_amd64.whl#sha256=eb2ca11ee4f189f96ac10698e81aeec7dfe157c4180bb6a88e37ad50b14c7d7d) |
| `0.0.27.post1` | `3.12` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp312-cp312-win_amd64.whl#sha256=cb386f192ef6b22959a02c0a8d5382835b55723d88f10bf3ce88be88dc0a08ad) |
| `0.0.27.post2` | `3.12` | `2.1-2.5` | `12.1` | PyTorch | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp312-cp312-win_amd64.whl#sha256=0454ba745babf43500320b1d171ef4e44dec38f279fab9df1710ca5ce44a749c) |
| `0.0.28.post1` | `3.8` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp38-cp38-win_amd64.whl#sha256=a4e3a1c5647b50f608c4b40a3b5254573f45788c80a1df9775bd122c5f8cb667) |
| `0.0.28.post1` | `3.9` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp39-cp39-win_amd64.whl#sha256=9ffd82ffa699cb17286b44d150165e2bc63f9dea89ce245ee777372149c0aafc) |
| `0.0.28.post2` | `3.9` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post2-cp39-cp39-win_amd64.whl#sha256=00dffa2073e507025919d44e19d91ea11fd5b149cb9967042f9d6772a15cbe1c) |
| `0.0.28.post3` | `3.9` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post3-cp39-cp39-win_amd64.whl#sha256=f2d3d2d5ed96a66bee582bbedaaf53a4933fcfb293140f14c573ec4422cafc26) |
| `0.0.28.post1` | `3.10` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp310-cp310-win_amd64.whl#sha256=1b20e753feac2706b16be5cc6631a30a0200f16e5142704cb26cc1454a7968f9) |
| `0.0.28.post2` | `3.10` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post2-cp310-cp310-win_amd64.whl#sha256=a4792ce65c7dc8a53cded78f30d90367327807453b41e2612927b3f83d3bb67e) |
| `0.0.28.post3` | `3.10` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post3-cp310-cp310-win_amd64.whl#sha256=a69ef5e54156e4a8e82c52e96f38c0d5e4f5a1a9401112f7f6c880a53d54ba5b) |
| `0.0.28.post1` | `3.11` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp311-cp311-win_amd64.whl#sha256=16b6558d50ee174ec41d3dde6d694fbad1f89ebb95d4f8c2a552d9fea7d3b9be) |
| `0.0.28.post2` | `3.11` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post2-cp311-cp311-win_amd64.whl#sha256=852f1fa29d68a8eca8d7a100f95f5ca663c5ceda3f2060b7f00d390145f379c9) |
| `0.0.28.post3` | `3.11` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post3-cp311-cp311-win_amd64.whl#sha256=a0a7e437438de51bfcc1ebcb6f6167989e90d8b1d77a30b6fe4b21ce5b094a2e) |
| `0.0.28.post1` | `3.12` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp312-cp312-win_amd64.whl#sha256=ae863a42667c65b470c390527ab09adabd0270e1ba1c063a9df832f32962984a) |
| `0.0.28.post2` | `3.12` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post2-cp312-cp312-win_amd64.whl#sha256=a8f52e4519640f58c92a2b1e1ad0e1c479b8406eb50f56920d97c3143039f0d2) |
| `0.0.28.post3` | `3.12` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post3-cp312-cp312-win_amd64.whl#sha256=3a3a0b8b12fadff6a111effcdc3573c6a584a8d71fbd5ead77999fec658ab919) |
| `0.0.29` | `3.9` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29-cp39-cp39-win_amd64.whl#sha256=0477735b8b3123c8a8a0a82fe1e42a42f68860b8d18ca1120695ef32e5179cdd) |
| `0.0.29.post1` | `3.9` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post1-cp39-cp39-win_amd64.whl#sha256=c23e82f232ff88fcf13b8ebb2c48d1c4f3f8d12640b8e3e82d671db5182d4e1a) |
| `0.0.29.post2` | `3.9` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post2-cp39-cp39-win_amd64.whl#sha256=eb73626de82953fa7673a19ddcff3ef37d5de5f4e3230fe18dfd99c52460c55d) |
| `0.0.29.post3` | `3.9` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post3-cp39-cp39-win_amd64.whl#sha256=14cb310fa78fdbe68772ce55e624b6a75d5766b2450030da49baa61112b801f1) |
| `0.0.29.post3` | `3.9` | `2.5-2.6` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp39-cp39-win_amd64.whl#sha256=800972a992d107ae835d5ac921a2ab4314db724b9063e6c9bd8920589973acfa) |
| `0.0.29` | `3.10` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29-cp310-cp310-win_amd64.whl#sha256=1afa261d5143636140b1749638d89ac21a0d04596c8ee1efd0b2e7ea2be28bff) |
| `0.0.29.post1` | `3.10` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post1-cp310-cp310-win_amd64.whl#sha256=b2e55d3209b95f702fb17caecd58c890192548941bbbee72f74aacb0d7c7690e) |
| `0.0.29.post2` | `3.10` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post2-cp310-cp310-win_amd64.whl#sha256=2eed954ce0491d379f19ea38796027d367e259a90d1fcc9f4166331c1c27ce87) |
| `0.0.29.post3` | `3.10` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post3-cp310-cp310-win_amd64.whl#sha256=34f13d69ad9404e44ae11169e99842c3fccdc2c75b1fc4831a70c78392d990db) |
| `0.0.29.post3` | `3.10` | `2.5-2.6` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp310-cp310-win_amd64.whl#sha256=0c95e6fdb60e360801bc851a0e2b5b1fcfa8056d547a074a8823a49db01ba3b0) |
| `0.0.29` | `3.11` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29-cp311-cp311-win_amd64.whl#sha256=c4ed5142cd19ba4723fa4dcf532229fbdbd9617a340450c06d7a9d9132aab154) |
| `0.0.29.post1` | `3.11` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post1-cp311-cp311-win_amd64.whl#sha256=dc3aea9f8a3d239f75cc218edb7fbd69f77817e195bdc1d734c43a6e68dbf589) |
| `0.0.29.post2` | `3.11` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post2-cp311-cp311-win_amd64.whl#sha256=eb1db57f05b595ed9f1d0f8cc83a8e54d2c0737a16982238a01e93bdd0f2a4f5) |
| `0.0.29.post3` | `3.11` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post3-cp311-cp311-win_amd64.whl#sha256=00f2dfd94c894ff6372e21bee3f09e96bce75b55649df366649c43f049eb7a1e) |
| `0.0.29.post3` | `3.11` | `2.5-2.6` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp311-cp311-win_amd64.whl#sha256=5128b3a90c305a506cc95b5879d39c5bd931137108e2cadc2c3c54ef5c8a2390) |
| `0.0.29` | `3.12` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29-cp312-cp312-win_amd64.whl#sha256=e4a1788368db4857269289772678f6c97252a9bc31ae2083517e124b6a82c086) |
| `0.0.29.post1` | `3.12` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post1-cp312-cp312-win_amd64.whl#sha256=9ef5f35330dd6b54f7457a888db07aa36a56935c5d1dc4e1a9f1909bbaa3ac4d) |
| `0.0.29.post2` | `3.12` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post2-cp312-cp312-win_amd64.whl#sha256=a3ddb47abce3810d3928e8f48b290c0423c7939764a217c2b35ac8124a3cf641) |
| `0.0.29.post3` | `3.12` | `2.4-2.6` | `12.4` | PyTorch | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post3-cp312-cp312-win_amd64.whl#sha256=3706eca371767ff9709595185910d809fc817ec3cf4234ef44d70d2b8844d7e2) |
| `0.0.29.post3` | `3.12` | `2.5-2.6` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp312-cp312-win_amd64.whl#sha256=2e658e2b2c45229e5c74d527055b51616d24f8bac243dbf1b2817ce525b9d8ba) |
| `0.0.30` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.30-cp39-cp39-win_amd64.whl#sha256=9ce1634798cb96643f077acbced80f985e3cdab12cf468851057ed31cab0bdab) |
| `0.0.30` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp39-cp39-win_amd64.whl#sha256=7ae83a603b5887694fba4564b1e4b37e68d0a4cb1f424332c86eb834fa1347f2) |
| `0.0.30` | `3.10` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.30-cp310-cp310-win_amd64.whl#sha256=9e54eed6080e65455213174ad6b26c5e361715ca2d52759fde26055188802d92) |
| `0.0.30` | `3.10` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp310-cp310-win_amd64.whl#sha256=894d0d4926c0e984b61d0d260f43495085f1e2300332bb76520735a6e6279922) |
| `0.0.30` | `3.11` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.30-cp311-cp311-win_amd64.whl#sha256=7b2e2aa615bce02ac20d58232b0e17304c62ec533ac0db2040a948df0155858d) |
| `0.0.30` | `3.11` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp311-cp311-win_amd64.whl#sha256=8b639361742031783488bfdcce5df64b0d713f30ac573e2dabc453de3948b4ac) |
| `0.0.30` | `3.12` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.30-cp312-cp312-win_amd64.whl#sha256=8549ca30700d70dae904ec4407c6188cd73fd551e585f862c1d3aca3b7bc371c) |
| `0.0.30` | `3.12` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp312-cp312-win_amd64.whl#sha256=097610300c1498f3d26823a77b32825e25f0ecb35ce1d7a12e5cdab5c7e81e99) |
| `0.0.31` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.31-cp39-abi3-win_amd64.whl#sha256=23331bdb9831ba0df96f55258537ca0df7ad888efc75cea97a0de79b5e2291c4) |
| `0.0.31.post1` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.31.post1-cp39-abi3-win_amd64.whl#sha256=294c30125442f5a84964e5b87b3cd5e83b87053896a13bbfee17c0043ee66e62) |
| `0.0.31` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.31-cp39-abi3-win_amd64.whl#sha256=88e145ec5c846db79046625b388a146a18968ca87a7a1c02843acba40ddf1d6a) |
| `0.0.31.post1` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.31.post1-cp39-abi3-win_amd64.whl#sha256=cbe0db2fcb8ec68f7bac0f13ee71450452506857e375be34001b339947369e33) |
| `0.0.32.post1` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.32.post1-cp39-abi3-win_amd64.whl#sha256=81f39be9581b978685d38d6165afc16046e072511a7c1f49fdba4c6c76852e36) |
| `0.0.32.post2` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.32.post2-cp39-abi3-win_amd64.whl#sha256=f6634c152bd84ae59f5ff1db147576973d8b38f0286d03c35e9ae5519e5dd792) |
| `0.0.32.post1` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.32.post1-cp39-abi3-win_amd64.whl#sha256=feb452bc2c8731da1c5d0e2e4536ba95bb214f77b41e91f24443c74d6f98a126) |
| `0.0.32.post2` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.32.post2-cp39-abi3-win_amd64.whl#sha256=87fa13f4b406ed640554cea6687d0020b496bd6b446ca17d24f9438a079e6f09) |
| `0.0.32.post1` | `3.9` | `2.8-2.9` | `12.9` | PyTorch | [Link](https://download.pytorch.org/whl/cu129/xformers-0.0.32.post1-cp39-abi3-win_amd64.whl) |
| `0.0.32.post2` | `3.9` | `2.8-2.9` | `12.9` | PyTorch | [Link](https://download.pytorch.org/whl/cu129/xformers-0.0.32.post2-cp39-abi3-win_amd64.whl) |
| `0.0.33` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.33-cp39-abi3-win_amd64.whl#sha256=958d1475199ffad3776c3e8d72b84ba1242d11a038ec0435e4e18c9cb648783b) |
| `0.0.33.post1` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.33.post1-cp39-abi3-win_amd64.whl#sha256=6be529f90cacac9279913e8c738f2b6f260a54e2ae975f0f17f1538cc1669635) |
| `0.0.33.post2` | `3.9` | `2.5+` | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.33.post2-cp39-abi3-win_amd64.whl#sha256=c1142f7418ff5e501675c52a7a87bcd2d085134f45fec80dd18045c0528703fc) |
| `0.0.33` | `3.9` | `2.9+` | `13.0` | PyTorch | [Link](https://download.pytorch.org/whl/cu130/xformers-0.0.33-cp39-abi3-win_amd64.whl) |
| `0.0.33.post1` | `3.9` | `2.9+` | `13.0` | PyTorch | [Link](https://download.pytorch.org/whl/cu130/xformers-0.0.33.post1-cp39-abi3-win_amd64.whl) |
| `0.0.33.post2` | `3.9` | `2.9+` | `13.0` | PyTorch | [Link](https://download.pytorch.org/whl/cu130/xformers-0.0.33.post2-cp39-abi3-win_amd64.whl) |
| `0.0.33` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.33-cp39-abi3-win_amd64.whl#sha256=d5635ceac32c8216744a18fb328c0eafdcdb45aaab3de415edf9b1caf6fa9dcc) |
| `0.0.33.post1` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.33.post1-cp39-abi3-win_amd64.whl#sha256=e20729ca1647d53f86143bd57451af953bb78e72677548c972cd016238a066e3) |
| `0.0.33.post2` | `3.9` | `2.7-2.9` | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.33.post2-cp39-abi3-win_amd64.whl#sha256=4a0a59a0c698a483f13ecad967dbbe71386827985e80cc373bec4cdf9aed59cd) |
| `0.0.34` | `3.9` | — | `12.6` | PyTorch | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.34-cp39-abi3-win_amd64.whl#sha256=d8eda7f3e36862251b4e17720e1f1330056e4cd7279f1ed7c3ef79759b2a1017) |
| `0.0.34` | `3.9` | — | `12.8` | PyTorch | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.34-cp39-abi3-win_amd64.whl#sha256=941979e890dd18e26f9860daa83acb706e658345d18511a962f909067331cc19) |
| `0.0.34` | `3.9` | — | `13.0` | PyTorch | [Link](https://download.pytorch.org/whl/cu130/xformers-0.0.34-cp39-abi3-win_amd64.whl) |
<!-- END_XFORMERS_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-sageattention"></a>
### ⚙️ SageAttention
精准且高效的注意力机制，通过平滑量化大幅降低显存占用，同时保持精度。
*   **官方仓库**： [thu-ml/SageAttention](https://github.com/thu-ml/SageAttention)
*   **预编译来源**： <!-- START_SAGEATTENTION_SOURCES -->[Wildminder](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)<!-- END_SAGEATTENTION_SOURCES -->

<details>
  <summary>展开已收录的 SageAttention</summary>

<!-- START_SAGEATTENTION2_TABLE -->
| Package Version | Python Ver | PyTorch Ver | CUDA Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|
| `2.1.1` | `3.12` | `2.6.0` | `12.6` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.1.1%2Bcu126torch2.6.0-cp312-cp312-win_amd64.whl) |
| `2.1.1` | `3.12` | `2.8.0` | `12.8` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.1.1%2Bcu128torch2.8.0-cp312-cp312-win_amd64.whl) |
<!-- END_SAGEATTENTION2_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-sageattention-22-sageattention2"></a>
### ⚙️ SageAttention 2.2 (SageAttention2++)
SageAttention 的升级版本，引入更先进的量化策略和优化算法，显存节省更多，速度更快。
*   **官方仓库**： [thu-ml/SageAttention](https://github.com/thu-ml/SageAttention)
*   **预编译来源**： <!-- START_SAGEATTENTION22_SOURCES -->[Wildminder](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)、[Eddy](https://huggingface.co/eddy1111111/sageattention-2.2.0-cp312-270-cu128-cp312-win_amd64/tree/main)<!-- END_SAGEATTENTION22_SOURCES -->
> [!NOTE]
> 仅支持 CUDA ≥ 12.8，因此需搭配 PyTorch ≥ 2.7。

<details>
  <summary>展开已收录的 SageAttention 2++</summary>

<!-- START_SAGEATTENTION22_TABLE -->
| Package Version | Python Ver | PyTorch Ver | CUDA Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|
| `2.2.0` | `3.12` | `2.7.0` | `12.8` | Eddy | [Link](https://huggingface.co/eddy1111111/sageattention-2.2.0-cp312-270-cu128-cp312-win_amd64/blob/main/sageattention-2.2.0-cp312-270-cu128-cp312-win_amd64.whl) |
| `2.2.0` | `3.12` | `2.9.0` | `12.8` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0%2Bcu128torch2.9.0cxx11abi1-cp312-cp312-win_amd64.whl) |
| `2.2.0.post3` | `3.12` | `2.10.0` | `12.8` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0.post3%2Bcu128torch2.10.0-cp312-cp312-win_amd64.whl) |
| `2.2.0.post3` | `3.12` | `2.10.0` | `13.0` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/sageattention-2.2.0.post3%2Bcu130torch2.10.0-cp312-cp312-win_amd64.whl) |
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
*   **预编译来源**： <!-- START_SAGEATTENTION3_SOURCES -->[Eddy](https://huggingface.co/eddy1111111/sageattention-2.2.0-cp312-270-cu128-cp312-win_amd64/tree/main)<!-- END_SAGEATTENTION3_SOURCES -->
> [!NOTE]
> SageAttention3 不保證所有型號的無損加速。對於其他影片產生模型,我們建議在某些圖層或時間步長中選擇性地使用 SageAttention2++

<details>
  <summary>展开已收录的 SageAttention 3</summary>

<!-- START_SAGEATTENTION3_TABLE -->
| Package Version | Python Ver | PyTorch Ver | CUDA Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|
| `1.0.0` | `3.12` | `2.8.0` | `12.8` | Eddy | [Link](https://huggingface.co/eddy1111111/sageattention-2.2.0-cp312-270-cu128-cp312-win_amd64/resolve/main/sageattn3-1.0.0-cp312-cp312-win_amd64.whl) |
<!-- END_SAGEATTENTION3_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-spargeattn"></a>
### ⚙️ SpargeAttn
稀疏注意力机制，通过智能跳过不重要的计算来加速推理，适用于长上下文场景。
*   **官方仓库**： [thu-ml/SpargeAttn](https://github.com/thu-ml/SpargeAttn)
*   **预编译来源**： <!-- START_SPARGEATTN_SOURCES --><!-- END_SPARGEATTN_SOURCES -->

<details>
  <summary>展开已收录的 SpargeAttn</summary>
  
<!-- START_SPARGEATTN_TABLE -->
| Package Version | PyTorch Ver | CUDA Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|
<!-- END_SPARGEATTN_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-nunchaku"></a>
### ⚙️ Nunchaku
MIT 开发的 Transformer 推理加速库，专注于提升解码速度和吞吐量。
*   **官方仓库**： [mit-han-lab/nunchaku](https://github.com/mit-han-lab/nunchaku/releases)
*   **预编译来源**： <!-- START_NUNCHAKU_SOURCES -->[Wildminder](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)<!-- END_NUNCHAKU_SOURCES -->

<details>
  <summary>展开已收录的 Nunchaku</summary>

<!-- START_NUNCHAKU_TABLE -->
| Package Version | Python Ver | PyTorch Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|:---:|
| `0.3.2` | `3.12` | `2.9` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/nunchaku-0.3.2%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `3.12` | `2.9` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/nunchaku-1.0.1%2Bcu128torch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `3.12` | `2.9` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/nunchaku-1.0.1%2Bcu130torch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `3.13` | `2.9` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/nunchaku-1.0.1%2Bcu128torch2.9-cp313-cp313-win_amd64.whl) |
| `1.0.1` | `3.13` | `2.9` | Wildminder | [Link](https://huggingface.co/Wildminder/AI-windows-whl/blob/main/nunchaku-1.0.1%2Bcu130torch2.9-cp313-cp313-win_amd64.whl) |
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
*   **Windows Fork**： <!-- START_TRITON_SOURCES --><!-- END_TRITON_SOURCES -->
*   **安装命令**： `pip install -U "triton-windows<3.6"`

<details>
  <summary>展开已收录的 Triton</summary>

<!-- START_TRITON_TABLE -->
| Package Version | Python Ver | Source | Download Link |
|:---:|:---:|:---:|:---:|
<!-- END_TRITON_TABLE -->
</details>
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>
<hr />

<a id="️-bitsandbytes"></a>
### ⚙️ bitsandbytes
轻量级 CUDA 算子库，提供 8-bit 优化器和 LLM 量化支持，大幅降低显存需求。
*   **官方仓库**： [bitsandbytes-foundation/bitsandbytes](https://github.com/bitsandbytes-foundation/bitsandbytes)
*   **预编译来源**： <!-- START_BITSANDBYTES_SOURCES --><!-- END_BITSANDBYTES_SOURCES -->

<details>
  <summary>展开已收录的 bitsandbytes</summary>

<!-- START_BITSANDBYTES_TABLE -->
| Package Version | Source | Download Link |
|:---:|:---:|:---:|
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











