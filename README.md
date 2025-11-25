<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->
<!-- PROJECT LOGO -->
<a id="readme-top"></a>
<div align="center">
  <h1 align="center">Windows AI Wheelhouse</h1>

<img src="https://github.com/BradPita/images/blob/main/WinAiWheelhouse.png" alt=">Windows AI Wheelhouse logo">

  <p align="center">
    面向 Windows 平台的 AI 预编译 Python 轮子合集
    <br />
    <br />
    <a href="https://github.com/BradPita/Win-AI-Wheelhouse/issues/new?labels=bug&template=bug-report---.md">报告失效链接</a>
    ·
    <a href="https://github.com/BradPita/Win-AI-Wheelhouse/issues/new?labels=enhancement&template=feature-request---.md">请求新增轮子</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>目录</summary>
  <ol>
    <li><a href="#关于项目">关于项目</a></li>
    <li>
      <a href="#快速开始">使用指南</a>
      <ul>
        <li><a href="#环境准备">环境准备</a></li>
        <li><a href="#安装示例">安装示例</a></li>
      </ul>
    </li>
    <li><a href="#可用轮子">可用轮子</a>
      <ul>
        <li><a href="#pytorch">PyTorch</a></li>
        <li><a href="#flash-attention">Flash Attention</a></li>
        <li><a href="#xformers">xformers</a></li>
        <li><a href="#sageattention">SageAttention</a></li>
        <li><a href="#natten">NATTEN</a></li>
        <li><a href="#tritonwindows-fork">Triton（Windows Fork）</a></li>
        <li><a href="#bitsandbytes">bitsandbytes</a></li>
        <li><a href="#radialattention-for-comfyui">RadialAttention</a></li>
      </ul>
    </li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
<a id="项目愿景"></a>
## 项目愿景

在 Windows 平台上，AI 爱好者常常面临一个共同的挑战：**那些如 `flash-attention`、`xformers` 等高性能的 Python 库，往往缺乏官方提供的 Windows 预编译 `.whl` 包。** 这使得从源码构建成为一个耗时且易错的过程，阻碍了许多创新想法的迅速实现。

**`Win-AI-Wheelhouse`** 致力于解决这一痛点。我们希望建立一个**集中、持续更新的 `.whl` 文件直链清单**，让 Windows 上的 PyTorch 用户（尤其是 **ComfyUI 社区**的成员）能够告别繁琐的编译流程，将宝贵的时间投入到 AI 创作与探索之中。

## 致敬与启发

