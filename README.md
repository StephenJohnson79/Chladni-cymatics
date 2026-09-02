# Chladni Plate / 克拉尼板

一个纯黑白、可交互的 Chladni（克拉尼）板演示。项目完全包含在单个 `index.html` 中，不需要安装依赖、运行构建命令或连接服务器。

An interactive monochrome Chladni plate demonstration. The complete experience is contained in one `index.html` file, with no dependencies, build step, or server required.

## 中文说明

### 功能

- 黑色振动板与白色沙粒，实时显示节点线。
- 桌面端约 7600 个粒子，移动端约 4400 个粒子。
- Web Audio 生成与驱动频率同步的声音。
- 中英文界面与双语公式说明。
- 支持鼠标或触摸拖动板面，扰动粒子分布。
- 自适应电脑和手机屏幕。

### 控制

- 左侧圆形按钮：开启或关闭声音。浏览器要求用户主动点击后才能播放声音。
- 第一个滑块：驱动频率，单位为 `Hz`。
- 第二个滑块：共振品质因数 `Q`，无量纲。Q 越高，共振频带越窄，节点图案通常越清晰。
- 第三个滑块：简并模态混合系数 `β`，无量纲，范围为 −1 到 +1。
- 右上角 `中 / EN`：切换界面语言。
- 右上角信息按钮：查看中英文方程、模型边界和学术参考。

### 在 GitHub Pages 上发布

1. 新建一个 GitHub 仓库。
2. 将本目录中的 `index.html` 和 `README.md` 上传到仓库根目录。
3. 在仓库的 **Settings → Pages** 中选择 **Deploy from a branch**。
4. 选择 `main` 分支和 `/ (root)` 目录，保存设置。
5. 等待 GitHub 生成公开网址。

也可以直接双击 `index.html`，在本地浏览器中运行。

### 模型说明

演示以 Kirchhoff–Love 薄板方程为物理基础，并使用余弦模态基进行实时近似。真实自由边方板没有已知的简单闭式解，通常需要 Rayleigh–Ritz、有限差分或有限元方法。这里的粒子运动是对沙粒向节点线迁移的实时视觉近似，不是完整的颗粒接触力学模拟。每颗粒子具有略微不同的停驻阈值，并使用静摩擦式停驻和局部密度排斥，从而形成有限宽度的颗粒节点带，避免无限聚合到单一像素线上。

方程、近似范围和参考文献均可通过页面右上角的信息按钮查看。

## English

### Features

- A black vibrating plate with white particles that reveal nodal lines in real time.
- Approximately 7,600 particles on desktop and 4,400 on mobile.
- Web Audio sound synchronized with the driving frequency.
- Chinese/English interface and bilingual equation notes.
- Mouse and touch interaction for disturbing the particle field.
- Responsive layout for desktop and mobile screens.

### Controls

- Circular button on the left: enables or mutes sound. Browsers require a user gesture before audio can begin.
- First slider: driving frequency in `Hz`.
- Second slider: dimensionless resonance quality factor `Q`. A higher Q creates a narrower resonance band and generally sharper nodal patterns.
- Third slider: dimensionless degenerate-mode mixing coefficient `β`, ranging from −1 to +1.
- `中 / EN` in the upper-right corner: switches the interface language.
- Information button in the upper-right corner: opens the bilingual equations, model limitations, and academic references.

### Publish with GitHub Pages

1. Create a new GitHub repository.
2. Upload `index.html` and `README.md` from this directory to the repository root.
3. Open **Settings → Pages** and select **Deploy from a branch**.
4. Choose the `main` branch and `/ (root)` folder, then save.
5. Wait for GitHub to provide the public URL.

You can also open `index.html` directly in a local browser.

### Model note

The demonstration is grounded in Kirchhoff–Love thin-plate theory and uses a cosine modal basis for real-time approximation. No simple closed-form solution is known for the true free-edge square-plate problem; it is normally treated with Rayleigh–Ritz, finite-difference, or finite-element methods. Particle motion is a real-time visual approximation of migration toward nodal lines, not a complete granular-contact simulation. Each particle has a slightly different settling threshold, with static-friction-like settling and local density repulsion producing a finite-width granular nodal band instead of collapse onto a single pixel line.

The equations, approximation boundaries, and academic references are available from the information button in the upper-right corner of the page.

## References / 参考文献

- S. J. D. D’Alessio, “Forced free vibrations of a square plate,” *SN Applied Sciences* 3, 60 (2021). [https://doi.org/10.1007/s42452-020-04062-6](https://doi.org/10.1007/s42452-020-04062-6)
- D. Misseroni et al., “Cymatics for the cloaking of flexural vibrations in a structured plate,” *Scientific Reports* 6, 23929 (2016). [https://doi.org/10.1038/srep23929](https://doi.org/10.1038/srep23929)
