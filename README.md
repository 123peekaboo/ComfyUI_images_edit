# AI 智能换装与环境合成工作流 (ComfyUI)

本项目基于 **ComfyUI** 设计了一套工业级的“人物服装替换+场景重绘”自动化工作流。通过解耦人物主体、服装特征与背景环境，实现了高保真的视觉转译。

## 🌟 核心特性 (Key Features)

* **感知与预处理模块**：利用  自动识别人物主体及服装区域，生成高精度像素遮罩。
* **特征解耦技术**：通过 LoRA 加载器与特定权重分配，确保在更换服装的同时保留人物的面部特征与姿态。
* **环境重绘 (Background Inpaint)**：支持在更换服装的同时，同步生成与新着装风格统一的背景环境，并处理光影衔接。
* **模块化设计**：工作流内部清晰划分为“图片处理”、“感知预处理”等区域，方便针对不同环节进行调优。

## 📸 工作流展示 (Workflow Preview)

<img width="1783" height="772" alt="image" src="https://github.com/user-attachments/assets/cb93c0ff-7081-4f23-b16b-159bfa526426" />


### 效果对比 (Before & After)

| 原始输入 (Source) | 提示词 (Target) | 最终合成 (Result) |
| :--- | :--- | :--- |
| **人物:**<br><img width="200" alt="Person" src="https://github.com/user-attachments/assets/599f6e13-324f-44f1-910e-09531ec13276" /><br>**背景:**<br><img width="200" alt="Background" src="https://github.com/user-attachments/assets/6e2e92f7-ad8a-4718-a45f-20cfa8256277" /> | Change the clothes to a dark green windbreaker and cargo pants. | <img width="400" alt="Result" src="https://github.com/user-attachments/assets/e7d840cd-0d04-485f-a038-a30ad27b1c6b" /> |


## 🛠️ 节点依赖 (Dependencies)

为了确保工作流正常运行，请通过 **ComfyUI Manager** 安装以下自定义节点：

1. **ComfyUI-Manager** (必备管理工具)
2. **Impact Pack** (用于 Mask 处理与 Face Detailer)
3. **ComfyUI-Custom-Scripts** (用于流程优化)
4. **IP-Adapter** (如果你的工作流涉及参考图迁移)

## 🚀 快速开始

1. 克隆本仓库：`git clone https://github.com/123peekaboo/仓库名.git`
2. 将 `workflows/` 文件夹下的 `.json` 文件拖入你的 ComfyUI 界面。
3. 点击 **"Install Missing Custom Nodes"** 补充缺失插件。
4. 上传人物图，调整重绘强度 (Denoise)，点击生成。