本项目深受 wildminder 的 [AI-windows-whl](https://github.com/wildminder/AI-windows-whl) 项目的启发，我们旨在延续其精神，为更广泛的 Windows AI 社区提供稳定可靠的预编译资源。

<!-- GETTING STARTED -->
<a id="快速开始"></a>
## 快速开始

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
> 在下方 [可用轮子](#可用轮子) 区域按 Python/PyTorch/CUDA 版本找到匹配行，然后复制下载链接放入 `pip install` 命令即可。

<p align="right">(<a href="#readme-top">返回顶部</a>)</p>


<!-- AVAILABLE WHEELS -->
<a id="可用轮子"></a>
## 可用轮子

以下是当前收录的包。

### PyTorch
万物根基，优先走官方通道安装。
*   **官方安装页面**： [https://pytorch.org/get-started/locally/](https://pytorch.org/get-started/locally/)

为了方便，在 Linux/WSL（NVIDIA GPU）环境下列出常用命令；其他配置（CPU、macOS、ROCm）请参考官网指引。

#### 稳定版（2.9.1）
多数用户推荐使用该版本。

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

**Torchaudio**
<!-- START_TORCHAUDIO_TABLE -->
| Package Version | PyTorch Ver | Python Ver | CUDA Ver | CXX11 ABI | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|
| `2.8.0a0` | `2.10.0` | `3.13` | `13.0` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/torchaudio-2.8.0a0%2Bcu130torch2.10.0cxx11abi1-cp313-cp313-win_amd64.whl?download=true) |
| `2.8.0a0` | `2.9.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/torchaudio-2.8.0a0%2Bcu128torch2.9.0cxx11abi1-cp312-cp312-win_amd64.whl?download=true) |
<!-- END_TORCHAUDIO_TABLE -->

****

### Flash Attention
高性能注意力实现。
*   **官方仓库**： [Dao-AILab/flash-attention](https://github.com/Dao-AILab/flash-attention)
*   **预编译来源**： [lldacing 的 HF](https://huggingface.co/lldacing/flash-attention-windows-wheel/tree/main)、[Wildminder 的 HF](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)、[mjun0812 GitHub](https://github.com/mjun0812/flash-attention-prebuild-wheels)

<!-- START_FLASHATTENTION_TABLE -->
| Package Version | PyTorch Ver | Python Ver | CUDA Ver | CXX11 ABI | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|
| `2.5.9` | `2.4` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.4-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `2.4` | `3.10` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.4-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `2.4` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.4-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `2.4` | `3.11` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.4-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `2.4` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.4-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `2.4` | `3.12` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.4-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `2.5` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.5-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `2.5` | `3.10` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.5-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `2.5` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.5-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `2.5` | `3.11` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.5-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `2.5` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.5-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `2.5` | `3.12` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.5-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `2.6` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.6-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `2.6` | `3.10` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.6-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `2.6` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.6-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `2.6` | `3.11` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.6-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `2.6` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.6-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `2.6` | `3.12` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.6-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `2.7` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.7-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `2.7` | `3.10` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.7-cp310-cp310-win_amd64.whl) |
| `2.5.9` | `2.7` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.7-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `2.7` | `3.11` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.7-cp311-cp311-win_amd64.whl) |
| `2.5.9` | `2.7` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu124torch2.7-cp312-cp312-win_amd64.whl) |
| `2.5.9` | `2.7` | `3.12` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.5.9%2Bcu128torch2.7-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `2.4` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.4-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `2.4` | `3.10` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.4-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `2.4` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.4-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `2.4` | `3.11` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.4-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `2.4` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.4-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `2.4` | `3.12` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.4-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `2.5` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.5-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `2.5` | `3.10` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.5-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `2.5` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.5-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `2.5` | `3.11` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.5-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `2.5` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.5-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `2.5` | `3.12` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.5-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `2.6` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.6-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `2.6` | `3.10` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.6-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `2.6` | `3.11` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.1/flash_attn-2.6.3%2Bcu126torch2.6-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `2.6` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.6-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `2.6` | `3.11` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.6-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `2.6` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.6-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `2.6` | `3.12` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.6-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `2.7` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.7-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `2.7` | `3.10` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.7-cp310-cp310-win_amd64.whl) |
| `2.6.3` | `2.7` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.7-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `2.7` | `3.11` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.7-cp311-cp311-win_amd64.whl) |
| `2.6.3` | `2.7` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu124torch2.7-cp312-cp312-win_amd64.whl) |
| `2.6.3` | `2.7` | `3.12` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.6.3%2Bcu128torch2.7-cp312-cp312-win_amd64.whl) |
| `2.7.0.post2` | `2.4.0` | `3.10` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.0.post2%2Bcu124torch2.4.0cxx11abiFALSE-cp310-cp310-win_amd64.whl?download=true) |
| `2.7.0.post2` | `2.4.0` | `3.11` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.0.post2%2Bcu124torch2.4.0cxx11abiFALSE-cp311-cp311-win_amd64.whl?download=true) |
| `2.7.0.post2` | `2.4.0` | `3.12` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.0.post2%2Bcu124torch2.4.0cxx11abiFALSE-cp312-cp312-win_amd64.whl?download=true) |
| `2.7.0.post2` | `2.4.1` | `3.10` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.0.post2%2Bcu124torch2.4.1cxx11abiFALSE-cp310-cp310-win_amd64.whl?download=true) |
| `2.7.0.post2` | `2.4.1` | `3.11` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.0.post2%2Bcu124torch2.4.1cxx11abiFALSE-cp311-cp311-win_amd64.whl?download=true) |
| `2.7.0.post2` | `2.4.1` | `3.12` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.0.post2%2Bcu124torch2.4.1cxx11abiFALSE-cp312-cp312-win_amd64.whl?download=true) |
| `2.7.0.post2` | `2.5.0` | `3.11` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.0.post2%2Bcu124torch2.5.0cxx11abiFALSE-cp311-cp311-win_amd64.whl?download=true) |
| `2.7.0.post2` | `2.5.0` | `3.12` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.0.post2%2Bcu124torch2.5.0cxx11abiFALSE-cp312-cp312-win_amd64.whl?download=true) |
| `2.7.0.post2` | `2.5.1` | `3.11` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.0.post2%2Bcu124torch2.5.1cxx11abiFALSE-cp311-cp311-win_amd64.whl?download=true) |
| `2.7.0.post2` | `2.5.1` | `3.12` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.0.post2%2Bcu124torch2.5.1cxx11abiFALSE-cp312-cp312-win_amd64.whl?download=true) |
| `2.7.4` | `2.4` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.4-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `2.4` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.4-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `2.5` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.5-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `2.5` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.5-cp311-cp311-win_amd64.whl) |
| `2.7.4` | `2.5` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.5-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `2.5.1` | `3.10` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu124torch2.5.1cxx11abiFALSE-cp310-cp310-win_amd64.whl?download=true) |
| `2.7.4` | `2.6` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.6-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `2.6` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.6-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `2.6.0` | `3.10` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu124torch2.6.0cxx11abiFALSE-cp310-cp310-win_amd64.whl?download=true) |
| `2.7.4` | `2.6.0` | `3.10` | `12.6` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu126torch2.6.0cxx11abiFALSE-cp310-cp310-win_amd64.whl?download=true) |
| `2.7.4` | `2.6.0` | `3.11` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu124torch2.6.0cxx11abiFALSE-cp311-cp311-win_amd64.whl?download=true) |
| `2.7.4` | `2.6.0` | `3.11` | `12.6` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu126torch2.6.0cxx11abiFALSE-cp311-cp311-win_amd64.whl?download=true) |
| `2.7.4` | `2.6.0` | `3.12` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu124torch2.6.0cxx11abiFALSE-cp312-cp312-win_amd64.whl?download=true) |
| `2.7.4` | `2.6.0` | `3.12` | `12.6` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu126torch2.6.0cxx11abiFALSE-cp312-cp312-win_amd64.whl?download=true) |
| `2.7.4` | `2.7` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.7-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `2.7` | `3.10` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.7.4%2Bcu128torch2.7-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `2.7` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.7-cp311-cp311-win_amd64.whl) |
| `2.7.4` | `2.7` | `3.11` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.9/flash_attn-2.7.4%2Bcu128torch2.7-cp311-cp311-win_amd64.whl) |
| `2.7.4` | `2.7` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.3.9/flash_attn-2.7.4%2Bcu124torch2.7-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `2.7` | `3.12` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.7.4%2Bcu128torch2.7-cp312-cp312-win_amd64.whl) |
| `2.7.4` | `2.8` | `3.10` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.7.4%2Bcu128torch2.8-cp310-cp310-win_amd64.whl) |
| `2.7.4` | `2.8` | `3.11` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.7.4%2Bcu128torch2.8-cp311-cp311-win_amd64.whl) |
| `2.7.4` | `2.8` | `3.12` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.7.4%2Bcu128torch2.8-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `2.5` | `3.10` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.5-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `2.5` | `3.11` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.5-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `2.6` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.6-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `2.6` | `3.10` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.6-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `2.6` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.6-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `2.6` | `3.11` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.6-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `2.6` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.6-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `2.6` | `3.12` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.6-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `2.6` | `3.13` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.6-cp313-cp313-win_amd64.whl) |
| `2.7.4.post1` | `2.7` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.7-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `2.7` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.7-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `2.7` | `3.11` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.7-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `2.7` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.7-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `2.7` | `3.12` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.7-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `2.7` | `3.13` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.7-cp313-cp313-win_amd64.whl) |
| `2.7.4.post1` | `2.7` | `3.13` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.7-cp313-cp313-win_amd64.whl) |
| `2.7.4.post1` | `2.7.0` | `3.10` | `12.8` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4.post1%2Bcu128torch2.7.0cxx11abiFALSE-cp310-cp310-win_amd64.whl?download=true) |
| `2.7.4.post1` | `2.7.0` | `3.11` | `12.8` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4.post1%2Bcu128torch2.7.0cxx11abiFALSE-cp311-cp311-win_amd64.whl?download=true) |
| `2.7.4.post1` | `2.7.0` | `3.12` | `12.8` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4.post1%2Bcu128torch2.7.0cxx11abiFALSE-cp312-cp312-win_amd64.whl?download=true) |
| `2.7.4.post1` | `2.8` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.8-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `2.8` | `3.11` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.8-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `2.8` | `3.12` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.8-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `2.8` | `3.13` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.8-cp313-cp313-win_amd64.whl) |
| `2.7.4.post1` | `2.8` | `3.13` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.8-cp313-cp313-win_amd64.whl) |
| `2.7.4.post1` | `2.8.0` | `3.10` | `12.8` | ✓ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4.post1%2Bcu128torch2.8.0cxx11abiTRUE-cp310-cp310-win_amd64.whl?download=true) |
| `2.7.4.post1` | `2.8.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.7.4.post1%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.7.4.post1` | `2.9` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.9-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `2.9` | `3.10` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.9-cp310-cp310-win_amd64.whl) |
| `2.7.4.post1` | `2.9` | `3.11` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.9-cp311-cp311-win_amd64.whl) |
| `2.7.4.post1` | `2.9` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.9-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `2.9` | `3.12` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.9-cp312-cp312-win_amd64.whl) |
| `2.7.4.post1` | `2.9` | `3.13` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu124torch2.9-cp313-cp313-win_amd64.whl) |
| `2.7.4.post1` | `2.9` | `3.13` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.7.4.post1%2Bcu126torch2.9-cp313-cp313-win_amd64.whl) |
| `2.8.0.post2` | `2.8.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.0.post2%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.1` | `2.8.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.1%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.2` | `2.6` | `3.13` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.12/flash_attn-2.8.2%2Bcu124torch2.6-cp313-cp313-win_amd64.whl) |
| `2.8.2` | `2.7` | `3.10` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.8.2%2Bcu128torch2.7-cp310-cp310-win_amd64.whl) |
| `2.8.2` | `2.7` | `3.11` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.8.2%2Bcu128torch2.7-cp311-cp311-win_amd64.whl) |
| `2.8.2` | `2.7` | `3.12` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.8.2%2Bcu128torch2.7-cp312-cp312-win_amd64.whl) |
| `2.8.2` | `2.7` | `3.13` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.12/flash_attn-2.8.2%2Bcu124torch2.7-cp313-cp313-win_amd64.whl) |
| `2.8.2` | `2.7` | `3.13` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.12/flash_attn-2.8.2%2Bcu126torch2.7-cp313-cp313-win_amd64.whl) |
| `2.8.2` | `2.8` | `3.10` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.8.2%2Bcu128torch2.8-cp310-cp310-win_amd64.whl) |
| `2.8.2` | `2.8` | `3.11` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.8.2%2Bcu128torch2.8-cp311-cp311-win_amd64.whl) |
| `2.8.2` | `2.8` | `3.12` | `12.8` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.10/flash_attn-2.8.2%2Bcu128torch2.8-cp312-cp312-win_amd64.whl) |
| `2.8.2` | `2.8` | `3.13` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.12/flash_attn-2.8.2%2Bcu124torch2.8-cp313-cp313-win_amd64.whl) |
| `2.8.2` | `2.8` | `3.13` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.12/flash_attn-2.8.2%2Bcu126torch2.8-cp313-cp313-win_amd64.whl) |
| `2.8.2` | `2.8.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.2%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.2` | `2.9.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.2%2Bcu128torch2.9.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.3` | `2.10.0` | `3.12` | `13.0` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu130torch2.10.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.3` | `2.10.0` | `3.13` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu128torch2.10.0cxx11abiTRUE-cp313-cp313-win_amd64.whl?download=true) |
| `2.8.3` | `2.10.0` | `3.13` | `13.0` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu130torch2.10.0cxx11abiTRUE-cp313-cp313-win_amd64.whl?download=true) |
| `2.8.3` | `2.5` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.5-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `2.5` | `3.10` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.5-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `2.5` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.5-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `2.5` | `3.11` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.5-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `2.5` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.5-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `2.5` | `3.12` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.5-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `2.6` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.6-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `2.6` | `3.10` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.6-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `2.6` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.6-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `2.6` | `3.11` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.6-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `2.6` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.6-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `2.6` | `3.12` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.6-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `2.6` | `3.13` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.6-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `2.6` | `3.13` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.6-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `2.7` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.7-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `2.7` | `3.10` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.7-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `2.7` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.7-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `2.7` | `3.11` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.7-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `2.7` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.7-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `2.7` | `3.12` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.7-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `2.7` | `3.13` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.7-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `2.7` | `3.13` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.7-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `2.8` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.8-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `2.8` | `3.10` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.8-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `2.8` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.8-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `2.8` | `3.11` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.8-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `2.8` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.8-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `2.8` | `3.12` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.8-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `2.8` | `3.13` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.8-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `2.8` | `3.13` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.8-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `2.8.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.3` | `2.9` | `3.10` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.9-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `2.9` | `3.10` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.9-cp310-cp310-win_amd64.whl) |
| `2.8.3` | `2.9` | `3.11` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.9-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `2.9` | `3.11` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.9-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `2.9` | `3.11` | `13.0` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu130torch2.9-cp311-cp311-win_amd64.whl) |
| `2.8.3` | `2.9` | `3.12` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.9-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `2.9` | `3.12` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.9-cp312-cp312-win_amd64.whl) |
| `2.8.3` | `2.9` | `3.13` | `12.6` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu126torch2.9-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `2.9` | `3.13` | `12.4` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu124torch2.9-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `2.9` | `3.13` | `13.0` | — | [Link](https://github.com/mjun0812/flash-attention-prebuild-wheels/releases/download/v0.4.19/flash_attn-2.8.3%2Bcu130torch2.9-cp313-cp313-win_amd64.whl) |
| `2.8.3` | `2.9.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu128torch2.9.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.3` | `2.9.0` | `3.12` | `13.0` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu130torch2.9.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.3` | `2.9.0` | `3.13` | `12.9` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu129torch2.9.0cxx11abiTRUE-cp313-cp313-win_amd64.whl?download=true) |
| `2.8.3` | `2.9.0` | `3.13` | `13.0` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu130torch2.9.0cxx11abiTRUE-cp313-cp313-win_amd64.whl?download=true) |
| `2.8.3` | `2.9.1` | `3.12` | `13.0` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu130torch2.9.1cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.3` | `2.9.1` | `3.13` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu128torch2.9.1cxx11abiTRUE-cp313-cp313-win_amd64.whl?download=true) |
| `2.8.3` | `2.9.1` | `3.13` | `13.0` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu130torch2.9.1cxx11abiTRUE-cp313-cp313-win_amd64.whl?download=true) |
<!-- END_FLASHATTENTION_TABLE -->
  
