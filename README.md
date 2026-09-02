# Chladni Plate / 克拉尼板

An interactive study of resonance, nodal geometry, sound, and granular motion on a virtual square plate.

一个关于方板共振、节点几何、声音与颗粒运动的互动研究。

## Interactive Demo / 在线体验

### [Open the interactive Chladni plate / 打开互动 Chladni 板](https://stephenjohnson79.github.io/chladni-cymatics/)

The experience opens in a browser and includes synchronized audio, real-time particle motion, bilingual controls, equations, and model notes.

点击上方链接即可在浏览器中体验同步声音、实时粒子运动、中英文控制、方程与模型说明。

---

## 中文

### 项目简介

Chladni 图形让不可见的振动变得可见：当薄板在特定频率附近发生共振时，板面上的砂粒会逐渐迁移到位移接近零的节点线，形成与振动模态对应的几何图案。

本项目将这一过程转化为实时浏览器体验。黑色板面上分布着数千颗白色粒子；驱动频率、共振品质因数和简并模态组合会共同改变节点结构。声音由 Web Audio 实时生成，并与驱动频率同步。

### 交互方式

- 圆形声音按钮用于开启或静音。受浏览器策略限制，声音必须通过一次主动点击启动。
- 频率滑块控制驱动频率，单位为 `Hz`。
- `Q` 滑块控制无量纲共振品质因数。较高的 Q 值对应更窄的共振频带和更明确的模态选择。
- `β` 滑块控制无量纲简并模态混合系数，范围为 −1 到 +1，用于改变对称、单向和反对称模态组合。
- 在板面上拖动可以扰动粒子，观察节点图案重新形成。
- 右上角可切换中英文，并查看完整方程、模型边界和参考文献。

### 物理与计算模型

演示以 Kirchhoff–Love 薄板方程为物理基础：

$$
\rho h\frac{\partial^2 w}{\partial t^2}+D\nabla^4w=q(x,y,t),
\qquad
D=\frac{Eh^3}{12(1-\nu^2)}.
$$

实时计算采用余弦模态基，并以虚拟板参数将无量纲模态缩放到可听频率。方板中具有相同固有频率的 $(m,n)$ 与 $(n,m)$ 模态通过系数 $\beta$ 组合。受迫响应使用带阻尼的共振响应函数，使靠近固有频率的模态获得更高权重。

粒子沿时间平均位移能量的梯度向节点区域迁移。为了避免所有粒子无限压缩到一条数学零线上，每颗粒子具有略微不同的停驻阈值，同时加入静摩擦式停驻、局部密度排斥和弱随机扰动，从而形成有限宽度的颗粒节点带。

### 模型边界

- 真实自由边方板没有已知的简单闭式解，通常需要 Rayleigh–Ritz、有限差分或有限元方法。
- 本项目的余弦基是适合实时浏览器计算的模态近似，并不等同于真实自由边方板的精确频谱。
- 粒子运动用于表现节点聚集现象，不是完整的颗粒碰撞、摩擦和空气耦合模拟。
- 实际 Chladni 图形还会受到板材、厚度、边界约束、驱动位置、阻尼和粒径等因素影响。

### 技术形式

项目由一个独立的 `index.html` 构成，使用 Canvas 2D、Web Audio API 和原生 JavaScript。它不依赖外部库，支持桌面与移动浏览器。

---

## English

### Overview

Chladni figures make otherwise invisible vibration visible. When a thin plate is driven near one of its resonant frequencies, grains on the surface migrate toward nodal lines—regions of nearly zero transverse displacement—and reveal the geometry of the corresponding vibration mode.

This project translates that process into a real-time browser experience. Thousands of white particles move across a black virtual plate while driving frequency, resonance quality, and degenerate-mode composition reshape the nodal field. Sound is synthesized with Web Audio and remains synchronized with the driving frequency.

### Interaction

- The circular sound control enables or mutes audio. Browser autoplay policies require an explicit user gesture before sound can begin.
- The frequency slider sets the driving frequency in `Hz`.
- The `Q` slider controls the dimensionless resonance quality factor. A higher Q produces a narrower resonance bandwidth and more selective modal response.
- The `β` slider controls the dimensionless degenerate-mode mixing coefficient from −1 to +1, shifting between symmetric, directional, and antisymmetric combinations.
- Dragging across the plate disturbs the particles and reveals how the nodal pattern re-forms.
- The controls in the upper-right corner switch language and open the equations, model boundaries, and references.

### Physical and computational model

The simulation is grounded in the Kirchhoff–Love thin-plate equation:

$$
\rho h\frac{\partial^2 w}{\partial t^2}+D\nabla^4w=q(x,y,t),
\qquad
D=\frac{Eh^3}{12(1-\nu^2)}.
$$

The real-time solver uses a cosine modal basis and an equivalent virtual-plate scale that places the dimensionless modes in the audible frequency range. Square-plate modes $(m,n)$ and $(n,m)$ with the same eigenfrequency are combined through the coefficient $\beta$. A damped forced-response function increases the contribution of modes near resonance.

Particles migrate along the gradient of time-averaged displacement energy toward nodal regions. To prevent every particle from collapsing onto one mathematical zero line, each grain receives a slightly different settling threshold, together with static-friction-like settling, local density repulsion, and weak stochastic agitation. The result is a finite-width granular nodal band.

### Scope and limitations

- No simple closed-form solution is known for the true free-edge square-plate problem; it is normally treated with Rayleigh–Ritz, finite-difference, or finite-element methods.
- The cosine basis used here is a real-time modal approximation, not the exact spectrum of a physical free-edge plate.
- Particle dynamics visualize nodal accumulation rather than complete grain collision, friction, and air-coupling physics.
- Physical Chladni figures also depend on material, thickness, constraints, drive position, damping, and grain size.

### Technical format

The project is contained in a standalone `index.html` built with Canvas 2D, the Web Audio API, and native JavaScript. It has no external runtime dependencies and supports desktop and mobile browsers.

---

## References / 参考文献

- S. J. D. D’Alessio, “Forced free vibrations of a square plate,” *SN Applied Sciences* 3, 60 (2021). [https://doi.org/10.1007/s42452-020-04062-6](https://doi.org/10.1007/s42452-020-04062-6)
- D. Misseroni et al., “Cymatics for the cloaking of flexural vibrations in a structured plate,” *Scientific Reports* 6, 23929 (2016). [https://doi.org/10.1038/srep23929](https://doi.org/10.1038/srep23929)
