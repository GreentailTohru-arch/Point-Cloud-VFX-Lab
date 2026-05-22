# 🎛️ Point Cloud VFX Lab (点云动效实验室)

**Point Cloud VFX Lab** 是一个基于 WebGL 和 Three.js 构建的实验性三维视觉创作工具。它的灵感来源于演唱会中的“音频调音台”——如果说调音台是用来控制和重塑声音频率的，那么本项目就是一个**“场景模型的视觉调音台”**。

通过提供一系列可组合的控制组件（推子、开关、旋钮），创作者可以将普通的 3D 静态模型转化为动态的、富有生命力的点云粒子视觉艺术。本项目专为新媒体艺术、数字交互设计以及实验性视觉创作而生。

## ✨ 核心理念 (Core Concept)

在数字艺术创作中，组合往往能产生意想不到的“涌现”效果。本项目将复杂的 GLSL 着色器算法抽象为直观的 UI 面板。不同的视觉特效开关叠加、推子数值的微调，可以碰撞出成百上千种全新的视觉表现。

**打破技术壁垒**：通常情况下，实现此类复杂的视觉动效往往需要创作者跨越陡峭的学习曲线，甚至需要专门去学习熟练 TouchDesigner、Processing 等专业软件或底层图形学。而 Point Cloud VFX Lab 的初衷，正是为了彻底消除这一技术屏障。它让数字艺术爱好者无需编写复杂的节点或代码，仅凭直观的 UI 交互，就能轻松触碰并实现专业级的生成艺术，让这成为一个真正的实时视觉实验场。

## 🚀 主要功能 (Features)

### 📦 数据接入 (Data Input)
* **OBJ 模型解析**：支持本地导入 `.obj` 格式的 3D 模型，并自动进行居中和缩放处理。
* **纹理映射**：支持导入 `.png` / `.jpg` 作为点云的颜色采样贴图。
* **坐标系校准**：内置 Z 轴向上（如 Blender 导出）等坐标系对齐功能，以及独立的 X/Y/Z 轴旋转校准。

### 🎚️ 基础控制 (Base Controls)
* 实时调整点云大小（Point Size）、旋转速度、粒子密度（Density）以及全局亮度（Brightness）。
* 内置 Mesh 与 Point Cloud 双模态预览小窗，方便创作者随时比对原始模型与点云状态。

### 🌀 动态视觉矩阵 (Kinetics & VFX)
内置大量基于自定义 Shader 的动态效果，**所有效果均可无缝叠加**：
* **飘散 (Particle Flow) & 蛇形蠕动 (Local Twist)**：基于噪声场（Noise）的有机形态流体变形。
* **海浪波动 (Ocean Wave)**：赋予模型如海面般的起伏律动。
* **发散聚合 (Explode & Assemble)**：将模型粒子向外发散为星空，并支持无缝聚合。
* **破碎重组 (Shatter & Link)**：基于网格碎片的局部撕裂与重组，伴随红色发光连线。
* **动态侦测 (Dynamic Tracking)**：赛博朋克风格的 UI 覆盖层，实时捕捉并追踪模型上的随机点位。
* **时间雨 (Time Rain)**：高科技酸性腐蚀效果，伴随绿光爆发和物理空洞剔除。
* **星星流沙 (Sand Wind)**：受定向风场影响的粒子剥离效果。

### 🎵 音频响应 (Audio Reactive)
* **音乐旋动 (Audio Bounce) & 音乐律动 (Audio Rhythm)**：接入 Web Audio API，实时捕获系统/麦克风音频，利用 FFT 数据驱动点云的缩放、跳跃与扭曲，非常适合 VJ 演出。

### 📡 空间扫描 (Space Scanning)
* **平面扫描打印 (Plane Scan)**：自下而上的科幻扫描层级构建。
* **高频扫描射线 (Laser Ray)**：多线激光交织，伴随边缘高亮与深度衰减渲染。

## 🛠️ 技术栈 (Tech Stack)

* **纯前端架构**：HTML5, CSS3, 原生 JavaScript。无需复杂的 Node.js 环境或构建工具（Webpack/Vite），**开箱即用**。
* **3D 引擎**：[Three.js](https://threejs.org/) (v0.160.0)。
* **核心图形学**：重度依赖自定义 `ShaderMaterial` (GLSL)，在 GPU 端处理数以十万计的粒子位置计算与颜色混合，确保极致的实时渲染性能。
* **UI/UX**：极光青色 (Aurora Cyan) 主题，毛玻璃质感 (Backdrop Filter) 面板，提供沉浸式的操作体验。

## 🏃 如何运行 (Getting Started)

由于本项目使用了原生的 ES Modules (通过 `importmap` 引入 Three.js)，你只需要一个本地服务器即可运行，无需 `npm install`。

1.  克隆或下载此仓库到本地。
2.  使用任意本地服务器托管文件夹。例如：
    * 使用 VS Code 插件 **Live Server**（推荐，右键 HTML 文件点击 "Open with Live Server"）。
    * 或使用 Python 环境：`python -m http.server 8000`
    * 或使用 Node 环境：`npx serve .`
3.  在浏览器中打开生成的本地链接（通常为 `http://localhost:8000` 或 `http://127.0.0.1:5500`）。
4.  点击左侧面板的 **OBJ Model** 导入一个测试模型，开启你的视觉实验！

## 💡 应用场景 (Use Cases)

* **数字艺术展览**：作为互动装置的视觉输出端。
* **实时演出 (VJing)**：结合音频响应功能，为电子音乐现场提供震撼的视觉反馈。
* **创意编程教学**：供数字艺术爱好者、Three.js 和 GLSL 学习者研究点云操控与渲染技术的绝佳案例。

## 📄 协议 (License)

[MIT License](LICENSE)