****

### xformers
内存友好的注意力及优化组件库。
*   **官方仓库**： [facebookresearch/xformers](https://github.com/facebookresearch/xformers/releases)
*   **PyTorch 官方索引**： [https://download.pytorch.org/whl/xformers/](https://download.pytorch.org/whl/xformers/)
> [!NOTE]
> 安装 PyTorch 后通常可以直接 `pip install xformers`。若失败，可在上述索引寻找与环境匹配的 wheel。

ABI3 版本可兼容 Python 3.9-3.12。

<!-- START_XFORMERS_TABLE -->
| Package Version | PyTorch Ver | Python Ver | CUDA Ver | Download Link |
|:---:|:---:|:---:|:---:|:---:|
| `0.0.22.post2` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post2%2Bcu118-cp310-cp310-win_amd64.whl#sha256=43e13660b1dd3164fc8a64f474c1dd4a17e2997856013459b1233415701fe76c) |
| `0.0.22.post2` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post2%2Bcu118-cp311-cp311-win_amd64.whl#sha256=1849b9d0fe88104d1d2aea595ce8aa23c932f7c0774ccc560b8a111c61602f36) |
| `0.0.22.post2` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post2%2Bcu118-cp38-cp38-win_amd64.whl#sha256=f33381dea46e12c1432e252447572dd06cdba88cf44444fa2aa32e337c910899) |
| `0.0.22.post2` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post2%2Bcu118-cp39-cp39-win_amd64.whl#sha256=5192b4da139ab8525d0330425878ca26b19050476af63bfd4a683c226b03ddc0) |
| `0.0.22.post3` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp310-cp310-win_amd64.whl#sha256=0ec5a4b94604280ea77819acddc605204970e002553c6c3a47101e8b454d74e9) |
| `0.0.22.post3` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp311-cp311-win_amd64.whl#sha256=f5e2085c1487ce720ff4fbabb0eafef2932cd7890893fe19ed0bbb84b31122e2) |
| `0.0.22.post3` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp38-cp38-win_amd64.whl#sha256=f405360e0e6be837604b3ffa36b85d783262773cb90f25eae0bd6f97af53ae64) |
| `0.0.22.post3` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp39-cp39-win_amd64.whl#sha256=d1ae287c67cd14fd8f638b5a499db4b8348972b4ba09c2ee7ac91bd49525d622) |
| `0.0.22.post4` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp310-cp310-win_amd64.whl#sha256=3b18c13a2f9543af7e89c60cc1dc09cf63408973162162d76243fde443a8464f) |
| `0.0.22.post4` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp311-cp311-win_amd64.whl#sha256=86a566b8ba5e2579837dd4253fd0ce42ea7b19c03d58207b7b476befd805a00c) |
| `0.0.22.post4` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp38-cp38-win_amd64.whl#sha256=7363a0884dbaad3d73b3986525704464002202967b76352442e516344a262c17) |
| `0.0.22.post4` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp39-cp39-win_amd64.whl#sha256=eea9261c8fa3d036b7f1bc5fc11869a597b7b570115758955ec3b32a5040c6bb) |
| `0.0.22.post4` | `2.1-2.5` | `3.10` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp310-cp310-win_amd64.whl#sha256=7901a41141348dd389f6cca759ebaa5480d98ecf40bb1c8c1a6cfe7b7d81413e) |
| `0.0.22.post4` | `2.1-2.5` | `3.11` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp311-cp311-win_amd64.whl#sha256=cee27b7e9ccc00d3d893cb293cab675624847ec022485c212c3ff85ddece15a6) |
| `0.0.22.post4` | `2.1-2.5` | `3.8` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp38-cp38-win_amd64.whl#sha256=b162a9a043bce9d27b715fe378f25c5756945976c430dea84a1de977ce0c0d09) |
| `0.0.22.post4` | `2.1-2.5` | `3.9` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp39-cp39-win_amd64.whl#sha256=242433f5eea7390779368e1d0d588c7dfb26cda6aa2d9743c64abda3884607eb) |
| `0.0.22.post7` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp310-cp310-win_amd64.whl#sha256=ed97fc004c16aa168004af5bee2d6b12fb33cac45a625482782812b2aefa84ec) |
| `0.0.22.post7` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp311-cp311-win_amd64.whl#sha256=f5a4c0199cd9e893e97378102be89141e8f3fae01a5df48023c8b23d13c21b27) |
| `0.0.22.post7` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp38-cp38-win_amd64.whl#sha256=fb5507d170232e201d75d53c888bc49a1f82835b61468c429a5f288220040374) |
| `0.0.22.post7` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp39-cp39-win_amd64.whl#sha256=532a2e71092b2770df6392387a69e1b65e53643308062ce30e0b018432c539da) |
| `0.0.22.post7` | `2.1-2.5` | `3.10` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp310-cp310-win_amd64.whl#sha256=fd3c88b4aa4cd5b6aa1ee162c42c649a6dd0555fd54eaed0d1158fe50f8b1517) |
| `0.0.22.post7` | `2.1-2.5` | `3.11` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp311-cp311-win_amd64.whl#sha256=5fcb0eb6eb0a6b78f6f866ea90ffbef955f8c903afd1e2fd934c1619eabb042e) |
| `0.0.22.post7` | `2.1-2.5` | `3.8` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp38-cp38-win_amd64.whl#sha256=0bf779c685c8d610d32850d886df9ae7f6c72dfa115b3fe375308bfe8e04effc) |
| `0.0.22.post7` | `2.1-2.5` | `3.9` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp39-cp39-win_amd64.whl#sha256=58af99cdec4399f57e4a77fe341bf17c26a3d65e5f526b87b5dc887ad70115ca) |
| `0.0.23` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp310-cp310-win_amd64.whl#sha256=a05811a355ce5ab5c25e964c78e9cc7fb9b03b674914c8df6d5db45a0bef3da0) |
| `0.0.23` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp311-cp311-win_amd64.whl#sha256=1e03af99f27612a0099045f835332c5ee4cb5c2df4c0dbcff73a91684a3ec8d4) |
| `0.0.23` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp38-cp38-win_amd64.whl#sha256=a7f335f6fb3d4ed6f693da8e08389c79274bef4181465f1435f6f5dd2d3615ab) |
| `0.0.23` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp39-cp39-win_amd64.whl#sha256=200173dcffb6aad82cdfe70a4948c778015898a2fa9a7434cdae4d340718978d) |
| `0.0.23` | `2.1-2.5` | `3.10` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp310-cp310-win_amd64.whl#sha256=518d866cc48fe91d055b5e89d86b4d2bec716d15f8a4babec8b2808bb4afb44a) |
| `0.0.23` | `2.1-2.5` | `3.11` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp311-cp311-win_amd64.whl#sha256=32203f4450470f5f16e719dac542f6b665f7111105dd543badf4ae5492de415e) |
| `0.0.23` | `2.1-2.5` | `3.8` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp38-cp38-win_amd64.whl#sha256=4408f2be58da163d598ff5496265c946f922269599cab45d36e65e9f42b37b5c) |
| `0.0.23` | `2.1-2.5` | `3.9` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp39-cp39-win_amd64.whl#sha256=86e078606e6ec871efea38939ec20649ef78a58d062a66d0b5d6a6bd58b51702) |
| `0.0.23.post1` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp310-cp310-win_amd64.whl#sha256=bb845f1dfe21dec3ccaf2c94adabf46bd604ac5bbfb35379340816914b1ce00a) |
| `0.0.23.post1` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp311-cp311-win_amd64.whl#sha256=8c232bccf88e19de91b545a2b29886c5684bf5d1f7014b6a3d126e481b5e01ee) |
| `0.0.23.post1` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp38-cp38-win_amd64.whl#sha256=6f3102134d300c59d31463cc12aae4864cb8dade2668bcd34198fcfd58ea08f8) |
| `0.0.23.post1` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp39-cp39-win_amd64.whl#sha256=103820665654b3e21257b1d5711b9fdda34b4a272f9de4b7c047bc4af292e60c) |
| `0.0.23.post1` | `2.1-2.5` | `3.10` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp310-cp310-win_amd64.whl#sha256=ef0744c5d1abcad7f8692b5a30ee72a71215451cbde020e2fb37af20f46ba76f) |
| `0.0.23.post1` | `2.1-2.5` | `3.11` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp311-cp311-win_amd64.whl#sha256=372995c113c3505648f0c2d2daac53a6df60a22f30eae98e47daca5efd38fe71) |
| `0.0.23.post1` | `2.1-2.5` | `3.8` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp38-cp38-win_amd64.whl#sha256=aad762aebfe7ea3f6b9132afbf5ae88cdaf87d0c377d199dfee193e1a72d0d24) |
| `0.0.23.post1` | `2.1-2.5` | `3.9` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp39-cp39-win_amd64.whl#sha256=e08e4ebbd9fbfe9545de4028b7f604d21dc4e301dc651b3fc1bb95ae6797524f) |
| `0.0.24` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp310-cp310-win_amd64.whl#sha256=9a701ee428eb1f44f854a77d70f345650e9bfc91cc73be27026f13f4a1d03bdd) |
| `0.0.24` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp311-cp311-win_amd64.whl#sha256=deb9ceac347f478e4b1ebaed969c0e0389107c268195023860d20b1504eeedbf) |
| `0.0.24` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp38-cp38-win_amd64.whl#sha256=0cf379d0a88cd3abcc6e05221a5dc9cb1b7dfac1e5a3ab366e9d5ea624f648ca) |
| `0.0.24` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp39-cp39-win_amd64.whl#sha256=c5ea36fd8e86ded344ccb82a3af92fd6e59082c1866fb30012188d62577f0654) |
| `0.0.24` | `2.1-2.5` | `3.10` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp310-cp310-win_amd64.whl#sha256=2ebacd38644e4df6a74e14fae55d561acd6d642b62819c1b8c10e07428efdad7) |
| `0.0.24` | `2.1-2.5` | `3.11` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp311-cp311-win_amd64.whl#sha256=7510268679d32475cb0f0c31d3f8b0a97ebfcd77fea2a1604516908eee0569bb) |
| `0.0.24` | `2.1-2.5` | `3.8` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp38-cp38-win_amd64.whl#sha256=dd7d65307373fcec77974775980ecd110fdc06489c4d18278a5a923afdd8dde1) |
| `0.0.24` | `2.1-2.5` | `3.9` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp39-cp39-win_amd64.whl#sha256=039f173608a37c1ff74dfd243671d0a12c9d507427f2b864373da838251fd374) |
| `0.0.25` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp310-cp310-win_amd64.whl#sha256=45c4d515e852549be73ae23004fe9e0b78531908563f41f45ec798c8199d9774) |
| `0.0.25` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp311-cp311-win_amd64.whl#sha256=c96e2226a4e9b2fb68cacb579eca85ed568cf6585d5290aa5b61c82f0a5a8822) |
| `0.0.25` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp38-cp38-win_amd64.whl#sha256=53ae4768a53a256a11755f32c10d8d690e0692e103bc7360d3f3e008bf95b84c) |
| `0.0.25` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp39-cp39-win_amd64.whl#sha256=35ef134e776bb10afd635daca281bad2b8c3eb10e553595504f155679737683c) |
| `0.0.25` | `2.1-2.5` | `3.10` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp310-cp310-win_amd64.whl#sha256=ef3dc7f65d0b25148570172647759eb3b6032c24d696b52dabd6b55164a4a1ab) |
| `0.0.25` | `2.1-2.5` | `3.11` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp311-cp311-win_amd64.whl#sha256=a62666f27a10e4e2aff49edce369bbf1f5218ff8d7f9580d33706950ddb992d7) |
| `0.0.25` | `2.1-2.5` | `3.8` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp38-cp38-win_amd64.whl#sha256=b72fc7f7222184421b63c794e1896424482ee5579d9f1d088b582560eefc3f58) |
| `0.0.25` | `2.1-2.5` | `3.9` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp39-cp39-win_amd64.whl#sha256=669adb8955585f0c30d7c1b0f6d757216c9ea0c62d625f79ebea8aa17665c8f0) |
| `0.0.25.post1` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp310-cp310-win_amd64.whl#sha256=8463057ab6c70828e7b0ef336598e8f56df90b0036549c5f560eef9d66cf25e9) |
| `0.0.25.post1` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp311-cp311-win_amd64.whl#sha256=41d84b2dea18b50275edf0909a64c34b18b71ddc594971703db4704feb300afc) |
| `0.0.25.post1` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp38-cp38-win_amd64.whl#sha256=f8c7b1a8e802d47cf833affcbf203acd62e111a656900e2b1b61d645b342c942) |
| `0.0.25.post1` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp39-cp39-win_amd64.whl#sha256=a6e43749a96663d6b69d2d801517b9d30c0931f689eafb2386e59033ef34a555) |
| `0.0.25.post1` | `2.1-2.5` | `3.10` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp310-cp310-win_amd64.whl#sha256=ddc22273f2ff06b886d9e86f17997e4f1f3074fdeb5d46bcdf50b704430df528) |
| `0.0.25.post1` | `2.1-2.5` | `3.11` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp311-cp311-win_amd64.whl#sha256=3eaf21f437c1e1a8aa126310e33b186cb6d90906b06f90759672ba9e1f61893c) |
| `0.0.25.post1` | `2.1-2.5` | `3.8` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp38-cp38-win_amd64.whl#sha256=45646a9877c6376800cb5ed4124e2f3d7baf418f75d9e21840589cf1f4fe1f8e) |
| `0.0.25.post1` | `2.1-2.5` | `3.9` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp39-cp39-win_amd64.whl#sha256=f48bbc04a916d1010b752a005d4a27c54fec181210b63d7879534455e3b53169) |
| `0.0.26` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp310-cp310-win_amd64.whl#sha256=a9b3af3c33023096fb6db0b6164c8fac069ff25d5d1fd8c88c96fa845be8f87f) |
| `0.0.26` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp311-cp311-win_amd64.whl#sha256=c121286fc5331d7929aeea4ca130ea7164149e17e23d935cb282e96b2cbf1a1d) |
| `0.0.26` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp38-cp38-win_amd64.whl#sha256=f177bbe3f2fe3eae73de22d18f0944089bfa8cfecf32c1fc606639899448288b) |
| `0.0.26` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp39-cp39-win_amd64.whl#sha256=02f814323f70ce4359666dbca2f2f244dc4312acde3ad3839b2d6c0a331c1d96) |
| `0.0.26` | `2.1-2.5` | `3.10` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp310-cp310-win_amd64.whl#sha256=2261abce21e7100fc5249d0cdbb949d51863c6bc60e121bdc27c29ab6c2a41c1) |
| `0.0.26` | `2.1-2.5` | `3.11` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp311-cp311-win_amd64.whl#sha256=b3c46089a1b6248b162b3923244a3e0dcec8746883230014c0136300cf0c2ca1) |
| `0.0.26` | `2.1-2.5` | `3.8` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp38-cp38-win_amd64.whl#sha256=aadca94d92803c4946a47df1eeac819dc7c5112d74c660886eda06e862a91268) |
| `0.0.26` | `2.1-2.5` | `3.9` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp39-cp39-win_amd64.whl#sha256=38199423eb78045a78ed68cf0f048e8d0c5f1dc6c12161b85b782bf5dc56f048) |
| `0.0.26.post1` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp310-cp310-win_amd64.whl#sha256=a8b401d4e5f3845bd277401506f62250702dedfc5cd7944e87d0bc9c30761281) |
| `0.0.26.post1` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp311-cp311-win_amd64.whl#sha256=2fd882d2dca2e5e814aede20819804041496c938fb395f00c511424ef76dd86e) |
| `0.0.26.post1` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp38-cp38-win_amd64.whl#sha256=70d72d7b61dc02463b24140c637ad3dc7281e88d90c319b26d9a2ae2f49fe1ca) |
| `0.0.26.post1` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp39-cp39-win_amd64.whl#sha256=2131fef2466cc4b3464113679aa6f701a7bc292bc623b08197fe4001369f8c40) |
| `0.0.26.post1` | `2.1-2.5` | `3.10` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp310-cp310-win_amd64.whl#sha256=e34b8dd6982077bee0c8eb2db8bc1513177201bfe0af890a4db42d8d31c966a5) |
| `0.0.26.post1` | `2.1-2.5` | `3.11` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp311-cp311-win_amd64.whl#sha256=d05c547b4ba603fc8e21fad03a342138eaaece35fe0a1692e6ee0d061ddd21ac) |
| `0.0.26.post1` | `2.1-2.5` | `3.8` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp38-cp38-win_amd64.whl#sha256=e96e2c1a11e84a6aac8386a304e3e338057c95029c82b221bf6aa1658aeacdf0) |
| `0.0.26.post1` | `2.1-2.5` | `3.9` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp39-cp39-win_amd64.whl#sha256=cf267bac8f4454db1056e4e6ff9e4df1e02b2b31d8116d50913af15fa6ae7132) |
| `0.0.27` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp310-cp310-win_amd64.whl#sha256=70d3850e0d11a78fedfba1ddce5d248544890569f7cb55737e86677158173384) |
| `0.0.27` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp311-cp311-win_amd64.whl#sha256=d4c1d6eeb9ecb7ecfab7747346f6e38b16c3d642fa67f44d038867c0419f2e3b) |
| `0.0.27` | `2.0-2.4` | `3.12` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp312-cp312-win_amd64.whl#sha256=be9d5e849e3249332f843a8c871177c540521b60d3265fb84f9215cde1f919c0) |
| `0.0.27` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp38-cp38-win_amd64.whl#sha256=a46f49ec62ce939ee1585bd8ab484be83328df5e3c64237dc22a314d46214868) |
| `0.0.27` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp39-cp39-win_amd64.whl#sha256=00d3e1e48cbfedf823113d9f43fc19aaa396d6ac7883c4b3fd1ce697d9f65d2d) |
| `0.0.27` | `2.1-2.5` | `3.10` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp310-cp310-win_amd64.whl#sha256=bef8100b1c53cdb5f884414b7daea0cec83966d977a70cbb7947786e473a4a1b) |
| `0.0.27` | `2.1-2.5` | `3.11` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp311-cp311-win_amd64.whl#sha256=93a41717c6edbfda4ca55a583d6d0a3e0726262ffa7f7f26ab439d84a7c482b9) |
| `0.0.27` | `2.1-2.5` | `3.12` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp312-cp312-win_amd64.whl#sha256=eb2ca11ee4f189f96ac10698e81aeec7dfe157c4180bb6a88e37ad50b14c7d7d) |
| `0.0.27` | `2.1-2.5` | `3.8` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp38-cp38-win_amd64.whl#sha256=d79457fd3d3b655527596e8de16787928b38ef21007bcd9fdb193c348a9516a4) |
| `0.0.27` | `2.1-2.5` | `3.9` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp39-cp39-win_amd64.whl#sha256=67ab5341c7dbfeb96450778a1cd358710c4e71566dd1115246c766d01f2d5417) |
| `0.0.27.post1` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp310-cp310-win_amd64.whl#sha256=15bdfd7e8c3a57dc6fdd97ec9482c858acd32a14861f058c2a3062f662ce3b52) |
| `0.0.27.post1` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp311-cp311-win_amd64.whl#sha256=3bac6bf0160c3b01bda9589eac891a4b1012cf5e8e63f20516e9c906ddc4b52b) |
| `0.0.27.post1` | `2.0-2.4` | `3.12` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp312-cp312-win_amd64.whl#sha256=c78b510a6d8e575e37c32e333cc08938fe161e733a684dd927eeb4c38ba526b6) |
| `0.0.27.post1` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp38-cp38-win_amd64.whl#sha256=366621048e45875d82da0e837d92e242ce42f4edd4403c7958e3435f471f8ff4) |
| `0.0.27.post1` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp39-cp39-win_amd64.whl#sha256=fe2661ded39d1a5d8e499a08aa54a51861b668eecdfd7d4e14bb5343e82cf326) |
| `0.0.27.post1` | `2.1-2.5` | `3.10` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp310-cp310-win_amd64.whl#sha256=4a7148f08a1d45bdb27ef0c965cfcd42d4284d2f39d3fe47aa0e08060028353e) |
| `0.0.27.post1` | `2.1-2.5` | `3.11` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp311-cp311-win_amd64.whl#sha256=15ff2f6dedbe112cdd8afc6a0fc7f5addfc2c3ed6a2b3db77b9789141b5c2a7c) |
| `0.0.27.post1` | `2.1-2.5` | `3.12` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp312-cp312-win_amd64.whl#sha256=cb386f192ef6b22959a02c0a8d5382835b55723d88f10bf3ce88be88dc0a08ad) |
| `0.0.27.post1` | `2.1-2.5` | `3.8` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp38-cp38-win_amd64.whl#sha256=301151d2ccd40ac6261ddf99fa29ff82b1f29b69f292251739cff28728786023) |
| `0.0.27.post1` | `2.1-2.5` | `3.9` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp39-cp39-win_amd64.whl#sha256=d6196c48b6196544c058b703ee51dfa7bd92021562f88b3afcebb35afe28ff3a) |
| `0.0.27.post2` | `2.0-2.4` | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp310-cp310-win_amd64.whl#sha256=b6080d3f247972af194bfe0bb89908904c15c43ed4ab96bda3038f55cd8ac071) |
| `0.0.27.post2` | `2.0-2.4` | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp311-cp311-win_amd64.whl#sha256=04225739672b3096dd137388d176370cb7e5e0b934ac0defd0031e4ad941bee7) |
| `0.0.27.post2` | `2.0-2.4` | `3.12` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp312-cp312-win_amd64.whl#sha256=ffad418be192becf08413e3cd66d1c9ce20fecd8bdb61a05cddb4f0139165fa4) |
| `0.0.27.post2` | `2.0-2.4` | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp38-cp38-win_amd64.whl#sha256=88ce8aaa16a1270f66201160649a6fd792bdb0463cc9a6b30fdb556737dc91bb) |
| `0.0.27.post2` | `2.0-2.4` | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp39-cp39-win_amd64.whl#sha256=674273d49c86ef40af563a3bd0908fc266a154683ed039c16e1012a2e4859ca7) |
| `0.0.27.post2` | `2.1-2.5` | `3.10` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp310-cp310-win_amd64.whl#sha256=cd476c23fea18aa7298753c031c4827a544d919ee542cec771c01bc824d0127d) |
| `0.0.27.post2` | `2.1-2.5` | `3.11` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp311-cp311-win_amd64.whl#sha256=7a26febb550b642c7da9864b6a46ccb89461571d27cfef54f7a252f03060d07c) |
| `0.0.27.post2` | `2.1-2.5` | `3.12` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp312-cp312-win_amd64.whl#sha256=0454ba745babf43500320b1d171ef4e44dec38f279fab9df1710ca5ce44a749c) |
| `0.0.27.post2` | `2.1-2.5` | `3.8` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp38-cp38-win_amd64.whl#sha256=5a83aa75a7208c359b2755af318e97e70855dbae6cdf998227f6dee220a56203) |
| `0.0.27.post2` | `2.1-2.5` | `3.9` | `12.1` | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp39-cp39-win_amd64.whl#sha256=d555ef6d3722941cd785cf4b7c6039b06e8a0ca1360ff661200cf043393ca5a2) |
| `0.0.28.post1` | `2.4-2.6` | `3.10` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp310-cp310-win_amd64.whl#sha256=1b20e753feac2706b16be5cc6631a30a0200f16e5142704cb26cc1454a7968f9) |
| `0.0.28.post1` | `2.4-2.6` | `3.11` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp311-cp311-win_amd64.whl#sha256=16b6558d50ee174ec41d3dde6d694fbad1f89ebb95d4f8c2a552d9fea7d3b9be) |
| `0.0.28.post1` | `2.4-2.6` | `3.12` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp312-cp312-win_amd64.whl#sha256=ae863a42667c65b470c390527ab09adabd0270e1ba1c063a9df832f32962984a) |
| `0.0.28.post1` | `2.4-2.6` | `3.8` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp38-cp38-win_amd64.whl#sha256=a4e3a1c5647b50f608c4b40a3b5254573f45788c80a1df9775bd122c5f8cb667) |
| `0.0.28.post1` | `2.4-2.6` | `3.9` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp39-cp39-win_amd64.whl#sha256=9ffd82ffa699cb17286b44d150165e2bc63f9dea89ce245ee777372149c0aafc) |
| `0.0.28.post2` | `2.4-2.6` | `3.10` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post2-cp310-cp310-win_amd64.whl#sha256=a4792ce65c7dc8a53cded78f30d90367327807453b41e2612927b3f83d3bb67e) |
| `0.0.28.post2` | `2.4-2.6` | `3.11` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post2-cp311-cp311-win_amd64.whl#sha256=852f1fa29d68a8eca8d7a100f95f5ca663c5ceda3f2060b7f00d390145f379c9) |
| `0.0.28.post2` | `2.4-2.6` | `3.12` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post2-cp312-cp312-win_amd64.whl#sha256=a8f52e4519640f58c92a2b1e1ad0e1c479b8406eb50f56920d97c3143039f0d2) |
| `0.0.28.post2` | `2.4-2.6` | `3.9` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post2-cp39-cp39-win_amd64.whl#sha256=00dffa2073e507025919d44e19d91ea11fd5b149cb9967042f9d6772a15cbe1c) |
| `0.0.28.post3` | `2.4-2.6` | `3.10` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post3-cp310-cp310-win_amd64.whl#sha256=a69ef5e54156e4a8e82c52e96f38c0d5e4f5a1a9401112f7f6c880a53d54ba5b) |
| `0.0.28.post3` | `2.4-2.6` | `3.11` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post3-cp311-cp311-win_amd64.whl#sha256=a0a7e437438de51bfcc1ebcb6f6167989e90d8b1d77a30b6fe4b21ce5b094a2e) |
| `0.0.28.post3` | `2.4-2.6` | `3.12` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post3-cp312-cp312-win_amd64.whl#sha256=3a3a0b8b12fadff6a111effcdc3573c6a584a8d71fbd5ead77999fec658ab919) |
| `0.0.28.post3` | `2.4-2.6` | `3.9` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post3-cp39-cp39-win_amd64.whl#sha256=f2d3d2d5ed96a66bee582bbedaaf53a4933fcfb293140f14c573ec4422cafc26) |
| `0.0.29` | `2.4-2.6` | `3.10` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29-cp310-cp310-win_amd64.whl#sha256=1afa261d5143636140b1749638d89ac21a0d04596c8ee1efd0b2e7ea2be28bff) |
| `0.0.29` | `2.4-2.6` | `3.11` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29-cp311-cp311-win_amd64.whl#sha256=c4ed5142cd19ba4723fa4dcf532229fbdbd9617a340450c06d7a9d9132aab154) |
| `0.0.29` | `2.4-2.6` | `3.12` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29-cp312-cp312-win_amd64.whl#sha256=e4a1788368db4857269289772678f6c97252a9bc31ae2083517e124b6a82c086) |
| `0.0.29` | `2.4-2.6` | `3.9` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29-cp39-cp39-win_amd64.whl#sha256=0477735b8b3123c8a8a0a82fe1e42a42f68860b8d18ca1120695ef32e5179cdd) |
| `0.0.29.post1` | `2.4-2.6` | `3.10` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post1-cp310-cp310-win_amd64.whl#sha256=b2e55d3209b95f702fb17caecd58c890192548941bbbee72f74aacb0d7c7690e) |
| `0.0.29.post1` | `2.4-2.6` | `3.11` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post1-cp311-cp311-win_amd64.whl#sha256=dc3aea9f8a3d239f75cc218edb7fbd69f77817e195bdc1d734c43a6e68dbf589) |
| `0.0.29.post1` | `2.4-2.6` | `3.12` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post1-cp312-cp312-win_amd64.whl#sha256=9ef5f35330dd6b54f7457a888db07aa36a56935c5d1dc4e1a9f1909bbaa3ac4d) |
| `0.0.29.post1` | `2.4-2.6` | `3.9` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post1-cp39-cp39-win_amd64.whl#sha256=c23e82f232ff88fcf13b8ebb2c48d1c4f3f8d12640b8e3e82d671db5182d4e1a) |
| `0.0.29.post2` | `2.4-2.6` | `3.10` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post2-cp310-cp310-win_amd64.whl) |
| `0.0.29.post2` | `2.4-2.6` | `3.11` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post2-cp311-cp311-win_amd64.whl) |
| `0.0.29.post2` | `2.4-2.6` | `3.12` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post2-cp312-cp312-win_amd64.whl) |
| `0.0.29.post2` | `2.4-2.6` | `3.9` | `12.4` | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post2-cp39-cp39-win_amd64.whl) |
| `0.0.29.post3` | `2.5-2.6` | `3.10` | `12.6` | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp310-cp310-win_amd64.whl) |
| `0.0.29.post3` | `2.5-2.6` | `3.11` | `12.6` | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp311-cp311-win_amd64.whl) |
| `0.0.29.post3` | `2.5-2.6` | `3.12` | `12.6` | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp312-cp312-win_amd64.whl) |
| `0.0.29.post3` | `2.5-2.6` | `3.9` | `12.6` | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp39-cp39-win_amd64.whl) |
| `0.0.30` | `2.7-2.9` | `3.10` | `12.8` | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp310-cp310-win_amd64.whl) |
| `0.0.30` | `2.7-2.9` | `3.11` | `12.8` | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp311-cp311-win_amd64.whl) |
| `0.0.30` | `2.7-2.9` | `3.12` | `12.8` | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp312-cp312-win_amd64.whl) |
| `0.0.30` | `2.7-2.9` | `3.9` | `12.8` | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp39-cp39-win_amd64.whl) |
| `0.0.31` | `2.7-2.9` | `3.9` | `12.8` | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.31-cp39-abi3-win_amd64.whl) |
| `0.0.31.post1` | `2.7-2.9` | `3.9` | `12.8` | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.31.post1-cp39-abi3-win_amd64.whl) |
| `0.0.32.post1` | `2.8-2.9` | `3.9` | `12.9` | [Link](https://download.pytorch.org/whl/cu129/xformers-0.0.32.post1-cp39-abi3-win_amd64.whl) |
| `0.0.32.post2` | `2.8-2.9` | `3.9` | `12.9` | [Link](https://download.pytorch.org/whl/cu129/xformers-0.0.32.post2-cp39-abi3-win_amd64.whl) |
| `0.0.33` | `2.10` | `3.9` | `13.0` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/xformers-0.0.33%2Bcu130torch2.10-cp39-abi3-win_amd64.whl?download=true) |
| `0.0.33` | `2.9` | `3.9` | `13.0` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/xformers-0.0.33%2Bcu130torch2.9-cp39-abi3-win_amd64.whl?download=true) |
| `0.0.33` | `2.9+` | `3.9` | `13.0` | [Link](https://download.pytorch.org/whl/cu130/xformers-0.0.33-cp39-abi3-win_amd64.whl) |
| `0.0.33.post1` | `2.9+` | `3.9` | `13.0` | [Link](https://download.pytorch.org/whl/cu130/xformers-0.0.33.post1-cp39-abi3-win_amd64.whl) |
<!-- END_XFORMERS_TABLE --> 

****

### SageAttention
*   **官方仓库**： [thu-ml/SageAttention](https://github.com/thu-ml/SageAttention)
*   **预编译来源**： [woct0rdho 发布页](https://github.com/woct0rdho/SageAttention/releases)、[Wildminder 的 HF](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)

<!-- START_SAGEATTENTION2_TABLE -->
| Package Version | PyTorch Ver | Python Ver | CUDA Ver | Download Link |
|:---:|:---:|:---:|:---:|:---:|
| `2.1.1` | `2.5.1` | `3.10` | `12.4` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu124torch2.5.1-cp310-cp310-win_amd64.whl) |
| `2.1.1` | `2.5.1` | `3.11` | `12.4` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu124torch2.5.1-cp311-cp311-win_amd64.whl) |
| `2.1.1` | `2.5.1` | `3.12` | `12.4` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu124torch2.5.1-cp312-cp312-win_amd64.whl) |
| `2.1.1` | `2.5.1` | `3.9` | `12.4` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu124torch2.5.1-cp39-cp39-win_amd64.whl) |
| `2.1.1` | `2.6.0` | `3.10` | `12.6` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu126torch2.6.0-cp310-cp310-win_amd64.whl) |
| `2.1.1` | `2.6.0` | `3.11` | `12.6` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu126torch2.6.0-cp311-cp311-win_amd64.whl) |
| `2.1.1` | `2.6.0` | `3.12` | `12.6` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.1.1%2Bcu126torch2.6.0-cp312-cp312-win_amd64.whl?download=true) |
| `2.1.1` | `2.6.0` | `3.13` | `12.6` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu126torch2.6.0-cp313-cp313-win_amd64.whl) |
| `2.1.1` | `2.6.0` | `3.9` | `12.6` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu126torch2.6.0-cp39-cp39-win_amd64.whl) |
| `2.1.1` | `2.7.0` | `3.10` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.0-cp310-cp310-win_amd64.whl) |
| `2.1.1` | `2.7.0` | `3.11` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.0-cp311-cp311-win_amd64.whl) |
| `2.1.1` | `2.7.0` | `3.12` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.0-cp312-cp312-win_amd64.whl) |
| `2.1.1` | `2.7.0` | `3.13` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.0-cp313-cp313-win_amd64.whl) |
| `2.1.1` | `2.7.0` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.0-cp39-cp39-win_amd64.whl) |
| `2.1.1` | `2.7.1` | `3.10` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.1-cp310-cp310-win_amd64.whl) |
| `2.1.1` | `2.7.1` | `3.11` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.1-cp311-cp311-win_amd64.whl) |
| `2.1.1` | `2.7.1` | `3.12` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.1-cp312-cp312-win_amd64.whl) |
| `2.1.1` | `2.7.1` | `3.13` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.1-cp313-cp313-win_amd64.whl) |
| `2.1.1` | `2.7.1` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.7.1-cp39-cp39-win_amd64.whl) |
| `2.1.1` | `2.8.0` | `3.10` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.8.0-cp310-cp310-win_amd64.whl) |
| `2.1.1` | `2.8.0` | `3.11` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.8.0-cp311-cp311-win_amd64.whl) |
| `2.1.1` | `2.8.0` | `3.12` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.1.1%2Bcu128torch2.8.0-cp312-cp312-win_amd64.whl?download=true) |
| `2.1.1` | `2.8.0` | `3.13` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.8.0-cp313-cp313-win_amd64.whl) |
| `2.1.1` | `2.8.0` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.1.1-windows/sageattention-2.1.1%2Bcu128torch2.8.0-cp39-cp39-win_amd64.whl) |
<!-- END_SAGEATTENTION2_TABLE -->

