# 🎮 天涯明月刀 PC 客户端文件说明（Moonlight Blade PC Client File Reference）

> 一份由玩家社区整理的《天涯明月刀》PC 客户端（DX12 版）游戏目录文件作用与处理参考。
>
> A community-maintained reference for the files inside the *Moonlight Blade* PC client (DX12 build) — what each file does and how to safely handle it.

![License: CC0-1.0](https://img.shields.io/badge/License-CC0%201.0-lightgrey.svg)

---

## ⚠️ 免责声明 / Disclaimer

本仓库内容由玩家社区整理，**仅供参考**，与游戏官方无关。修改、删除或替换游戏文件可能导致游戏无法运行、数据异常，甚至触发反作弊系统产生账号风险。

**操作前请务必自行备份相关文件**，因操作造成的一切后果由操作者自行承担。

This repository is a community reference and is **not affiliated with the game's official team**. Modifying, deleting, or replacing game files may cause crashes, data corruption, or trigger anti-cheat systems and put your account at risk.

**Always back up files before making changes.** You are solely responsible for any consequences.

---

## 📖 阅读说明 / How to Read This Document

> ✍️ **关于本仓库的编写说明 / About This Repository**
>
> 本文档由 **AI 辅助编写**，并参考了实际游戏目录与官方资料。文件名、版本号等信息基于实际游戏目录核对。
>
> This document was written with **AI assistance**, referencing the actual game directory and official documentation. File names and version numbers were cross-checked against the actual game directory.

### 处理建议标记 / Handling Tags

每个文件都标注了**处理建议**，分类含义如下：

Each file below is tagged with a **handling recommendation**:

| 标记 / Tag    | 含义 / Meaning                                             |
| ----------- | -------------------------------------------------------- |
| 🔒 **不可删除** | 删除或修改会导致游戏报错、无法运行。Keep it — removing it breaks the game. |
| 🗑️ **可删除** | 删除后不影响游戏正常运行。Safe to remove.                             |
| 🔄 **可替换**  | 可以用更高版本的同名文件直接替换。Replaceable with a newer version.       |
| ❓ **未验证**   | 尚未验证其作用（缺少 NVIDIA 显卡等条件）。Not yet verified.               |

> 版本信息用于对比你所能获取到的更新版本文件，仅供参考。
>
> Version numbers are listed as a baseline for comparing against newer builds you may obtain.

### 关于文件名写法 / About File Names

为提升可读性，部分冗长的文件名使用了**简化写法**。请按下表规则还原为真实文件名：

To improve readability, some long file names are abbreviated. Use the rules below to resolve them to real file names:

| 简化写法 / Abbreviation | 还原规则 / Resolution Rule                                                |
| ------------------- | --------------------------------------------------------------------- |
| `APEX_Clothing`     | 匹配 `APEX_Clothing*_x64.dll`（含 `*CHECKED` / `*PROFILE` / `*Legacy` 变体） |
| `APEX_Loader`       | 匹配 `APEX_Loader*_x64.dll`                                             |
| `ApexFramework`     | 匹配 `ApexFramework*_x64.dll`                                           |

> 其他未简化的文件名均为**精确文件名**，可直接在目录中定位。
>
> All other file names are exact and can be located directly.

---

# 💾 DX12 运行目录 / DX12 Runtime Directory

**📂 路径 / Path：** `XVersion\`

## 🔒 NVIDIA APEX 1.2.0.1（不可删除 / Do NOT delete）

> 衣物与布料物理模拟（Cloth Physics）核心组件，删除会导致游戏无法运行。  
> Core cloth-physics components. Removing them breaks the game.

| 文件 / File           |
| ------------------- |
| `APEX_Clothing`     |
| `APEX_Common`       |
| `APEX_Destructible` |
| `APEX_Framework`    |
| `APEX_Loader`       |
| `APEXFramework`     |

> 目录中同时存在 `*CHECKED`（调试版）、`*PROFILE`（性能剖析版）、`*Legacy`（旧版兼容）变体，均属 APEX 组件，**不可删除**。其中 GPU 相关变体（`APEX_ClothingGPU*`）版本为 1.2.3.4。
>
> Debug (`*CHECKED`), profiling (`*PROFILE`), and legacy-compat (`*Legacy`) variants also exist — all part of APEX and **must not be deleted**. The GPU variants (`APEX_ClothingGPU*`) are version 1.2.3.4.

---

## 🔒 Microsoft Visual C++ 运行时（**捆绑运行时** / Bundled Runtimes）

> 游戏自带的运行时。**若系统已安装对应 VC++ 运行时则可删除，否则不可删除。**
>
> Bundled runtime libraries. Safe to remove **only if** the corresponding VC++ runtime is already installed on your system.

| 文件 / File            |
| -------------------- |
| `concrt140.dll`      |
| `msvcp100.dll`       |
| `msvcp140.dll`       |
| `msvcr100.dll`       |
| `msvcrt.dll`         |
| `vcruntime140.dll`   |
| `vcruntime140_1.dll` |

---

## 🗑️ CrashSight（可删除，已验证 / Safe to remove, verified）

> 崩溃上报与性能监控组件（CrashSight SDK），删除不影响游戏运行。  
> Crash reporting and performance monitoring SDK. Safe to remove.

> 🔗 参考 / Reference: `crashsight.qq.com/documents/zh/crashsight/sdkDocuments/pc-sdk`

| 文件 / File              | 版本 / Version |
| ---------------------- | ------------ |
| `CrashSight64.dll`     | 2.1.7.620    |
| `CrashSight64_226.dll` | 2.2.6.1033   |
| `CrashSight211.dll`    | 2.1.1        |
| `GameBabyConfig64.dat` | —            |
| `GbSpy64.dll`          | 1.1.0.1      |

---

## ❓ CUDA Runtime 3.0（未验证 / Not verified）

> NVIDIA CUDA 运行时库。需 NVIDIA 显卡才能验证其实际作用，暂无更多信息。  
> NVIDIA CUDA runtime library. Requires an NVIDIA GPU to verify. No further info available.

> 🔗 参考 / Reference: `developer.nvidia.com/cuda-toolkit-archive`

| 文件 / File           | 版本 / Version           |
| ------------------- | ---------------------- |
| `cudart64_30_9.dll` | 6.14.11.3000（CUDA 3.0） |

---

## 🔒 DirectX 9 组件（系统未安装 DX9 时不可删除 / Do NOT delete unless DX9 is installed）

| 文件 / File      | 版本 / Version   |
| -------------- | -------------- |
| `d3dref9.dll`  | 6.3.9600.17298 |
| `D3DX9_43.dll` | 9.29.952.3111  |

> 游戏启动仍需要 DX9 文件。**若系统已安装 DX9 组件则可删除，否则不可删除。**  
> The game still requires DX9 files at startup. Safe to remove **only if** DX9 components are already installed on your system.

---

## 🗑️ dsound.dll（可删除，已验证 / Safe to remove, verified）

| 文件 / File    | 版本 / Version   |
| ------------ | -------------- |
| `dsound.dll` | 6.1.7600.16385 |

> 系统 `System32` 目录中已自带同名 `dsound.dll`。  
> Windows ships an identically-named `dsound.dll` in `System32`.

---

## 🔄 DirectXShaderCompiler（可替换 / Replaceable）

> DirectX 着色器编译器（DXIL 编译器及运行时）。  
> DirectX shader compiler (DXIL compiler and runtime).

> 🔗 参考 / Reference: `github.com/Microsoft/DirectXShaderCompiler`  
> 版本 / Version: **1.8.2502.8**

| 文件 / File        |
| ---------------- |
| `dxcompiler.dll` |
| `dxil.dll`       |

---

## 🔒 FMOD 4.44.12（不可删除 / Do NOT delete）

| 文件 / File                |
| ------------------------ |
| `fmod_event_net_x64.dll` |
| `fmod_event_x64.dll`     |
| `fmodex_x64.dll`         |

> 音频引擎核心组件，删除会导致游戏无法运行。  
> Core audio engine. Removing them breaks the game.

---

## 🔄 NVIDIA Texture Tools（可替换 / Replaceable）

> NVIDIA 纹理压缩工具（Texture Tools），用于 GPU 加速纹理压缩。FreeImage 为其图像格式解码依赖。  
> NVIDIA Texture Tools for GPU-accelerated texture compression. FreeImage is its image-decoding dependency.

> 🔗 参考 / Reference: `developer.nvidia.com/gpu-accelerated-texture-compression/`

| 文件 / File      | 版本 / Version |
| -------------- | ------------ |
| `nvtt_x64.dll` | 2.1.0.0      |

| 文件 / File           | 版本 / Version | 参考 / Reference                        |
| ------------------- | ------------ | ------------------------------------- |
| `FreeImage_x64.dll` | 3.15.4       | `sourceforge.net/projects/freeimage/` |

> NVTT 官方发行版（2024.1.1）随附的 FreeImage 为 3.19.0，可替换以修复旧版已知漏洞。  
> The official NVTT release (2024.1.1) bundles FreeImage 3.19.0, which can be used to replace the older version and address known vulnerabilities.

---

## 🔒 游戏语音 GVoice 1.1.17（可替换，但不可删除 / Replaceable, but do NOT delete）

> 游戏语音组件（GVoice SDK）。天涯明月刀已取消语音功能，但仍需运行文件，**不可删除**。可使用更高版本替换。  
> In-game voice SDK (GVoice). The voice feature was removed, but the files are still required at runtime — **do not delete**. Replaceable with a newer version.

> 🔗 参考 / Reference:
>
> - `gcloud.tencent.com/pages/products/gvoice.html`
> - `gcloud.tencent.com/pages/documents/details.html?projectId=256&docId=6061`

| 文件 / File         | 版本 / Version  |
| ----------------- | ------------- |
| `GCloudVoice.dll` | 1.1.17.168537 |

---

## 🗑️ GFSDK（可删除，已验证 / Safe to remove, verified）

> NVIDIA GeForce 体验与 Aftermath 显卡调试组件。  
> NVIDIA GeForce Experience and Aftermath GPU-debugging components.

| 文件 / File                         | 版本 / Version |
| --------------------------------- | ------------ |
| `GfeSDK_x64.dll`                  | —            |
| `GFSDK_Aftermath_Lib.x64.dll`     | 2.18.0.0     |
| `GFSDK_Aftermath_Lib_UWP.x64.dll` | 2.18.0.0     |

---

## 🔄 XeSS SDK（可删除、可替换 / Removable & replaceable）

> 🔗 参考 / Reference: `github.com/intel/xess`

| 文件 / File         | 版本 / Version | 建议 / Recommendation                                                      |
| ----------------- | ------------ | ------------------------------------------------------------------------ |
| `igxess.dll`      | 0.8.133      | 可删除、可替换 / removable & replaceable                                        |
| `libxess.dll`     | 1.2.0.13     | 🔒 **不可删除，但可替换更新 / Do NOT delete, but replaceable with a newer version** |
| `XeFX.dll`        | 0.1.133      | 可删除、可替换 / removable & replaceable                                        |
| `XeFX_Loader.dll` | —            | 可删除、可替换 / removable & replaceable                                        |

> 删除 `igxess.dll`、`XeFX.dll`、`XeFX_Loader.dll` 三个文件后，游戏内 XeSS 选项会消失。  
> Removing the three files above makes the in-game XeSS option disappear.

---

## 🔄 VLC Media Player 3.0.16（可替换 / Replaceable）

> 视频播放组件（libVLC），用于游戏内视频播放。  
> Video playback component (libVLC) for in-game video.

> 🔗 参考 / Reference: `https://www.videolan.org/vlc/`

| 文件 / File                |
| ------------------------ |
| `plugins\`（文件夹 / folder） |
| `libvlc.dll`             |
| `libvlccore.dll`         |

---

## ❓ DLSS / NVIDIA Streamline（未验证 / Not verified）

> NVIDIA 显卡相关的渲染与性能组件（DLSS / Streamline / Reflex），需 NVIDIA 显卡才能验证其作用。  
> NVIDIA rendering and performance components (DLSS / Streamline / Reflex). Requires an NVIDIA GPU to verify.

| 文件 / File           | 版本 / Version |
| ------------------- | ------------ |
| `nvngx_dlss.dll`    | 310.7.0.0    |
| `nvngx_dlssg.dll`   | 310.7.0.0    |
| `sl.common.dll`     | 2.12.0.0     |
| `sl.dlss.dll`       | 2.12.0.0     |
| `sl.dlss_g.dll`     | 2.12.0.0     |
| `sl.interposer.dll` | 2.12.0.0     |
| `sl.pcl.dll`        | 2.12.0.0     |
| `sl.reflex.dll`     | 2.12.0.0     |

---

## 🔒 NxCharacter 2.8.4.6（不可删除 / Do NOT delete）

> NVIDIA APEX 角色控制器组件。  
> NVIDIA APEX character-controller component.

| 文件 / File                  |
| -------------------------- |
| `NxCharacter64.dll`        |
| `NxCharacter64CHECKED.dll` |

---

## 🔒 OpenCV 2.4.9（不可删除 / Do NOT delete）

> 计算机视觉库（OpenCV），删除会导致游戏无法运行。  
> Computer-vision library (OpenCV). Removing them breaks the game.


| 文件 / File                   |
| --------------------------- |
| `opencv_core249_x64.dll`    |
| `opencv_highgui249_x64.dll` |
| `opencv_imgproc249_x64.dll` |

---

## 🗑️ Qt 4.7.1.0（可删除，已验证 / Safe to remove, verified）

| 文件 / File         |
| ----------------- |
| `QtCore4_x64.dll` |
| `QtGui4_x64.dll`  |

---

## 🔒 SpeedTree（不可删除 / Do NOT delete）

> 植被渲染引擎（SpeedTree）核心组件，删除会导致游戏无法运行。  
> Core vegetation-rendering engine (SpeedTree). Removing them breaks the game.

| 文件 / File                                                       |
| --------------------------------------------------------------- |
| `SpeedTreeCore_Windows_v6.3_VC15_MTDLL_DX12_x64.dll`            |
| `SpeedTreeForest_Windows_v6.3_VC15_MTDLL_DX12_x64.dll`          |
| `SpeedTreeRenderer_DirectX12_v6.3_VC15_MTDLL_DX12_x64.dll`      |
| `SpeedTreeRenderInterface_Windows_v6.3_VC15_MTDLL_DX12_x64.dll` |

---

# 📁 游戏根目录 / Game Root Directory

**📂 路径 / Path：** `（根目录）\` / `(root)\`

## 🗑️ CrashSight（可删除，已验证 / Safe to remove, verified）

> 崩溃上报与性能监控组件（CrashSight SDK）。  
> Crash reporting and performance monitoring SDK.

> 🔗 参考 / Reference: `crashsight.qq.com/documents/zh/crashsight/sdkDocuments/pc-sdk`

| 文件 / File              | 版本 / Version |
| ---------------------- | ------------ |
| `CrashSight64.dll`     | 2.1.7.620    |
| `CrashSight64_226.dll` | 2.2.6.1033   |
| `CrashSight211.dll`    | 2.1.1        |
| `GameBabyConfig.dat`   | —            |
| `GameBabyConfig64.dat` | —            |
| `GbSpy.dll`            | 1.1.0.1      |
| `GbSpy64.dll`          | 1.1.0.1      |
| `PerfSight.dll`        | —            |

## 🗑️ QSReplayManager_x64.dll（建议删除，已验证 / Recommended to remove, verified）

> 每次游戏更新后均需要重新删除。  
> Must be re-deleted after every game update.

## 🗑️ xunyoucall.dll（建议删除，已验证 / Recommended to remove, verified）

> 迅游加速器相关组件，建议删除。  
> Xunyou game accelerator component. Recommended to remove.

> 版本 / Version: 1.0.0.23

---

# 🌐 内置浏览器 / Embedded Browser

**📂 路径 / Path：** `QBrowser\`

> 基于 CEF（Chromium Embedded Framework）的内置浏览器，用于游戏内网页展示（公告、活动页等）。  
> A CEF-based embedded browser used for in-game web content (announcements, event pages, etc.).

> CEF 版本 / CEF version: **3.3239.1723.g071d1c1_windows32**（32 位）

> 🔗 参考 / Reference: `https://cef-builds.spotifycdn.com/index.html`

### 🔒 核心库（不可替换 / NOT replaceable）

| 文件 / File    | 说明 / Description                                                       |
| ------------ | ---------------------------------------------------------------------- |
| `libcef.dll` | CEF 核心库，腾讯定制版，**不可替换** / Tencent-customized build, **NOT replaceable** |

### 🔄 可替换（CEF 官方原版 / Replaceable）

| 文件 / File                                                                        | 说明 / Description                         |
| -------------------------------------------------------------------------------- | ---------------------------------------- |
| `cef.pak` / `cef_100_percent.pak` / `cef_200_percent.pak` / `cef_extensions.pak` | CEF 资源包 / CEF resource packs             |
| `icudtl.dat`                                                                     | ICU 国际化数据 / ICU i18n data                |
| `natives_blob.bin` / `v8_context_snapshot.bin`                                   | V8 引擎快照 / V8 snapshots                   |
| `chrome_elf.dll`                                                                 | Chromium 安全模块 / Chromium security module |
| `libEGL.dll` / `libGLESv2.dll`                                                   | ANGLE 图形层 / ANGLE graphics layer         |
| `d3dcompiler_43.dll` / `d3dcompiler_47.dll`                                      | Shader 编译器 / shader compilers            |

### 🗑️ 可删除 / Removable

| 文件 / File                | 说明 / Description                                              |
| ------------------------ | ------------------------------------------------------------- |
| `widevinecdmadapter.dll` | Widevine DRM 适配器（可删除，不影响运行）/ Widevine DRM adapter (removable) |
| `devtools_resources.pak` | 开发者工具资源（可删除）/ DevTools resources (removable)                  |

### 其他文件 / Other Files

| 文件 / File                                                                     | 说明 / Description                                |
| ----------------------------------------------------------------------------- | ----------------------------------------------- |
| `QBrowser.exe` / `QBrowserProcess.exe` / `QSBrowser.exe` / `QSSubProcess.exe` | 浏览器进程（不可删除）/ browser processes (do NOT delete)  |
| `Skin_*.dat`                                                                  | 界面皮肤资源（不可删除）/ UI skin resources (do NOT delete) |
| `locales\`                                                                    | 语言包（仅 zh-CN）/ locale packs (zh-CN only)         |
| `swiftshader\`                                                                | 软件渲染器（可删除）/ software renderer (removable)       |

---

# 📺 斗鱼直播组件 / Douyu Live Component

**📂 路径 / Path：** `ESTV\`

> 可删除。删除后游戏内「电视台」入口按键消失。  
> Safe to remove — the in-game "TV" entry button disappears after removal.

---

# 🪟 Windows 7 兼容组件 / Windows 7 Compatibility Component

**📂 路径 / Path：** `Win7\`

🔒 **不可删除** — 游戏启动会调用此目录中的文件。  
🔒 **Do NOT delete** — the game calls these files at startup.

| 文件 / File       | 说明 / Description                        |
| --------------- | --------------------------------------- |
| `d3d12.dll`     | DX12 on Win7 运行时 / DX12-on-Win7 runtime |
| `dxilconv7.dll` | DXIL 着色器转换 / DXIL shader converter      |

> 🔗 参考 / Reference:
>
> - `microsoft.github.io/DirectX-Specs/d3d/D3D12onWin7.html`
> - `github.com/microsoft/DirectX-Specs/blob/master/d3d/D3D12onWin7.md`

---

## 📝 待办 / TODO

- [ ] 验证 NVIDIA 相关组件（CUDA、DLSS）的实际作用

---

## 🤝 参与与再创作 / Contributing & Remixing

本仓库以 [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) 发布，欢迎任何人自由 fork、修改、再分发，也**鼓励你基于本文档创作自己的版本**。

若提交 Pull Request，请：

- 提供可复现的依据（如删除后的行为观察、文件版本信息等）。
- 涉及"可删除 / 可替换"的结论，请注明你验证的游戏版本。

This repository is released under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). You are free to fork, modify, and redistribute it, and are **encouraged to create your own version** based on this document.

For Pull Requests, please:

- Provide reproducible evidence (observed behavior, file version info, etc.).
- For "safe to remove / replace" claims, note the game version you tested on.

---

## 📄 许可 / License

本作品采用 [CC0 1.0 通用（CC0 1.0）](https://creativecommons.org/publicdomain/zero/1.0/) 许可，作者在法律允许的范围内放弃所有著作权及相关权利，将作品奉献至公有领域。

To the extent possible under law, the author has waived all copyright and related or neighboring rights to this work under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/).
