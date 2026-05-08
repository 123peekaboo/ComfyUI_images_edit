### 📦 ComfyUI 插件依赖清单 (Custom Nodes)

建议通过 **ComfyUI Manager** 搜索并安装以下插件：

| 插件名称 (Custom Node Name) | 对应 GitHub 仓库 (参考链接) | 核心用途 |
| --- | --- | --- |
| **ComfyUI-Manager** | [ltdrdata/ComfyUI-Manager](https://github.com/ltdrdata/ComfyUI-Manager) | **必备**。用于自动安装缺失节点和模型。 |
| **ComfyUI-Impact-Pack** | [ltdrdata/ComfyUI-Impact-Pack](https://github.com/ltdrdata/ComfyUI-Impact-Pack) | 处理 **SAM (Segment Anything)**、Mask 细化及潜在的 FaceDetailer。 |
| **ComfyUI-Inspire-Pack** | [ltdrdata/ComfyUI-Inspire-Pack](https://github.com/ltdrdata/ComfyUI-Inspire-Pack) | 增强型 KSampler 和图像处理辅助工具。 |
| **comfyui_segment_msak_stater** | [AIGODLIKE/comfyui-segment-mask-state](https://www.google.com/search?q=https://github.com/AIGODLIKE/comfyui-segment-mask-state) | 用于感知模块中的语义分割与遮罩状态管理。 |
| **ComfyUI-Custom-Scripts** | [pythongosssss/ComfyUI-Custom-Scripts](https://github.com/pythongosssss/ComfyUI-Custom-Scripts) | 提供了一些 UI 层面的增强功能（如 LoraLoader 的增强预览）。 |

---

### 🧠 必需的模型文件 (Required Models)

工作流运行还需要对应的权重文件，请确保它们放置在 `ComfyUI/models/` 的对应子目录下：

1. **Checkpoints (基础大模型)**:
* 放置路径：`models/checkpoints/`
* 建议：由于你使用了 LoraLoader，请确保有一个兼容的 SD1.5 或 SDXL 基础模型（根据你 Lora 的架构决定）。


2. **LoRA Models**:
* 放置路径：`models/loras/`
* *注意：请在 README 中注明你工作流里特定 Lora 的下载地址（如来自 Civitai）。*


3. **ControlNet Models**:
* 放置路径：`models/controlnet/`
* 需要：`control_v11p_sd15_canny` 或 `depth`（根据你在预处理阶段选择的控制类型）。


4. **Detection & Segmentation (感知模块相关)**:
* **SAM**: `sam_vit_b.pth` 或 `sam_vit_h.pth` (放置于 `models/sams/`)
* **GroundingDINO**: 插件通常会在第一次运行时自动下载，若失败需手动放置于 `models/grounding-dino/`。