***

#### SageAttention 2.2 (SageAttention2++)
> [!NOTE]
> 仅支持 CUDA ≥ 12.8，因此需搭配 PyTorch ≥ 2.7。

<!-- START_SAGEATTENTION22_TABLE -->
| Package Version | PyTorch Ver | Python Ver | CUDA Ver | Download Link |
|:---:|:---:|:---:|:---:|:---:|
| `2.2.0` | `2.5.1` | `3.9` | `12.4` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post1/sageattention-2.2.0%2Bcu124torch2.5.1.post1-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.5.1` | `3.9` | `12.4` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post2/sageattention-2.2.0%2Bcu124torch2.5.1.post2-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.5.1` | `3.9` | `12.4` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post3/sageattention-2.2.0%2Bcu124torch2.5.1.post3-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.6.0` | `3.9` | `12.6` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post1/sageattention-2.2.0%2Bcu126torch2.6.0.post1-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.6.0` | `3.9` | `12.6` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post2/sageattention-2.2.0%2Bcu126torch2.6.0.post2-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.6.0` | `3.9` | `12.6` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post3/sageattention-2.2.0%2Bcu126torch2.6.0.post3-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.7.1` | `3.10` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.7.1-cp310-cp310-win_amd64.whl) |
| `2.2.0` | `2.7.1` | `3.11` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.7.1-cp311-cp311-win_amd64.whl) |
| `2.2.0` | `2.7.1` | `3.12` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.7.1-cp312-cp312-win_amd64.whl) |
| `2.2.0` | `2.7.1` | `3.13` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.7.1-cp313-cp313-win_amd64.whl) |
| `2.2.0` | `2.7.1` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post1/sageattention-2.2.0%2Bcu128torch2.7.1.post1-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.7.1` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post2/sageattention-2.2.0%2Bcu128torch2.7.1.post2-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.7.1` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post3/sageattention-2.2.0%2Bcu128torch2.7.1.post3-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.7.1` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.7.1-cp39-cp39-win_amd64.whl) |
| `2.2.0` | `2.8.0` | `3.10` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.8.0-cp310-cp310-win_amd64.whl) |
| `2.2.0` | `2.8.0` | `3.11` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.8.0-cp311-cp311-win_amd64.whl) |
| `2.2.0` | `2.8.0` | `3.12` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.8.0-cp312-cp312-win_amd64.whl) |
| `2.2.0` | `2.8.0` | `3.13` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.8.0-cp313-cp313-win_amd64.whl) |
| `2.2.0` | `2.8.0` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post1/sageattention-2.2.0%2Bcu128torch2.8.0.post1-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.8.0` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post2/sageattention-2.2.0%2Bcu128torch2.8.0.post2-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.8.0` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post3/sageattention-2.2.0%2Bcu128torch2.8.0.post3-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.8.0` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows/sageattention-2.2.0%2Bcu128torch2.8.0-cp39-cp39-win_amd64.whl) |
| `2.2.0` | `2.9.0` | `3.12` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0%2Bcu128torch2.9.0cxx11abi1-cp312-cp312-win_amd64.whl?download=true) |
| `2.2.0` | `2.9.0` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post3/sageattention-2.2.0%2Bcu128torch2.9.0.post3-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.9.0` | `3.9` | `13.0` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post3/sageattention-2.2.0%2Bcu130torch2.9.0.post3-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.9.0` | `3.9` | `12.8` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post4/sageattention-2.2.0%2Bcu128torch2.9.0andhigher.post4-cp39-abi3-win_amd64.whl) |
| `2.2.0` | `2.9.0` | `3.9` | `13.0` | [Link](https://github.com/woct0rdho/SageAttention/releases/download/v2.2.0-windows.post4/sageattention-2.2.0%2Bcu130torch2.9.0andhigher.post4-cp39-abi3-win_amd64.whl) |
| `2.2.0.post3` | `2.10.0` | `3.12` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu128torch2.10.0-cp312-cp312-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.10.0` | `3.12` | `13.0` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu130torch2.10.0-cp312-cp312-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.10.0` | `3.13` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu128torch2.10.0-cp313-cp313-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.10.0` | `3.13` | `13.0` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu130torch2.10.0-cp313-cp313-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.8.0` | `3.13` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu128torch2.8.0-cp313-cp313-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.8.0` | `3.13` | `12.9` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu129torch2.8.0-cp313-cp313-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.9.0` | `3.13` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu128torch2.9.0-cp313-cp313-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.9.0` | `3.13` | `12.9` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu129torch2.9.0-cp313-cp313-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.9.0` | `3.13` | `13.0` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu130torch2.9.0-cp313-cp313-win_amd64.whl?download=true) |
<!-- END_SAGEATTENTION22_TABLE -->

