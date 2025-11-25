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
| Package Version | PyTorch Ver | Python Ver | CUDA Ver | Download Link |
|:---:|:---:|:---:|:---:|:---:|
| `2.8.0a0` | `2.10.0` | `3.13` | `13.0` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/torchaudio-2.8.0a0%2Bcu130torch2.10.0cxx11abi1-cp313-cp313-win_amd64.whl?download=true) |
| `2.8.0a0` | `2.9.0` | `3.12` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/torchaudio-2.8.0a0%2Bcu128torch2.9.0cxx11abi1-cp312-cp312-win_amd64.whl?download=true) |
<!-- END_TORCHAUDIO_TABLE -->

****

### Flash Attention
高性能注意力实现。
*   **官方仓库**： [Dao-AILab/flash-attention](https://github.com/Dao-AILab/flash-attention)
*   **预编译来源**： [lldacing 的 HF](https://huggingface.co/lldacing/flash-attention-windows-wheel/tree/main)、[Wildminder 的 HF](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)、[mjun0812 GitHub](https://github.com/mjun0812/flash-attention-prebuild-wheels)

<!-- START_FLASHATTENTION_TABLE -->
| Package Version | PyTorch Ver | Python Ver | CUDA Ver | CXX11 ABI | Download Link |
|:---:|:---:|:---:|:---:|:---:|:---:|
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
| `2.7.4` | `2.5.1` | `3.10` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu124torch2.5.1cxx11abiFALSE-cp310-cp310-win_amd64.whl?download=true) |
| `2.7.4` | `2.6.0` | `3.10` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu124torch2.6.0cxx11abiFALSE-cp310-cp310-win_amd64.whl?download=true) |
| `2.7.4` | `2.6.0` | `3.10` | `12.6` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu126torch2.6.0cxx11abiFALSE-cp310-cp310-win_amd64.whl?download=true) |
| `2.7.4` | `2.6.0` | `3.11` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu124torch2.6.0cxx11abiFALSE-cp311-cp311-win_amd64.whl?download=true) |
| `2.7.4` | `2.6.0` | `3.11` | `12.6` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu126torch2.6.0cxx11abiFALSE-cp311-cp311-win_amd64.whl?download=true) |
| `2.7.4` | `2.6.0` | `3.12` | `12.4` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu124torch2.6.0cxx11abiFALSE-cp312-cp312-win_amd64.whl?download=true) |
| `2.7.4` | `2.6.0` | `3.12` | `12.6` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4%2Bcu126torch2.6.0cxx11abiFALSE-cp312-cp312-win_amd64.whl?download=true) |
| `2.7.4.post1` | `2.7.0` | `3.10` | `12.8` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4.post1%2Bcu128torch2.7.0cxx11abiFALSE-cp310-cp310-win_amd64.whl?download=true) |
| `2.7.4.post1` | `2.7.0` | `3.11` | `12.8` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4.post1%2Bcu128torch2.7.0cxx11abiFALSE-cp311-cp311-win_amd64.whl?download=true) |
| `2.7.4.post1` | `2.7.0` | `3.12` | `12.8` | ✗ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4.post1%2Bcu128torch2.7.0cxx11abiFALSE-cp312-cp312-win_amd64.whl?download=true) |
| `2.7.4.post1` | `2.8.0` | `3.10` | `12.8` | ✓ | [Link](https://huggingface.co/lldacing/flash-attention-windows-wheel/resolve/main/flash_attn-2.7.4.post1%2Bcu128torch2.8.0cxx11abiTRUE-cp310-cp310-win_amd64.whl?download=true) |
| `2.7.4.post1` | `2.8.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.7.4.post1%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.0.post2` | `2.8.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.0.post2%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.1` | `2.8.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.1%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.2` | `2.8.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.2%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.2` | `2.9.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.2%2Bcu128torch2.9.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.3` | `2.10.0` | `3.12` | `13.0` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu130torch2.10.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
| `2.8.3` | `2.10.0` | `3.13` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu128torch2.10.0cxx11abiTRUE-cp313-cp313-win_amd64.whl?download=true) |
| `2.8.3` | `2.10.0` | `3.13` | `13.0` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu130torch2.10.0cxx11abiTRUE-cp313-cp313-win_amd64.whl?download=true) |
| `2.8.3` | `2.8.0` | `3.12` | `12.8` | ✓ | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/flash_attn-2.8.3%2Bcu128torch2.8.0cxx11abiTRUE-cp312-cp312-win_amd64.whl?download=true) |
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
| `0.0.22.post2` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post2%2Bcu118-cp310-cp310-win_amd64.whl#sha256=43e13660b1dd3164fc8a64f474c1dd4a17e2997856013459b1233415701fe76c) |
| `0.0.22.post2` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post2%2Bcu118-cp311-cp311-win_amd64.whl#sha256=1849b9d0fe88104d1d2aea595ce8aa23c932f7c0774ccc560b8a111c61602f36) |
| `0.0.22.post2` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post2%2Bcu118-cp38-cp38-win_amd64.whl#sha256=f33381dea46e12c1432e252447572dd06cdba88cf44444fa2aa32e337c910899) |
| `0.0.22.post2` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post2%2Bcu118-cp39-cp39-win_amd64.whl#sha256=5192b4da139ab8525d0330425878ca26b19050476af63bfd4a683c226b03ddc0) |
| `0.0.22.post3` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=ddbb0520b98337ed4084836dd42ec67e430948773e9fe2bf4128a8bdb5b3e367) |
| `0.0.22.post3` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp310-cp310-win_amd64.whl#sha256=0ec5a4b94604280ea77819acddc605204970e002553c6c3a47101e8b454d74e9) |
| `0.0.22.post3` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post3-cp310-cp310-manylinux2014_x86_64.whl#sha256=698f79c39327f043651f5c1022c35bbde52b17200198d9ba55081556685beeb8) |
| `0.0.22.post3` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=4f6272d3c6a301aa0c6354f8b8973bb31195c8d93092b24c869bc71a9a333b90) |
| `0.0.22.post3` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp311-cp311-win_amd64.whl#sha256=f5e2085c1487ce720ff4fbabb0eafef2932cd7890893fe19ed0bbb84b31122e2) |
| `0.0.22.post3` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post3-cp311-cp311-manylinux2014_x86_64.whl#sha256=4f3aba42b1d31cf45d3491f129eeec74a2f56203aca9b55de2188db85f2574fe) |
| `0.0.22.post3` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=ee8af7cb855c8ee119a770a564742bad80c219d67232b4284d7b282676418407) |
| `0.0.22.post3` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp38-cp38-win_amd64.whl#sha256=f405360e0e6be837604b3ffa36b85d783262773cb90f25eae0bd6f97af53ae64) |
| `0.0.22.post3` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post3-cp38-cp38-manylinux2014_x86_64.whl#sha256=1884c1bbef9e2086daf815ba449aa3972c9443b82d86f6bc1c124380cb6a18de) |
| `0.0.22.post3` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=05f75bb9d4694541913389bacd13aec64406fcc2905afbae1710f0b9588775a8) |
| `0.0.22.post3` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post3%2Bcu118-cp39-cp39-win_amd64.whl#sha256=d1ae287c67cd14fd8f638b5a499db4b8348972b4ba09c2ee7ac91bd49525d622) |
| `0.0.22.post3` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post3-cp39-cp39-manylinux2014_x86_64.whl#sha256=f48159317d099a0fefb25990a38cc44b3244f528d59b107db9f5845212c66658) |
| `0.0.22.post4` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=acedcab631eecf9d943497726d036762f5a94e45a95abbd66a4b63d397354fe9) |
| `0.0.22.post4` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp310-cp310-win_amd64.whl#sha256=3b18c13a2f9543af7e89c60cc1dc09cf63408973162162d76243fde443a8464f) |
| `0.0.22.post4` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp310-cp310-manylinux2014_x86_64.whl#sha256=7075114dbf698b609b599f0d35032c0b2f9a389751e8bbf4dd3c628376b0dd9c) |
| `0.0.22.post4` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp310-cp310-win_amd64.whl#sha256=7901a41141348dd389f6cca759ebaa5480d98ecf40bb1c8c1a6cfe7b7d81413e) |
| `0.0.22.post4` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=1b5df00679c2a2126118546f50265177199b3dccf261600c89c16e9a0671368c) |
| `0.0.22.post4` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp311-cp311-win_amd64.whl#sha256=86a566b8ba5e2579837dd4253fd0ce42ea7b19c03d58207b7b476befd805a00c) |
| `0.0.22.post4` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp311-cp311-manylinux2014_x86_64.whl#sha256=b429475157d5043f4fcd17fd247801b6c96199b9d973aea3f22c0328216dcd14) |
| `0.0.22.post4` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp311-cp311-win_amd64.whl#sha256=cee27b7e9ccc00d3d893cb293cab675624847ec022485c212c3ff85ddece15a6) |
| `0.0.22.post4` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=0ab95a3209292246c2cc8667b103c38206798835754efd933f8dbcb7db650f00) |
| `0.0.22.post4` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp38-cp38-win_amd64.whl#sha256=7363a0884dbaad3d73b3986525704464002202967b76352442e516344a262c17) |
| `0.0.22.post4` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp38-cp38-manylinux2014_x86_64.whl#sha256=83e96c3999753fbf71c70afb002d3e8715b8a73efbd16f99810b7152222a730e) |
| `0.0.22.post4` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp38-cp38-win_amd64.whl#sha256=b162a9a043bce9d27b715fe378f25c5756945976c430dea84a1de977ce0c0d09) |
| `0.0.22.post4` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=98f76454be9f136a3f20d91dfb49f53781ac323b7412b463e347b457e61994a5) |
| `0.0.22.post4` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post4%2Bcu118-cp39-cp39-win_amd64.whl#sha256=eea9261c8fa3d036b7f1bc5fc11869a597b7b570115758955ec3b32a5040c6bb) |
| `0.0.22.post4` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp39-cp39-manylinux2014_x86_64.whl#sha256=3c4c7bac62164cae75b64db0a4f6eab4aa65b8136ab65d04af3dfead1bf922e1) |
| `0.0.22.post4` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post4-cp39-cp39-win_amd64.whl#sha256=242433f5eea7390779368e1d0d588c7dfb26cda6aa2d9743c64abda3884607eb) |
| `0.0.22.post7` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=06377ae0e94f9b4fe99e08663dbf3d0d133535d7648e050e435f881facc3b34d) |
| `0.0.22.post7` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp310-cp310-win_amd64.whl#sha256=ed97fc004c16aa168004af5bee2d6b12fb33cac45a625482782812b2aefa84ec) |
| `0.0.22.post7` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp310-cp310-manylinux2014_x86_64.whl#sha256=44c33373976705b1f3c5729a5ed24165b21536e3d3eedc58dd60ce68d3603f89) |
| `0.0.22.post7` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp310-cp310-win_amd64.whl#sha256=fd3c88b4aa4cd5b6aa1ee162c42c649a6dd0555fd54eaed0d1158fe50f8b1517) |
| `0.0.22.post7` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=d114a75bdb06c6cb6e4889c10c5d6d990e8433f57da475e70d2bef3d628b1ac5) |
| `0.0.22.post7` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp311-cp311-win_amd64.whl#sha256=f5a4c0199cd9e893e97378102be89141e8f3fae01a5df48023c8b23d13c21b27) |
| `0.0.22.post7` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp311-cp311-manylinux2014_x86_64.whl#sha256=479a42055ab23a9cfc0d329656d12cc7e6a6e71b49ae4874bd01d8276dfd47ef) |
| `0.0.22.post7` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp311-cp311-win_amd64.whl#sha256=5fcb0eb6eb0a6b78f6f866ea90ffbef955f8c903afd1e2fd934c1619eabb042e) |
| `0.0.22.post7` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=27effefc6ce76362d88897ffdb7b1364290a9773d37da92fbe2e06470067cfcf) |
| `0.0.22.post7` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp38-cp38-win_amd64.whl#sha256=fb5507d170232e201d75d53c888bc49a1f82835b61468c429a5f288220040374) |
| `0.0.22.post7` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp38-cp38-manylinux2014_x86_64.whl#sha256=59c3ff4aff3284726961e8cff4135d0b4b7592db9a8c29ba4d3f22a7df152af9) |
| `0.0.22.post7` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp38-cp38-win_amd64.whl#sha256=0bf779c685c8d610d32850d886df9ae7f6c72dfa115b3fe375308bfe8e04effc) |
| `0.0.22.post7` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=f526353668f85b270d700639d9b42863cc47db7d7e93abceac9e6e3c099a9aa2) |
| `0.0.22.post7` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.22.post7%2Bcu118-cp39-cp39-win_amd64.whl#sha256=532a2e71092b2770df6392387a69e1b65e53643308062ce30e0b018432c539da) |
| `0.0.22.post7` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp39-cp39-manylinux2014_x86_64.whl#sha256=0ea555b39accebd8b351f34b9ff96a82fb28136043d3db78a1403e92ff17a182) |
| `0.0.22.post7` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.22.post7-cp39-cp39-win_amd64.whl#sha256=58af99cdec4399f57e4a77fe341bf17c26a3d65e5f526b87b5dc887ad70115ca) |
| `0.0.23` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=5cbda33632505f634aee52ae55832ebd4010e64fe656c45ca477cd0b55b26d8f) |
| `0.0.23` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp310-cp310-win_amd64.whl#sha256=a05811a355ce5ab5c25e964c78e9cc7fb9b03b674914c8df6d5db45a0bef3da0) |
| `0.0.23` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp310-cp310-manylinux2014_x86_64.whl#sha256=f739814d5279ff81c7955b1aa6dae2f462799f663f1d5785ed965acc833ed258) |
| `0.0.23` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp310-cp310-win_amd64.whl#sha256=518d866cc48fe91d055b5e89d86b4d2bec716d15f8a4babec8b2808bb4afb44a) |
| `0.0.23` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=cf614b8ea3ff4635440f82095b7cae6583a49fa4161e4b3e50a6ab5cc31771d5) |
| `0.0.23` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp311-cp311-win_amd64.whl#sha256=1e03af99f27612a0099045f835332c5ee4cb5c2df4c0dbcff73a91684a3ec8d4) |
| `0.0.23` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp311-cp311-manylinux2014_x86_64.whl#sha256=8c3463def8f115239b60114693a54d50a8f78a09f475428ea22d034bf3587985) |
| `0.0.23` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp311-cp311-win_amd64.whl#sha256=32203f4450470f5f16e719dac542f6b665f7111105dd543badf4ae5492de415e) |
| `0.0.23` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=fd9fb11aa3b557e45210bfd7174dece2826c92e9706ec4b1e0dfafc9e5a66ca8) |
| `0.0.23` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp38-cp38-win_amd64.whl#sha256=a7f335f6fb3d4ed6f693da8e08389c79274bef4181465f1435f6f5dd2d3615ab) |
| `0.0.23` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp38-cp38-manylinux2014_x86_64.whl#sha256=4b183292b65735682549cffbaeade63defa16b758371ef5789685bc334710a53) |
| `0.0.23` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp38-cp38-win_amd64.whl#sha256=4408f2be58da163d598ff5496265c946f922269599cab45d36e65e9f42b37b5c) |
| `0.0.23` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=e9c9a23cc2cf9531bb6d3bb55b6707f199d550385bf12e5a8c85da20782535c5) |
| `0.0.23` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23%2Bcu118-cp39-cp39-win_amd64.whl#sha256=200173dcffb6aad82cdfe70a4948c778015898a2fa9a7434cdae4d340718978d) |
| `0.0.23` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp39-cp39-manylinux2014_x86_64.whl#sha256=8453648261f91f22595c4bee0c6f04a8f986bd6bee3a619c3a144065f644ce71) |
| `0.0.23` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23-cp39-cp39-win_amd64.whl#sha256=86e078606e6ec871efea38939ec20649ef78a58d062a66d0b5d6a6bd58b51702) |
| `0.0.23.post1` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=dc5f828dbe187c1bf69d41853a55170d2506ff4c40fc0dfbea3bc7e18daed2e5) |
| `0.0.23.post1` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp310-cp310-win_amd64.whl#sha256=bb845f1dfe21dec3ccaf2c94adabf46bd604ac5bbfb35379340816914b1ce00a) |
| `0.0.23.post1` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp310-cp310-manylinux2014_x86_64.whl#sha256=f3491e4b1077314a4535fc78c36b592a13b794eefffaa308db879f7147424a96) |
| `0.0.23.post1` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp310-cp310-win_amd64.whl#sha256=ef0744c5d1abcad7f8692b5a30ee72a71215451cbde020e2fb37af20f46ba76f) |
| `0.0.23.post1` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=40930e63a16ca3bc0e12984490a5e74d3a13cbe7a26a23124e4d83205aa69d74) |
| `0.0.23.post1` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp311-cp311-win_amd64.whl#sha256=8c232bccf88e19de91b545a2b29886c5684bf5d1f7014b6a3d126e481b5e01ee) |
| `0.0.23.post1` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp311-cp311-manylinux2014_x86_64.whl#sha256=2aea20e84852fafe87f4103b4adfe5f324915defa403e98fadc5a97f333f7105) |
| `0.0.23.post1` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp311-cp311-win_amd64.whl#sha256=372995c113c3505648f0c2d2daac53a6df60a22f30eae98e47daca5efd38fe71) |
| `0.0.23.post1` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=ab216c008c23c09e0658b760fd683d057178287620ae0a9a2a6e2f2d421348cd) |
| `0.0.23.post1` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp38-cp38-win_amd64.whl#sha256=6f3102134d300c59d31463cc12aae4864cb8dade2668bcd34198fcfd58ea08f8) |
| `0.0.23.post1` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp38-cp38-manylinux2014_x86_64.whl#sha256=17e26c66cd25ad529705228f62744ed3f86f0fe3c54fa4e23c78cd7da7a71776) |
| `0.0.23.post1` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp38-cp38-win_amd64.whl#sha256=aad762aebfe7ea3f6b9132afbf5ae88cdaf87d0c377d199dfee193e1a72d0d24) |
| `0.0.23.post1` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=0905e12df37c9027e8286c1382d459cae675f10a82d9ddb4a9312f93439583cd) |
| `0.0.23.post1` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.23.post1%2Bcu118-cp39-cp39-win_amd64.whl#sha256=103820665654b3e21257b1d5711b9fdda34b4a272f9de4b7c047bc4af292e60c) |
| `0.0.23.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp39-cp39-manylinux2014_x86_64.whl#sha256=a117e4cc835d9a19c653d79b5c66e37c72f713241e2d85b6561a15006f84b6e6) |
| `0.0.23.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.23.post1-cp39-cp39-win_amd64.whl#sha256=e08e4ebbd9fbfe9545de4028b7f604d21dc4e301dc651b3fc1bb95ae6797524f) |
| `0.0.24` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=e15b3b4e6c3aec8ea66c6fd96c60c8220bf48256d3331c4f085b873fa072c10d) |
| `0.0.24` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp310-cp310-win_amd64.whl#sha256=9a701ee428eb1f44f854a77d70f345650e9bfc91cc73be27026f13f4a1d03bdd) |
| `0.0.24` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp310-cp310-manylinux2014_x86_64.whl#sha256=018f928bd37b855021d12bff57797e729604474ccc2daa5504e1e4e4a5e6e3f7) |
| `0.0.24` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp310-cp310-win_amd64.whl#sha256=2ebacd38644e4df6a74e14fae55d561acd6d642b62819c1b8c10e07428efdad7) |
| `0.0.24` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=387dc0def94db0367b4b8e350b1402a0b336d91d8d718b49c51030b60a1bead2) |
| `0.0.24` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp311-cp311-win_amd64.whl#sha256=deb9ceac347f478e4b1ebaed969c0e0389107c268195023860d20b1504eeedbf) |
| `0.0.24` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp311-cp311-manylinux2014_x86_64.whl#sha256=9c7e0c599bed5c7110f816b38083d13158c32b1e2e5a9fcb86a818112e5ba092) |
| `0.0.24` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp311-cp311-win_amd64.whl#sha256=7510268679d32475cb0f0c31d3f8b0a97ebfcd77fea2a1604516908eee0569bb) |
| `0.0.24` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=21339dbdb4bfe149ba37f77ec049351b1e4dc57bde2ebdda255c71daffef18c4) |
| `0.0.24` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp38-cp38-win_amd64.whl#sha256=0cf379d0a88cd3abcc6e05221a5dc9cb1b7dfac1e5a3ab366e9d5ea624f648ca) |
| `0.0.24` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp38-cp38-manylinux2014_x86_64.whl#sha256=50e27d395905d2b95259f1c836207ae45b976d2f318c1099ca5e0edc41627abd) |
| `0.0.24` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp38-cp38-win_amd64.whl#sha256=dd7d65307373fcec77974775980ecd110fdc06489c4d18278a5a923afdd8dde1) |
| `0.0.24` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=d5c7eb29a3bba26aeaeaa314253f4deac26e7bbfddabb839a5f430f38bf632d3) |
| `0.0.24` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.24%2Bcu118-cp39-cp39-win_amd64.whl#sha256=c5ea36fd8e86ded344ccb82a3af92fd6e59082c1866fb30012188d62577f0654) |
| `0.0.24` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp39-cp39-manylinux2014_x86_64.whl#sha256=c9b3644551186f0e8bff4275813623ff051192b0f2469e7e5f25d56d38f359eb) |
| `0.0.24` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.24-cp39-cp39-win_amd64.whl#sha256=039f173608a37c1ff74dfd243671d0a12c9d507427f2b864373da838251fd374) |
| `0.0.25` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=0a243a6fe7c2009cbce3c580cdf4db970de7cb88219eb859aab68ddc58d57f53) |
| `0.0.25` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp310-cp310-win_amd64.whl#sha256=45c4d515e852549be73ae23004fe9e0b78531908563f41f45ec798c8199d9774) |
| `0.0.25` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp310-cp310-manylinux2014_x86_64.whl#sha256=aff69fb8708e0500ecbb2174e9b9533948bf126e7daa59e5d784c1fc37e9d46c) |
| `0.0.25` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp310-cp310-win_amd64.whl#sha256=ef3dc7f65d0b25148570172647759eb3b6032c24d696b52dabd6b55164a4a1ab) |
| `0.0.25` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=83ba04dec77c572fcb9d3deacef80a629b7a180fe42d22c5f27dca770926c6a5) |
| `0.0.25` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp311-cp311-win_amd64.whl#sha256=c96e2226a4e9b2fb68cacb579eca85ed568cf6585d5290aa5b61c82f0a5a8822) |
| `0.0.25` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp311-cp311-manylinux2014_x86_64.whl#sha256=4a58e42aea10eea9c68121afd9880c914d4512c76f9236c66fe853abab602e52) |
| `0.0.25` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp311-cp311-win_amd64.whl#sha256=a62666f27a10e4e2aff49edce369bbf1f5218ff8d7f9580d33706950ddb992d7) |
| `0.0.25` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=3aafc90c95817fff37655eb0b94d6ee81ae7352e23425cb97c011117a5cd3eb8) |
| `0.0.25` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp38-cp38-win_amd64.whl#sha256=53ae4768a53a256a11755f32c10d8d690e0692e103bc7360d3f3e008bf95b84c) |
| `0.0.25` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp38-cp38-manylinux2014_x86_64.whl#sha256=4218e995f8953050b4f702d0dd79abf4d6247889efeda4c7077ab7d8fd41b65a) |
| `0.0.25` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp38-cp38-win_amd64.whl#sha256=b72fc7f7222184421b63c794e1896424482ee5579d9f1d088b582560eefc3f58) |
| `0.0.25` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=1500937b4871b00b1df3e2226919d9e567896e37defa83751dc872f89e8fe8b4) |
| `0.0.25` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25%2Bcu118-cp39-cp39-win_amd64.whl#sha256=35ef134e776bb10afd635daca281bad2b8c3eb10e553595504f155679737683c) |
| `0.0.25` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp39-cp39-manylinux2014_x86_64.whl#sha256=4df5c35536f820c96b90c2aa40444f84947c6c7ebfbdacb2789a9aca526d3be7) |
| `0.0.25` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25-cp39-cp39-win_amd64.whl#sha256=669adb8955585f0c30d7c1b0f6d757216c9ea0c62d625f79ebea8aa17665c8f0) |
| `0.0.25.post1` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=522841d8ba5109c8497ebb119c7dca21fd844466b6dde7b518cc8752ffc09107) |
| `0.0.25.post1` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp310-cp310-win_amd64.whl#sha256=8463057ab6c70828e7b0ef336598e8f56df90b0036549c5f560eef9d66cf25e9) |
| `0.0.25.post1` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp310-cp310-manylinux2014_x86_64.whl#sha256=cdfe9560848fa5ba75fc04d3da8803658e35997adc6075ee6bbf6d67c1f0fa5e) |
| `0.0.25.post1` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp310-cp310-win_amd64.whl#sha256=ddc22273f2ff06b886d9e86f17997e4f1f3074fdeb5d46bcdf50b704430df528) |
| `0.0.25.post1` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=17e55a8d33aa18bdad5b4723bd3924ffa4095ed65d5bc1d95a5ce7841deba3f4) |
| `0.0.25.post1` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp311-cp311-win_amd64.whl#sha256=41d84b2dea18b50275edf0909a64c34b18b71ddc594971703db4704feb300afc) |
| `0.0.25.post1` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp311-cp311-manylinux2014_x86_64.whl#sha256=bbe8e83043f761d701baaac16f57d0de7d9b53e5111e15e324a3bfedbc94e3eb) |
| `0.0.25.post1` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp311-cp311-win_amd64.whl#sha256=3eaf21f437c1e1a8aa126310e33b186cb6d90906b06f90759672ba9e1f61893c) |
| `0.0.25.post1` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=c6a5df7205350658147293e14cc0aefba997aceb564df7c94a301ce60e4abc0f) |
| `0.0.25.post1` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp38-cp38-win_amd64.whl#sha256=f8c7b1a8e802d47cf833affcbf203acd62e111a656900e2b1b61d645b342c942) |
| `0.0.25.post1` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp38-cp38-manylinux2014_x86_64.whl#sha256=3c82a2c9180d87591a0306113b62248818ceee7176aad35a79557e70841432a4) |
| `0.0.25.post1` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp38-cp38-win_amd64.whl#sha256=45646a9877c6376800cb5ed4124e2f3d7baf418f75d9e21840589cf1f4fe1f8e) |
| `0.0.25.post1` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=a8f2df4f21e876551e62fab25fa4a134f386f00a5a5337d1ad18f0408cd18d52) |
| `0.0.25.post1` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.25.post1%2Bcu118-cp39-cp39-win_amd64.whl#sha256=a6e43749a96663d6b69d2d801517b9d30c0931f689eafb2386e59033ef34a555) |
| `0.0.25.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp39-cp39-manylinux2014_x86_64.whl#sha256=1ccc5f2b9370f97fb5e646cd76228106a872a4b96b05e209c595d05141abff70) |
| `0.0.25.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.25.post1-cp39-cp39-win_amd64.whl#sha256=f48bbc04a916d1010b752a005d4a27c54fec181210b63d7879534455e3b53169) |
| `0.0.26` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=b5bae78d4a762a951c801fdaebadb637faf16fa09a20d16bb147749b6f555de1) |
| `0.0.26` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp310-cp310-win_amd64.whl#sha256=a9b3af3c33023096fb6db0b6164c8fac069ff25d5d1fd8c88c96fa845be8f87f) |
| `0.0.26` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp310-cp310-manylinux2014_x86_64.whl#sha256=4c96698a3b10ae5f8d8736cc8f8f1d45170332bf9054ac07248e16129b184b74) |
| `0.0.26` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp310-cp310-win_amd64.whl#sha256=2261abce21e7100fc5249d0cdbb949d51863c6bc60e121bdc27c29ab6c2a41c1) |
| `0.0.26` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=5b791e63f205cbd0a541c1ae984f88a5863ee246ecc2abc47a77ad8cc19ca3cc) |
| `0.0.26` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp311-cp311-win_amd64.whl#sha256=c121286fc5331d7929aeea4ca130ea7164149e17e23d935cb282e96b2cbf1a1d) |
| `0.0.26` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp311-cp311-manylinux2014_x86_64.whl#sha256=97ac2a7804a2f4f767251a3ae4378f2ca696f0925593a122a160e8afe72b6522) |
| `0.0.26` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp311-cp311-win_amd64.whl#sha256=b3c46089a1b6248b162b3923244a3e0dcec8746883230014c0136300cf0c2ca1) |
| `0.0.26` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=368a2dc2b68859351f8992c171535cee744377d93fbdf435e226dc4d5d7a0af2) |
| `0.0.26` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp38-cp38-win_amd64.whl#sha256=f177bbe3f2fe3eae73de22d18f0944089bfa8cfecf32c1fc606639899448288b) |
| `0.0.26` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp38-cp38-manylinux2014_x86_64.whl#sha256=af9ae02ff3590149db359ae3b5e0dc2f329d1a5b208c693e5cb7ea4edc8087e0) |
| `0.0.26` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp38-cp38-win_amd64.whl#sha256=aadca94d92803c4946a47df1eeac819dc7c5112d74c660886eda06e862a91268) |
| `0.0.26` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=ae32a726f01a3b45075e577a1bc642789d3cf5fda1db70b785d5fe93d13fbffc) |
| `0.0.26` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26%2Bcu118-cp39-cp39-win_amd64.whl#sha256=02f814323f70ce4359666dbca2f2f244dc4312acde3ad3839b2d6c0a331c1d96) |
| `0.0.26` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp39-cp39-manylinux2014_x86_64.whl#sha256=cd92568a7c23c5588a8e5b85ac91865308fb085807f002d5dfc2aa4c2d71187a) |
| `0.0.26` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26-cp39-cp39-win_amd64.whl#sha256=38199423eb78045a78ed68cf0f048e8d0c5f1dc6c12161b85b782bf5dc56f048) |
| `0.0.26.post1` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=5b1d153580d9934c47738b9186f0f14405a7499fd0b437cb79f708b3c5578f8c) |
| `0.0.26.post1` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp310-cp310-win_amd64.whl#sha256=a8b401d4e5f3845bd277401506f62250702dedfc5cd7944e87d0bc9c30761281) |
| `0.0.26.post1` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp310-cp310-manylinux2014_x86_64.whl#sha256=1fe0f9a3dddb7f6175c2e34de2f318d6742eec28c068b8334b093016b2c9c2c8) |
| `0.0.26.post1` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp310-cp310-win_amd64.whl#sha256=e34b8dd6982077bee0c8eb2db8bc1513177201bfe0af890a4db42d8d31c966a5) |
| `0.0.26.post1` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=008d9176ebffbd86290b068860ff0ec5e6cb25cbaf7548085a073b2247fbd80e) |
| `0.0.26.post1` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp311-cp311-win_amd64.whl#sha256=2fd882d2dca2e5e814aede20819804041496c938fb395f00c511424ef76dd86e) |
| `0.0.26.post1` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp311-cp311-manylinux2014_x86_64.whl#sha256=0d35615870b9237077aec51802a5a821f9e9d2708730c8914d5cff301fb29558) |
| `0.0.26.post1` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp311-cp311-win_amd64.whl#sha256=d05c547b4ba603fc8e21fad03a342138eaaece35fe0a1692e6ee0d061ddd21ac) |
| `0.0.26.post1` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=2fd3f525dc2db79b96f0a2add194e0c5e095a15efdbcd007118f2af3c1d68dd4) |
| `0.0.26.post1` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp38-cp38-win_amd64.whl#sha256=70d72d7b61dc02463b24140c637ad3dc7281e88d90c319b26d9a2ae2f49fe1ca) |
| `0.0.26.post1` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp38-cp38-manylinux2014_x86_64.whl#sha256=f3afa385266264d5f713e75ad1b31de99add9a719f2f461f98e032c259170cc9) |
| `0.0.26.post1` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp38-cp38-win_amd64.whl#sha256=e96e2c1a11e84a6aac8386a304e3e338057c95029c82b221bf6aa1658aeacdf0) |
| `0.0.26.post1` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=8e862ec2507d2df58b4f1320043c4e5c1496a1c2c9e5c446392b9c9d6bd6ceb7) |
| `0.0.26.post1` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.26.post1%2Bcu118-cp39-cp39-win_amd64.whl#sha256=2131fef2466cc4b3464113679aa6f701a7bc292bc623b08197fe4001369f8c40) |
| `0.0.26.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp39-cp39-manylinux2014_x86_64.whl#sha256=16dcfa801450a03f148d6d5f7ba2b5540a27c52517946570fe0e1f75238d73a1) |
| `0.0.26.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.26.post1-cp39-cp39-win_amd64.whl#sha256=cf267bac8f4454db1056e4e6ff9e4df1e02b2b31d8116d50913af15fa6ae7132) |
| `0.0.27` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=066f97377fb7298ebe16fa9feb299a1fe5787284e34798c0a7459d464744b3cd) |
| `0.0.27` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp310-cp310-win_amd64.whl#sha256=70d3850e0d11a78fedfba1ddce5d248544890569f7cb55737e86677158173384) |
| `0.0.27` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp310-cp310-manylinux2014_x86_64.whl#sha256=d0efa09336da8bbff5335ab29c46f7baff03eb1fabd2d6daad4df5fd0f3ba396) |
| `0.0.27` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp310-cp310-win_amd64.whl#sha256=bef8100b1c53cdb5f884414b7daea0cec83966d977a70cbb7947786e473a4a1b) |
| `0.0.27` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=d10039c11acb3f2f45ed7fd16674015e62665660fa50cb1c4a45615e9c65f4e8) |
| `0.0.27` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp311-cp311-win_amd64.whl#sha256=d4c1d6eeb9ecb7ecfab7747346f6e38b16c3d642fa67f44d038867c0419f2e3b) |
| `0.0.27` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp311-cp311-manylinux2014_x86_64.whl#sha256=253a647e40d5381dca6f556893d64e642cf839dda8bac46c3bea07292ca3f8fc) |
| `0.0.27` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp311-cp311-win_amd64.whl#sha256=93a41717c6edbfda4ca55a583d6d0a3e0726262ffa7f7f26ab439d84a7c482b9) |
| `0.0.27` | — | `3.12` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp312-cp312-manylinux2014_x86_64.whl#sha256=d0f9921f3a0feacd7cae86e2d6a64ef2766ce0be6202df024571ef2ab73b6227) |
| `0.0.27` | — | `3.12` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp312-cp312-win_amd64.whl#sha256=be9d5e849e3249332f843a8c871177c540521b60d3265fb84f9215cde1f919c0) |
| `0.0.27` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp312-cp312-manylinux2014_x86_64.whl#sha256=dc55cc75bebd522ce77672f5e49205d02e4d6f6eff6b3ee6ebc1de42aec66b49) |
| `0.0.27` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp312-cp312-win_amd64.whl#sha256=eb2ca11ee4f189f96ac10698e81aeec7dfe157c4180bb6a88e37ad50b14c7d7d) |
| `0.0.27` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=d4f9f4fae3ee99716638724b22658e914df2c96dfa11349130852d83e2a5c621) |
| `0.0.27` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp38-cp38-win_amd64.whl#sha256=a46f49ec62ce939ee1585bd8ab484be83328df5e3c64237dc22a314d46214868) |
| `0.0.27` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp38-cp38-manylinux2014_x86_64.whl#sha256=b92348c98a96b01fa1b385f07914394363cd3c008d93978049da0e2212520daa) |
| `0.0.27` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp38-cp38-win_amd64.whl#sha256=d79457fd3d3b655527596e8de16787928b38ef21007bcd9fdb193c348a9516a4) |
| `0.0.27` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=7d2127f4cb5daaffce80b71a134984f70a65424390cedd9e2dce76755a2e792b) |
| `0.0.27` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27%2Bcu118-cp39-cp39-win_amd64.whl#sha256=00d3e1e48cbfedf823113d9f43fc19aaa396d6ac7883c4b3fd1ce697d9f65d2d) |
| `0.0.27` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp39-cp39-manylinux2014_x86_64.whl#sha256=f88ccc7613a72be9cf75e2f7c0cf6bb6ec244bdcce9fe8b3448af48a685c7ab5) |
| `0.0.27` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27-cp39-cp39-win_amd64.whl#sha256=67ab5341c7dbfeb96450778a1cd358710c4e71566dd1115246c766d01f2d5417) |
| `0.0.27.post1` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=316afe337d349b8a613baf7b73c32d9b7220a32f33972838fb48080be6fa5239) |
| `0.0.27.post1` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp310-cp310-win_amd64.whl#sha256=15bdfd7e8c3a57dc6fdd97ec9482c858acd32a14861f058c2a3062f662ce3b52) |
| `0.0.27.post1` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp310-cp310-manylinux2014_x86_64.whl#sha256=e11a3918f4824cc45df7959f5b7dd252307371a2b34a3dea73fefab4e1829cca) |
| `0.0.27.post1` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp310-cp310-win_amd64.whl#sha256=4a7148f08a1d45bdb27ef0c965cfcd42d4284d2f39d3fe47aa0e08060028353e) |
| `0.0.27.post1` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=3119b11c81ed7c8360441003f633c137f547027505dcb7f51826a0c51bc2fdab) |
| `0.0.27.post1` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp311-cp311-win_amd64.whl#sha256=3bac6bf0160c3b01bda9589eac891a4b1012cf5e8e63f20516e9c906ddc4b52b) |
| `0.0.27.post1` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp311-cp311-manylinux2014_x86_64.whl#sha256=bde1e57eb2b580b93f6172734ab4758b567022f2da77b4c533485e4822ce2aad) |
| `0.0.27.post1` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp311-cp311-win_amd64.whl#sha256=15ff2f6dedbe112cdd8afc6a0fc7f5addfc2c3ed6a2b3db77b9789141b5c2a7c) |
| `0.0.27.post1` | — | `3.12` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp312-cp312-manylinux2014_x86_64.whl#sha256=d02db8732a66c434008b084dcff0d9813a5754a89dba4d603b3b206b9074bae0) |
| `0.0.27.post1` | — | `3.12` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp312-cp312-win_amd64.whl#sha256=c78b510a6d8e575e37c32e333cc08938fe161e733a684dd927eeb4c38ba526b6) |
| `0.0.27.post1` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp312-cp312-manylinux2014_x86_64.whl#sha256=93076705c5fc726f5c7b3a0c1d21fba29721cfb5cae0c05ea5e4b0ed15c29c39) |
| `0.0.27.post1` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp312-cp312-win_amd64.whl#sha256=cb386f192ef6b22959a02c0a8d5382835b55723d88f10bf3ce88be88dc0a08ad) |
| `0.0.27.post1` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=c186637d6ab8f9977d11acacbeaee82e4280e99a9295a3d227b6c857e4e7061b) |
| `0.0.27.post1` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp38-cp38-win_amd64.whl#sha256=366621048e45875d82da0e837d92e242ce42f4edd4403c7958e3435f471f8ff4) |
| `0.0.27.post1` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp38-cp38-manylinux2014_x86_64.whl#sha256=4d546de820dd12e87ce7da1dc46d5f2d68e6f145197a0730cc433753a7ff9eea) |
| `0.0.27.post1` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp38-cp38-win_amd64.whl#sha256=301151d2ccd40ac6261ddf99fa29ff82b1f29b69f292251739cff28728786023) |
| `0.0.27.post1` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=4054a3f35f935c3732e8bb69b7042560827d594f0e8ac56abd20245359dc39b5) |
| `0.0.27.post1` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post1%2Bcu118-cp39-cp39-win_amd64.whl#sha256=fe2661ded39d1a5d8e499a08aa54a51861b668eecdfd7d4e14bb5343e82cf326) |
| `0.0.27.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp39-cp39-manylinux2014_x86_64.whl#sha256=79f8ccb1a64b1d8dbc1240c054ebec57e52148f99f9b1ee11ff4d2fbfcf90d13) |
| `0.0.27.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post1-cp39-cp39-win_amd64.whl#sha256=d6196c48b6196544c058b703ee51dfa7bd92021562f88b3afcebb35afe28ff3a) |
| `0.0.27.post2` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp310-cp310-manylinux2014_x86_64.whl#sha256=b3cdeeb9eae4547805ab8c3c645ac2fa9c6da85b46c039d9befa117e9f6f22fe) |
| `0.0.27.post2` | — | `3.10` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp310-cp310-win_amd64.whl#sha256=b6080d3f247972af194bfe0bb89908904c15c43ed4ab96bda3038f55cd8ac071) |
| `0.0.27.post2` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp310-cp310-manylinux2014_x86_64.whl#sha256=7d4bd4876559fdc3cccbcaea717d3a28ca7f2fb09ab84cac3d859449ba247830) |
| `0.0.27.post2` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp310-cp310-win_amd64.whl#sha256=cd476c23fea18aa7298753c031c4827a544d919ee542cec771c01bc824d0127d) |
| `0.0.27.post2` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp311-cp311-manylinux2014_x86_64.whl#sha256=c38d275b8184da691f8573707c816710bc9b1357028876324428e4a64fa5117d) |
| `0.0.27.post2` | — | `3.11` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp311-cp311-win_amd64.whl#sha256=04225739672b3096dd137388d176370cb7e5e0b934ac0defd0031e4ad941bee7) |
| `0.0.27.post2` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp311-cp311-manylinux2014_x86_64.whl#sha256=373a1c5d65dab89ea058d17a37c07e5da5ff3b9bebf61425e26a0a5293b0d4a9) |
| `0.0.27.post2` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp311-cp311-win_amd64.whl#sha256=7a26febb550b642c7da9864b6a46ccb89461571d27cfef54f7a252f03060d07c) |
| `0.0.27.post2` | — | `3.12` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp312-cp312-manylinux2014_x86_64.whl#sha256=9f90c504567cace89c45283630e60a24a2b93f7998479376f461741f663d1f0e) |
| `0.0.27.post2` | — | `3.12` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp312-cp312-win_amd64.whl#sha256=ffad418be192becf08413e3cd66d1c9ce20fecd8bdb61a05cddb4f0139165fa4) |
| `0.0.27.post2` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp312-cp312-manylinux2014_x86_64.whl#sha256=3500f5ff3614aa18762fddc945e4057e7225e23f35986c6666cc49d6cb1c8ee7) |
| `0.0.27.post2` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp312-cp312-win_amd64.whl#sha256=0454ba745babf43500320b1d171ef4e44dec38f279fab9df1710ca5ce44a749c) |
| `0.0.27.post2` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp38-cp38-manylinux2014_x86_64.whl#sha256=376a4460a6eaa2d5270ca7f455bf0df08190a7c7c8d6b4021a08f2dfc62600e9) |
| `0.0.27.post2` | — | `3.8` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp38-cp38-win_amd64.whl#sha256=88ce8aaa16a1270f66201160649a6fd792bdb0463cc9a6b30fdb556737dc91bb) |
| `0.0.27.post2` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp38-cp38-manylinux2014_x86_64.whl#sha256=ab39ba95a7529c412c3d81e7817e2b42c31980b72e1937055fd4ba4503a34b3d) |
| `0.0.27.post2` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp38-cp38-win_amd64.whl#sha256=5a83aa75a7208c359b2755af318e97e70855dbae6cdf998227f6dee220a56203) |
| `0.0.27.post2` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp39-cp39-manylinux2014_x86_64.whl#sha256=9c6cdd7174f083eaa5b07a6b789dbaef6c3c85dcdc680c448d6d3a03f69f1629) |
| `0.0.27.post2` | — | `3.9` | `11.8` | [Link](https://download.pytorch.org/whl/cu118/xformers-0.0.27.post2%2Bcu118-cp39-cp39-win_amd64.whl#sha256=674273d49c86ef40af563a3bd0908fc266a154683ed039c16e1012a2e4859ca7) |
| `0.0.27.post2` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp39-cp39-manylinux2014_x86_64.whl#sha256=f9fca3af140a8649678e946d55e32c8be59917c4b7d0e96437c057a4bbe30e11) |
| `0.0.27.post2` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu121/xformers-0.0.27.post2-cp39-cp39-win_amd64.whl#sha256=d555ef6d3722941cd785cf4b7c6039b06e8a0ca1360ff661200cf043393ca5a2) |
| `0.0.28` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28-cp310-cp310-manylinux_2_28_x86_64.whl#sha256=e8cb204fec45e1aa91108ca4257ebb750c0b53e5e17fbe8aa3ed071aed51bc9e) |
| `0.0.28` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28-cp311-cp311-manylinux_2_28_x86_64.whl#sha256=4ef0c42ca3719e5f5d970675cd1d1a15c1865adc4a8e9694222d9a43dda81525) |
| `0.0.28` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28-cp312-cp312-manylinux_2_28_x86_64.whl#sha256=a75b2bb10faf5a9cb67ddbecb63221314d9c5b98801576282e3ccfdf4329f407) |
| `0.0.28` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28-cp38-cp38-manylinux_2_28_x86_64.whl#sha256=49ca5afb866b24483d505cf2a5955735b4207ced4b054addd35aeb1e66130cc2) |
| `0.0.28` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28-cp39-cp39-manylinux_2_28_x86_64.whl#sha256=9d28bf2bde5b0645be2ac104b5da7f8ca919724c7bb304669178a82b1a3b82a0) |
| `0.0.28.post1` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post1-cp310-cp310-manylinux_2_28_x86_64.whl#sha256=9df9404b70459ebb5f880976acea00bc9dca9f5bf3905e6ba898c02b7f5e3193) |
| `0.0.28.post1` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp310-cp310-win_amd64.whl#sha256=1b20e753feac2706b16be5cc6631a30a0200f16e5142704cb26cc1454a7968f9) |
| `0.0.28.post1` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post1-cp311-cp311-manylinux_2_28_x86_64.whl#sha256=cbe14cc3f9bce0966ae2afe38a94f4052fb4adab423fdc75eaf6ece428c303fb) |
| `0.0.28.post1` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp311-cp311-win_amd64.whl#sha256=16b6558d50ee174ec41d3dde6d694fbad1f89ebb95d4f8c2a552d9fea7d3b9be) |
| `0.0.28.post1` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post1-cp312-cp312-manylinux_2_28_x86_64.whl#sha256=3791878ebd295c8850baf0a8511f64548aeef5f7e8c2e9f9056014bd1a7bc318) |
| `0.0.28.post1` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp312-cp312-win_amd64.whl#sha256=ae863a42667c65b470c390527ab09adabd0270e1ba1c063a9df832f32962984a) |
| `0.0.28.post1` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post1-cp38-cp38-manylinux_2_28_x86_64.whl#sha256=0dd077bda68fa813c3ce6ed805ed8ebac721c2f5513d7d66c298518e453d95c6) |
| `0.0.28.post1` | — | `3.8` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp38-cp38-win_amd64.whl#sha256=a4e3a1c5647b50f608c4b40a3b5254573f45788c80a1df9775bd122c5f8cb667) |
| `0.0.28.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post1-cp39-cp39-manylinux_2_28_x86_64.whl#sha256=c65203e4cad6fe0a1f308babd5fecef1daf442a337709f3129866489bfdeda66) |
| `0.0.28.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post1-cp39-cp39-win_amd64.whl#sha256=9ffd82ffa699cb17286b44d150165e2bc63f9dea89ce245ee777372149c0aafc) |
| `0.0.28.post2` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post2-cp310-cp310-manylinux_2_28_x86_64.whl#sha256=aff29ce4ad040a7a9a480bda05beac47c5d150dc5273e10583299fb7fc5c63ba) |
| `0.0.28.post2` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post2-cp310-cp310-win_amd64.whl#sha256=a4792ce65c7dc8a53cded78f30d90367327807453b41e2612927b3f83d3bb67e) |
| `0.0.28.post2` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post2-cp311-cp311-manylinux_2_28_x86_64.whl#sha256=d83b4da72dd4cffe7b44957ae3fd03a60d32b49c2b51b56a0f94b4f730f21f47) |
| `0.0.28.post2` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post2-cp311-cp311-win_amd64.whl#sha256=852f1fa29d68a8eca8d7a100f95f5ca663c5ceda3f2060b7f00d390145f379c9) |
| `0.0.28.post2` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post2-cp312-cp312-manylinux_2_28_x86_64.whl#sha256=672ada48bd911dbbe4b83201f3bac9c703c6a9f850da0e59e1816e1ef7400990) |
| `0.0.28.post2` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post2-cp312-cp312-win_amd64.whl#sha256=a8f52e4519640f58c92a2b1e1ad0e1c479b8406eb50f56920d97c3143039f0d2) |
| `0.0.28.post2` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post2-cp39-cp39-manylinux_2_28_x86_64.whl#sha256=61e4860aa70b1120d9459fd0859ed0d0cd66157f38d4ba657f045dc4b81f7db9) |
| `0.0.28.post2` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post2-cp39-cp39-win_amd64.whl#sha256=00dffa2073e507025919d44e19d91ea11fd5b149cb9967042f9d6772a15cbe1c) |
| `0.0.28.post3` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post3-cp310-cp310-manylinux_2_28_x86_64.whl#sha256=48132d3b19c5e120bdcfcf9ec5a0eaaafec27a81de6d14055542ca552df2adbc) |
| `0.0.28.post3` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post3-cp310-cp310-win_amd64.whl#sha256=a69ef5e54156e4a8e82c52e96f38c0d5e4f5a1a9401112f7f6c880a53d54ba5b) |
| `0.0.28.post3` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post3-cp311-cp311-manylinux_2_28_x86_64.whl#sha256=85a9f5508156b00d37dc495bbaa7b0085f97188646dcf9d703c6e6d5f5be87a2) |
| `0.0.28.post3` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post3-cp311-cp311-win_amd64.whl#sha256=a0a7e437438de51bfcc1ebcb6f6167989e90d8b1d77a30b6fe4b21ce5b094a2e) |
| `0.0.28.post3` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post3-cp312-cp312-manylinux_2_28_x86_64.whl#sha256=10858fa75a5fafd83b79b82c1383b00b9472e4b0b6865660b161103fbd4adc60) |
| `0.0.28.post3` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post3-cp312-cp312-win_amd64.whl#sha256=3a3a0b8b12fadff6a111effcdc3573c6a584a8d71fbd5ead77999fec658ab919) |
| `0.0.28.post3` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.28.post3-cp39-cp39-manylinux_2_28_x86_64.whl#sha256=c3d612d5465b4a01dc6e7c3cc69520bba9f950f3ffbb4e54f05b28eb820a6dbc) |
| `0.0.28.post3` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.28.post3-cp39-cp39-win_amd64.whl#sha256=f2d3d2d5ed96a66bee582bbedaaf53a4933fcfb293140f14c573ec4422cafc26) |
| `0.0.29` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.29-cp310-cp310-manylinux_2_28_x86_64.whl#sha256=b6b190df07a60d4027862381ef309f747a6f2a650ec50781c6fa6c6da3f1ddc1) |
| `0.0.29` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29-cp310-cp310-win_amd64.whl#sha256=1afa261d5143636140b1749638d89ac21a0d04596c8ee1efd0b2e7ea2be28bff) |
| `0.0.29` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.29-cp311-cp311-manylinux_2_28_x86_64.whl#sha256=47102f3ceb8e3ee87fed1fbaca88eee23bc0947f69a5f3d86f25a7b51c031f46) |
| `0.0.29` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29-cp311-cp311-win_amd64.whl#sha256=c4ed5142cd19ba4723fa4dcf532229fbdbd9617a340450c06d7a9d9132aab154) |
| `0.0.29` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.29-cp312-cp312-manylinux_2_28_x86_64.whl#sha256=cbfc9ee1ab7cb6445f5f5f04beba1d82788046643d6673737c3cf92fecbb11ad) |
| `0.0.29` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29-cp312-cp312-win_amd64.whl#sha256=e4a1788368db4857269289772678f6c97252a9bc31ae2083517e124b6a82c086) |
| `0.0.29` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.29-cp39-cp39-manylinux_2_28_x86_64.whl#sha256=2fb80d5948b496e2dee77db8c0d3a61e187a697ff0c765d7137908aa4b018f4d) |
| `0.0.29` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29-cp39-cp39-win_amd64.whl#sha256=0477735b8b3123c8a8a0a82fe1e42a42f68860b8d18ca1120695ef32e5179cdd) |
| `0.0.29.post1` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.29.post1-cp310-cp310-manylinux_2_28_x86_64.whl#sha256=9f9793e879571d91524ff3e25ef129f0b9ac7578eab45de0181023d112c118be) |
| `0.0.29.post1` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post1-cp310-cp310-win_amd64.whl#sha256=b2e55d3209b95f702fb17caecd58c890192548941bbbee72f74aacb0d7c7690e) |
| `0.0.29.post1` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.29.post1-cp311-cp311-manylinux_2_28_x86_64.whl#sha256=8c8cb2be0d13d1c8b074b7511bbca3e7389b626256a9b8425d60fb179b0ab128) |
| `0.0.29.post1` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post1-cp311-cp311-win_amd64.whl#sha256=dc3aea9f8a3d239f75cc218edb7fbd69f77817e195bdc1d734c43a6e68dbf589) |
| `0.0.29.post1` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.29.post1-cp312-cp312-manylinux_2_28_x86_64.whl#sha256=7c18f2ae889b44614d483e4e9dbd11eb1d3c660f7d7fc14dcec39f5c091842c4) |
| `0.0.29.post1` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post1-cp312-cp312-win_amd64.whl#sha256=9ef5f35330dd6b54f7457a888db07aa36a56935c5d1dc4e1a9f1909bbaa3ac4d) |
| `0.0.29.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.1/xformers-0.0.29.post1-cp39-cp39-manylinux_2_28_x86_64.whl#sha256=3a44c3d163ce79e4dc76719b57e3ba0065d92cd1ca199da2d7486b8dbc057af5) |
| `0.0.29.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post1-cp39-cp39-win_amd64.whl#sha256=c23e82f232ff88fcf13b8ebb2c48d1c4f3f8d12640b8e3e82d671db5182d4e1a) |
| `0.0.29.post2` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/rocm6.2.4/xformers-0.0.29.post2-cp310-cp310-manylinux_2_28_x86_64.whl) |
| `0.0.29.post2` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post2-cp310-cp310-win_amd64.whl) |
| `0.0.29.post2` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/rocm6.2.4/xformers-0.0.29.post2-cp311-cp311-manylinux_2_28_x86_64.whl) |
| `0.0.29.post2` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post2-cp311-cp311-win_amd64.whl) |
| `0.0.29.post2` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/rocm6.2.4/xformers-0.0.29.post2-cp312-cp312-manylinux_2_28_x86_64.whl) |
| `0.0.29.post2` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post2-cp312-cp312-win_amd64.whl) |
| `0.0.29.post2` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.2.4/xformers-0.0.29.post2-cp39-cp39-manylinux_2_28_x86_64.whl) |
| `0.0.29.post2` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu124/xformers-0.0.29.post2-cp39-cp39-win_amd64.whl) |
| `0.0.29.post3` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/rocm6.2.4/xformers-0.0.29.post3-cp310-cp310-manylinux_2_28_x86_64.whl) |
| `0.0.29.post3` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp310-cp310-win_amd64.whl) |
| `0.0.29.post3` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/rocm6.2.4/xformers-0.0.29.post3-cp311-cp311-manylinux_2_28_x86_64.whl) |
| `0.0.29.post3` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp311-cp311-win_amd64.whl) |
| `0.0.29.post3` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/rocm6.2.4/xformers-0.0.29.post3-cp312-cp312-manylinux_2_28_x86_64.whl) |
| `0.0.29.post3` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp312-cp312-win_amd64.whl) |
| `0.0.29.post3` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.2.4/xformers-0.0.29.post3-cp39-cp39-manylinux_2_28_x86_64.whl) |
| `0.0.29.post3` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu126/xformers-0.0.29.post3-cp39-cp39-win_amd64.whl) |
| `0.0.30` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/rocm6.3/xformers-0.0.30-cp310-cp310-manylinux_2_28_x86_64.whl) |
| `0.0.30` | — | `3.10` | — | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp310-cp310-win_amd64.whl) |
| `0.0.30` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/rocm6.3/xformers-0.0.30-cp311-cp311-manylinux_2_28_x86_64.whl) |
| `0.0.30` | — | `3.11` | — | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp311-cp311-win_amd64.whl) |
| `0.0.30` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/rocm6.3/xformers-0.0.30-cp312-cp312-manylinux_2_28_x86_64.whl) |
| `0.0.30` | — | `3.12` | — | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp312-cp312-win_amd64.whl) |
| `0.0.30` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.3/xformers-0.0.30-cp39-cp39-manylinux_2_28_x86_64.whl) |
| `0.0.30` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.30-cp39-cp39-win_amd64.whl) |
| `0.0.31` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.3/xformers-0.0.31-cp39-abi3-manylinux_2_28_x86_64.whl) |
| `0.0.31` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.31-cp39-abi3-win_amd64.whl) |
| `0.0.31.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.3/xformers-0.0.31.post1-cp39-abi3-manylinux_2_28_x86_64.whl) |
| `0.0.31.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu128/xformers-0.0.31.post1-cp39-abi3-win_amd64.whl) |
| `0.0.32.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.3/xformers-0.0.32.post1-cp39-abi3-manylinux_2_28_x86_64.whl) |
| `0.0.32.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu129/xformers-0.0.32.post1-cp39-abi3-win_amd64.whl) |
| `0.0.32.post2` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.4/xformers-0.0.32.post2-cp39-abi3-manylinux_2_28_x86_64.whl) |
| `0.0.32.post2` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu129/xformers-0.0.32.post2-cp39-abi3-win_amd64.whl) |
| `0.0.33` | `2.10` | `3.9` | `13.0` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/xformers-0.0.33%2Bcu130torch2.10-cp39-abi3-win_amd64.whl?download=true) |
| `0.0.33` | `2.9` | `3.9` | `13.0` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/xformers-0.0.33%2Bcu130torch2.9-cp39-abi3-win_amd64.whl?download=true) |
| `0.0.33` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.4/xformers-0.0.33-cp39-abi3-manylinux_2_28_x86_64.whl) |
| `0.0.33` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu130/xformers-0.0.33-cp39-abi3-win_amd64.whl) |
| `0.0.33` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu129/xformers-0.0.33%2B5d4b92a5.d20251026-cp39-abi3-linux_x86_64.whl) |
| `0.0.33` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu130/xformers-0.0.33%2B5d4b92a5.d20251029-cp39-abi3-linux_x86_64.whl) |
| `0.0.33.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/rocm6.4/xformers-0.0.33.post1-cp39-abi3-manylinux_2_28_x86_64.whl) |
| `0.0.33.post1` | — | `3.9` | — | [Link](https://download.pytorch.org/whl/cu130/xformers-0.0.33.post1-cp39-abi3-win_amd64.whl) |
<!-- END_XFORMERS_TABLE --> 

****

### SageAttention
*   **官方仓库**： [thu-ml/SageAttention](https://github.com/thu-ml/SageAttention)
*   **预编译来源**： [woct0rdho 发布页](https://github.com/woct0rdho/SageAttention/releases)、[Wildminder 的 HF](https://huggingface.co/Wildminder/AI-windows-whl/tree/main)

<!-- START_SAGEATTENTION2_TABLE -->
| Package Version | PyTorch Ver | Python Ver | CUDA Ver | Download Link |
|:---:|:---:|:---:|:---:|:---:|
| `2.1.1` | `2.6.0` | `3.12` | `12.6` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.1.1%2Bcu126torch2.6.0-cp312-cp312-win_amd64.whl?download=true) |
| `2.1.1` | `2.8.0` | `3.12` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.1.1%2Bcu128torch2.8.0-cp312-cp312-win_amd64.whl?download=true) |
| `2.2.0` | `2.9.0` | `3.12` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0%2Bcu128torch2.9.0cxx11abi1-cp312-cp312-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.10.0` | `3.12` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu128torch2.10.0-cp312-cp312-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.10.0` | `3.12` | `13.0` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu130torch2.10.0-cp312-cp312-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.10.0` | `3.13` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu128torch2.10.0-cp313-cp313-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.10.0` | `3.13` | `13.0` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu130torch2.10.0-cp313-cp313-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.8.0` | `3.13` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu128torch2.8.0-cp313-cp313-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.8.0` | `3.13` | `12.9` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu129torch2.8.0-cp313-cp313-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.9.0` | `3.13` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu128torch2.9.0-cp313-cp313-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.9.0` | `3.13` | `12.9` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu129torch2.9.0-cp313-cp313-win_amd64.whl?download=true) |
| `2.2.0.post3` | `2.9.0` | `3.13` | `13.0` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0.post3%2Bcu130torch2.9.0-cp313-cp313-win_amd64.whl?download=true) |
<!-- END_SAGEATTENTION2_TABLE -->

***

#### SageAttention 2.2 (SageAttention2++)
> [!NOTE]
> 仅支持 CUDA ≥ 12.8，因此需搭配 PyTorch ≥ 2.7。

<!-- START_SAGEATTENTION22_TABLE -->
| Package Version | PyTorch Ver | Python Ver | CUDA Ver | Download Link |
|:---:|:---:|:---:|:---:|:---:|
| `2.2.0` | `2.9.0` | `3.12` | `12.8` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/sageattention-2.2.0%2Bcu128torch2.9.0cxx11abi1-cp312-cp312-win_amd64.whl?download=true) |
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
<!-- END_SPARGEATTN_TABLE -->

****

### Nunchaku
*   **官方仓库**： [mit-han-lab/nunchaku](https://github.com/mit-han-lab/nunchaku/releases)
<!-- START_NUNCHAKU_TABLE -->
| Package Version | PyTorch Ver | Python Ver | Download Link |
|:---:|:---:|:---:|:---:|
| `0.3.2` | `2.9` | `3.12` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/nunchaku-0.3.2%2Btorch2.9-cp312-cp312-win_amd64.whl?download=true) |
| `1.0.1` | `2.9` | `3.12` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/nunchaku-1.0.1%2Bcu128torch2.9-cp312-cp312-win_amd64.whl?download=true) |
| `1.0.1` | `2.9` | `3.12` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/nunchaku-1.0.1%2Bcu130torch2.9-cp312-cp312-win_amd64.whl?download=true) |
| `1.0.1` | `2.9` | `3.13` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/nunchaku-1.0.1%2Bcu128torch2.9-cp313-cp313-win_amd64.whl?download=true) |
| `1.0.1` | `2.9` | `3.13` | [Link](https://huggingface.co/Wildminder/AI-windows-whl/resolve/main/nunchaku-1.0.1%2Bcu130torch2.9-cp313-cp313-win_amd64.whl?download=true) |
| `1.0.2` | `2.10` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2+torch2.10-cp310-cp310-linux_x86_64.whl) |
| `1.0.2` | `2.10` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2+torch2.10-cp310-cp310-win_amd64.whl) |
| `1.0.2` | `2.10` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2+torch2.10-cp311-cp311-linux_x86_64.whl) |
| `1.0.2` | `2.10` | `3.11` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2+torch2.10-cp311-cp311-win_amd64.whl) |
| `1.0.2` | `2.10` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2+torch2.10-cp312-cp312-linux_x86_64.whl) |
| `1.0.2` | `2.10` | `3.12` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2+torch2.10-cp312-cp312-win_amd64.whl) |
| `1.0.2` | `2.10` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2+torch2.10-cp313-cp313-linux_x86_64.whl) |
| `1.0.2` | `2.10` | `3.13` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2+torch2.10-cp313-cp313-win_amd64.whl) |
| `1.0.2` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2+torch2.7-cp310-cp310-linux_x86_64.whl) |
| `1.0.2` | `2.7` | `3.10` | [Link](https://github.com/nunchaku-tech/nunchaku/releases/download/v1.0.2/nunchaku-1.0.2+torch2.7-cp310-cp310-win_amd64.whl) |
<!-- END_NUNCHAKU_TABLE -->
  
****

### NATTEN
Neighborhood Attention Transformer。
*   **官方仓库**： [SHI-Labs/NATTEN](https://github.com/SHI-Labs/NATTEN)
*   **预编译来源**： [lldacing 的 HF](https://huggingface.co/lldacing/NATTEN-windows/tree/main)

<!-- START_NATTEN_TABLE -->
| Package Version | PyTorch Ver | Python Ver | CUDA Ver | Download Link |
|:---:|:---:|:---:|:---:|:---:|
| `0.17.3` | — | `3.10` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch240cu124-cp310-cp310-win_amd64.whl?download=true) |
| `0.17.3` | — | `3.10` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch241cu124-cp310-cp310-win_amd64.whl?download=true) |
| `0.17.3` | — | `3.10` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch250cu124-cp310-cp310-win_amd64.whl?download=true) |
| `0.17.3` | — | `3.10` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch251cu124-cp310-cp310-win_amd64.whl?download=true) |
| `0.17.3` | — | `3.11` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch240cu124-cp311-cp311-win_amd64.whl?download=true) |
| `0.17.3` | — | `3.11` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch241cu124-cp311-cp311-win_amd64.whl?download=true) |
| `0.17.3` | — | `3.11` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch250cu124-cp311-cp311-win_amd64.whl?download=true) |
| `0.17.3` | — | `3.11` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch251cu124-cp311-cp311-win_amd64.whl?download=true) |
| `0.17.3` | — | `3.12` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch240cu124-cp312-cp312-win_amd64.whl?download=true) |
| `0.17.3` | — | `3.12` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch241cu124-cp312-cp312-win_amd64.whl?download=true) |
| `0.17.3` | — | `3.12` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch250cu124-cp312-cp312-win_amd64.whl?download=true) |
| `0.17.3` | — | `3.12` | `12.4` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.3%2Btorch251cu124-cp312-cp312-win_amd64.whl?download=true) |
| `0.17.5` | — | `3.10` | `12.6` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.5%2Btorch260cu126-cp310-cp310-win_amd64.whl?download=true) |
| `0.17.5` | — | `3.10` | `12.8` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.5%2Btorch270cu128-cp310-cp310-win_amd64.whl?download=true) |
| `0.17.5` | — | `3.11` | `12.6` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.5%2Btorch260cu126-cp311-cp311-win_amd64.whl?download=true) |
| `0.17.5` | — | `3.11` | `12.8` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.5%2Btorch270cu128-cp311-cp311-win_amd64.whl?download=true) |
| `0.17.5` | — | `3.12` | `12.6` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.5%2Btorch260cu126-cp312-cp312-win_amd64.whl?download=true) |
| `0.17.5` | — | `3.12` | `12.8` | [Link](https://huggingface.co/lldacing/NATTEN-windows/resolve/main/natten-0.17.5%2Btorch270cu128-cp312-cp312-win_amd64.whl?download=true) |
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

<p align="center">▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀</p>

<!-- DATA ACCESS -->
## Accessing Data Programmatically (wheels.json)

All wheel information in this repository is managed in the `wheels.json` file, which serves as the single source of truth. The tables in this README are automatically generated from this file.

This provides a stable, structured JSON endpoint for any external tool or application that needs to access this data without parsing Markdown.

### How to Use

You can access the raw JSON file directly via the following URL:

```
https://raw.githubusercontent.com/wildminder/AI-windows-whl/main/wheels.json
```

**Example using `curl`:**
```sh
curl -L -o wheels.json https://raw.githubusercontent.com/wildminder/AI-windows-whl/main/wheels.json
```

The file contains a list of `packages`, each with its metadata and an array of `wheels`, where each wheel object contains version details and a direct download `url`.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<p align="center">▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀</p>

<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have found a new pre-built wheel or a reliable source, please fork the repo and create a pull request, or simply open an issue with the link.
<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

This repository is simply a collection of links. Huge thanks to the individuals and groups who do the hard work of building and hosting these wheels for the community:


<!-- MARKDOWN LINKS & IMAGES -->
[contributors-shield]: https://img.shields.io/github/contributors/YOUR_USERNAME/Windows-AI-Wheels.svg?style=for-the-badge
[contributors-url]: https://github.com/YOUR_USERNAME/Windows-AI-Wheels/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/YOUR_USERNAME/Windows-AI-Wheels.svg?style=for-the-badge
[forks-url]: https://github.com/YOUR_USERNAME/Windows-AI-Wheels/network/members
[stars-shield]: https://img.shields.io/github/stars/YOUR_USERNAME/Windows-AI-Wheels.svg?style=for-the-badge
[stars-url]: https://github.com/YOUR_USERNAME/Windows-AI-Wheels/stargazers
[issues-shield]: https://img.shields.io/github/issues/YOUR_USERNAME/Windows-AI-Wheels.svg?style=for-the-badge

[issues-url]: https://github.com/YOUR_USERNAME/Windows-AI-Wheels/issues