****

## SpargeAttn  
*   **官方仓库**： [thu-ml/SpargeAttn](https://github.com/thu-ml/SpargeAttn)
*   **预编译来源**： [woct0rdho 发布页](https://github.com/woct0rdho/SpargeAttn/releases)
<!-- START_SPARGEATTN_TABLE -->
| Package Version | PyTorch Ver | CUDA Ver | Download Link |
|:---:|:---:|:---:|:---:|
| `0.1.0` | `2.5.1` | `12.4` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post2/spas_sage_attn-0.1.0%2Bcu124torch2.5.1.post2-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.5.1` | `12.4` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post3/spas_sage_attn-0.1.0%2Bcu124torch2.5.1.post3-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.5.1` | `12.4` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows/spas_sage_attn-0.1.0%2Bcu124torch2.5.1-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.6.0` | `12.6` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post2/spas_sage_attn-0.1.0%2Bcu126torch2.6.0.post2-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.6.0` | `12.6` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post3/spas_sage_attn-0.1.0%2Bcu126torch2.6.0.post3-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.6.0` | `12.6` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows/spas_sage_attn-0.1.0%2Bcu126torch2.6.0-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.7.1` | `12.8` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post1/spas_sage_attn-0.1.0%2Bcu128torch2.7.1.post1-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.7.1` | `12.8` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post2/spas_sage_attn-0.1.0%2Bcu128torch2.7.1.post2-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.7.1` | `12.8` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post3/spas_sage_attn-0.1.0%2Bcu128torch2.7.1.post3-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.7.1` | `12.8` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows/spas_sage_attn-0.1.0%2Bcu128torch2.7.1-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.8.0` | `12.8` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post1/spas_sage_attn-0.1.0%2Bcu128torch2.8.0.post1-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.8.0` | `12.8` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post2/spas_sage_attn-0.1.0%2Bcu128torch2.8.0.post2-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.8.0` | `12.8` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post3/spas_sage_attn-0.1.0%2Bcu128torch2.8.0.post3-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.8.0` | `12.8` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows/spas_sage_attn-0.1.0%2Bcu128torch2.8.0-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.9.0` | `12.8` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post2/spas_sage_attn-0.1.0%2Bcu128torch2.9.0.post2-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.9.0` | `12.8` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post3/spas_sage_attn-0.1.0%2Bcu128torch2.9.0.post3-cp39-abi3-win_amd64.whl) |
| `0.1.0` | `2.9.0` | `13.0` | [Link](https://github.com/woct0rdho/SpargeAttn/releases/download/v0.1.0-windows.post3/spas_sage_attn-0.1.0%2Bcu130torch2.9.0.post3-cp39-abi3-win_amd64.whl) |
<!-- END_SPARGEATTN_TABLE -->

****

### Nunchaku
*   **官方仓库**： [mit-han-lab/nunchaku](https://github.com/mit-han-lab/nunchaku/releases)
<!-- START_NUNCHAKU_TABLE -->
| Package Version | PyTorch Ver | Python Ver | Download Link |
|:---:|:---:|:---:|:---:|
| `0.2.0` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `0.2.0` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `0.2.0` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `0.2.0` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `0.2.0` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `0.2.0` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `0.2.0` | `2.6` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `0.2.0` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `0.2.0` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `0.2.0` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `0.2.0` | `2.7` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `0.2.0` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `0.2.0` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `0.2.0` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `0.2.0` | `2.8` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.2.0/nunchaku-0.2.0%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `0.3.0` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `0.3.0` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `0.3.0` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `0.3.0` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `0.3.0` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `0.3.0` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `0.3.0` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `0.3.0` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `0.3.0` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `0.3.0` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `0.3.0` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `0.3.0` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.0/nunchaku-0.3.0%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `0.3.1` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `0.3.1` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `0.3.1` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `0.3.1` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `0.3.1` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `0.3.1` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `0.3.1` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `0.3.1` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `0.3.1` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `0.3.1` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `0.3.1` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `0.3.1` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.1/nunchaku-0.3.1%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `0.3.2` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `0.3.2` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `0.3.2` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `0.3.2` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `0.3.2` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `0.3.2` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `0.3.2` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `0.3.2` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `0.3.2` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `0.3.2` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `0.3.2` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `0.3.2` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `0.3.2` | `2.9` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `0.3.2` | `2.9` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v0.3.2/nunchaku-0.3.2%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `0.3.2` | `2.9` | `3.12` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/nunchaku-0.3.2%2Btorch2.9-cp312-cp312-win_amd64.whl?download=true) |
| `1.0.0` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.0` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.0` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.0` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.0` | `2.6` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.0` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.0` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.0` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.0` | `2.7` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.0` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.0` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.0` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.0` | `2.8` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.0` | `2.9` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0` | `2.9` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.0` | `2.9` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0` | `2.9` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0/nunchaku-1.0.0%2Btorch2.9-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250820` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250820/nunchaku-1.0.0.dev20250820%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250820` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250820/nunchaku-1.0.0.dev20250820%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250820` | `2.9` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250820/nunchaku-1.0.0.dev20250820%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.9` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.9` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250823` | `2.9` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250823/nunchaku-1.0.0.dev20250823%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.9` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.9` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250830` | `2.9` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250830/nunchaku-1.0.0.dev20250830%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.9` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.9` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250902` | `2.9` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250902/nunchaku-1.0.0.dev20250902%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.6` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.7` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.8` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.9` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.9` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.9` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250903` | `2.9` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250903/nunchaku-1.0.0.dev20250903%2Btorch2.9-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.6` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.7` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.8` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.9` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.9` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.9` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.0.dev20250904` | `2.9` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.0dev20250904/nunchaku-1.0.0.dev20250904%2Btorch2.9-cp313-cp313-win_amd64.whl) |
| `1.0.1` | `2.10` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.1` | `2.10` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.1` | `2.10` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `2.10` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.1` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.1` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.1` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.1` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.1` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `2.6` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.1` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.1` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.1` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `2.7` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.1` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.1` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.1` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.1` | `2.8` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1/nunchaku-1.0.1%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.1` | `2.9` | `3.12` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/nunchaku-1.0.1%2Bcu128torch2.9-cp312-cp312-win_amd64.whl?download=true) |
| `1.0.1` | `2.9` | `3.12` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/nunchaku-1.0.1%2Bcu130torch2.9-cp312-cp312-win_amd64.whl?download=true) |
| `1.0.1` | `2.9` | `3.13` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/nunchaku-1.0.1%2Bcu128torch2.9-cp313-cp313-win_amd64.whl?download=true) |
| `1.0.1` | `2.9` | `3.13` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/nunchaku-1.0.1%2Bcu130torch2.9-cp313-cp313-win_amd64.whl?download=true) |
| `1.0.1.dev20250923` | `2.10` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.10` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.10` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.10` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.6` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.7` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250923` | `2.8` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250923/nunchaku-1.0.1.dev20250923%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.10` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.10` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.10` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.10` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.6` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.7` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250924` | `2.8` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250924/nunchaku-1.0.1.dev20250924%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.10` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.10` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.10` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.10` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.6` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.7` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250926` | `2.8` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250926/nunchaku-1.0.1.dev20250926%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.10` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.10` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.10` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.10` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.6` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.7` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250929` | `2.8` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250929/nunchaku-1.0.1.dev20250929%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.10` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.10` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.10` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.10` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.5` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.5-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.5` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.5-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.5` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.5-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.6` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.6-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.6` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.6-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.6` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.6-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.6` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.6-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.7` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.1.dev20250930` | `2.8` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.1dev20250930/nunchaku-1.0.1.dev20250930%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.2` | `2.10` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.2` | `2.10` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.2` | `2.10` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.2` | `2.10` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.2` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.7-cp310-cp310-win_amd64.whl) |
| `1.0.2` | `2.7` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.7-cp311-cp311-win_amd64.whl) |
| `1.0.2` | `2.7` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.7-cp312-cp312-win_amd64.whl) |
| `1.0.2` | `2.7` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.7-cp313-cp313-win_amd64.whl) |
| `1.0.2` | `2.8` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.8-cp310-cp310-win_amd64.whl) |
| `1.0.2` | `2.8` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.8-cp311-cp311-win_amd64.whl) |
| `1.0.2` | `2.8` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.8-cp312-cp312-win_amd64.whl) |
| `1.0.2` | `2.8` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.8-cp313-cp313-win_amd64.whl) |
| `1.0.2` | `2.9` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.0.2` | `2.9` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.0.2` | `2.9` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.0.2` | `2.9` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2%2Btorch2.9-cp313-cp313-win_amd64.whl) |
| `1.1.0.dev20251111` | `2.10` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.10-cp310-cp310-win_amd64.whl) |
| `1.1.0.dev20251111` | `2.10` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.10-cp311-cp311-win_amd64.whl) |
| `1.1.0.dev20251111` | `2.10` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.10-cp312-cp312-win_amd64.whl) |
| `1.1.0.dev20251111` | `2.10` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.10-cp313-cp313-win_amd64.whl) |
| `1.1.0.dev20251111` | `2.9` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.9-cp310-cp310-win_amd64.whl) |
| `1.1.0.dev20251111` | `2.9` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.9-cp311-cp311-win_amd64.whl) |
| `1.1.0.dev20251111` | `2.9` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.9-cp312-cp312-win_amd64.whl) |
| `1.1.0.dev20251111` | `2.9` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.1.0dev20251111/nunchaku-1.1.0.dev20251111%2Btorch2.9-cp313-cp313-win_amd64.whl) |
<!-- END_NUNCHAKU_TABLE -->
  
****

### NATTEN
Neighborhood Attention Transformer。
*   **官方仓库**： [SHI-Labs/NATTEN](https://github.com/SHI-Labs/NATTEN)
*   **预编译来源**： [lldacing 的 HF](https://huggingface.co/lldacing/NATTEN-windows/tree/main)

<!-- START_NATTEN_TABLE -->
| Package Version | PyTorch Ver | Python Ver | CUDA Ver | Download Link |
|:---:|:---:|:---:|:---:|:---:|
| `0.17.3` | `2.4.0` | `3.10` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch240cu124-cp310-cp310-win_amd64.whl?download=true) |
| `0.17.3` | `2.4.0` | `3.11` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch240cu124-cp311-cp311-win_amd64.whl?download=true) |
| `0.17.3` | `2.4.0` | `3.12` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch240cu124-cp312-cp312-win_amd64.whl?download=true) |
| `0.17.3` | `2.4.1` | `3.10` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch241cu124-cp310-cp310-win_amd64.whl?download=true) |
| `0.17.3` | `2.4.1` | `3.11` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch241cu124-cp311-cp311-win_amd64.whl?download=true) |
| `0.17.3` | `2.4.1` | `3.12` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch241cu124-cp312-cp312-win_amd64.whl?download=true) |
| `0.17.3` | `2.5.0` | `3.10` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch250cu124-cp310-cp310-win_amd64.whl?download=true) |
| `0.17.3` | `2.5.0` | `3.11` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch250cu124-cp311-cp311-win_amd64.whl?download=true) |
| `0.17.3` | `2.5.0` | `3.12` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch250cu124-cp312-cp312-win_amd64.whl?download=true) |
| `0.17.3` | `2.5.1` | `3.10` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch251cu124-cp310-cp310-win_amd64.whl?download=true) |
| `0.17.3` | `2.5.1` | `3.11` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch251cu124-cp311-cp311-win_amd64.whl?download=true) |
| `0.17.3` | `2.5.1` | `3.12` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch251cu124-cp312-cp312-win_amd64.whl?download=true) |
| `0.17.5` | `2.6.0` | `3.10` | `12.6` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.5%2Btorch260cu126-cp310-cp310-win_amd64.whl?download=true) |
| `0.17.5` | `2.6.0` | `3.11` | `12.6` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.5%2Btorch260cu126-cp311-cp311-win_amd64.whl?download=true) |
| `0.17.5` | `2.6.0` | `3.12` | `12.6` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.5%2Btorch260cu126-cp312-cp312-win_amd64.whl?download=true) |
| `0.17.5` | `2.7.0` | `3.10` | `12.8` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.5%2Btorch270cu128-cp310-cp310-win_amd64.whl?download=true) |
| `0.17.5` | `2.7.0` | `3.11` | `12.8` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.5%2Btorch270cu128-cp311-cp311-win_amd64.whl?download=true) |
| `0.17.5` | `2.7.0` | `3.12` | `12.8` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.5%2Btorch270cu128-cp312-cp312-win_amd64.whl?download=true) |
<!-- END_NATTEN_TABLE -->
****

<a id="tritonwindows-fork"></a>
### Triton（Windows Fork）
Triton 是用于编写高效深度学习算子的语言与编译器，官方暂不支持 Windows，可依赖社区 fork 的预编译包。
*   **Windows Fork**： [woct0rdho/triton-windows](https://github.com/woct0rdho/triton-windows/releases)
*   **安装命令**： `pip install -U "triton-windows<3.6"`

****

### bitsandbytes
围绕 CUDA 自定义算子的轻量封装，提供 8-bit 优化器、矩阵乘（LLM.int8()）与量化能力。
*   **官方仓库**： [bitsandbytes-foundation/bitsandbytes](https://github.com/bitsandbytes-foundation/bitsandbytes)

****

### RadialAttention for ComfyUI
*   **节点**： [ComfyUI-RadialAttn](https://github.com/woct0rdho/ComfyUI-RadialAttn)

<p align="right">(<a href="#readme-top">返回顶部</a>)</p>

****

<!-- CONTRIBUTING -->
## 贡献 (Contributing)

贡献让开源社区成为一个令人惊叹的学习、启发和创造的地方。我们**非常感激**您做出的任何贡献。

如果您发现了新的预编译 wheel 文件或可靠的来源，请 pull request，或者直接开一个 issue 附上链接。
<p align="right">(<a href="#readme-top">返回顶部</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## 致谢 (Acknowledgments)

本仓库仅仅是一个链接集合。衷心感谢那些为社区辛勤构建和托管这些 wheel 文件的个人和团队：


<!-- MARKDOWN LINKS & IMAGES -->
[contributors-shield]: https://img.shields.io/github/contributors/YOUR_USERNAME/Windows-AI-Wheels.svg?style=for-the-badge
[contributors-url]: https://github.com/YOUR_USERNAME/Windows-AI-Wheels/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/YOUR_USERNAME/Windows-AI-Wheels.svg?style=for-the-badge
[forks-url]: https://github.com/YOUR_USERNAME/Windows-AI-Wheels/network/members
[stars-shield]: https://img.shields.io/github/stars/YOUR_USERNAME/Windows-AI-Wheels.svg?style=for-the-badge
[stars-url]: https://github.com/YOUR_USERNAME/Windows-AI-Wheels/stargazers
[issues-shield]: https://img.shields.io/github/issues/YOUR_USERNAME/Windows-AI-Wheels.svg?style=for-the-badge

[issues-url]: https://github.com/YOUR_USERNAME/Windows-AI-Wheels/issues
