# cloth_simulation

浏览器里的 **2D 悬挂布料物理 + 丝质高光着色** 演示：单文件 HTML，无需构建，双击或用静态服务器打开即可。

本地可直接用浏览器打开：

```text
cloth-simulation.html
```

## 功能说明

- **质点–弹簧网格**：结构 / 剪切 / 弯曲约束，迭代求解。
- **积分**：Verlet + 子步进（`SUBSTEPS`），阻尼与重力可调。
- **边界**：顶部整行固定（悬挂），画布边缘软约束；挂杆处带摩擦以减弱寄生振荡。
- **交互**：鼠标靠近推开布料，移动产生拖拽感；靠近边缘与顶部区域力度衰减。
- **观感**：在光照用的「抬起」空间（`lift`）内对网格做双线性细分着色（`SHADE_SUBDIV`），减轻平面着色带来的细密格子线，整体更像一整块织物。

## 技术栈

| 项目 | 说明 |
|------|------|
| 运行环境 | 任意现代浏览器（Canvas 2D） |
| 依赖 | 无 |
| 入口文件 | `cloth-simulation.html` |

## 可调参数（源码内常量）

在 `cloth-simulation.html` 顶部脚本中可微调，例如：

| 常量 | 作用简述 |
|------|-----------|
| `COLS` / `ROWS` | 仿真网格密度 |
| `GRAVITY` / `DAMPING` | 重力与速度阻尼 |
| `CONSTRAINT_ITERS` | 约束迭代次数 |
| `MOUSE_PUSH` / `MOUSE_DRAG` | 鼠标推开与拖拽强度 |
| `SHADE_SUBDIV` | 绘制细分（越大越顺滑、计算略增） |
| `Z_SAG` | 伪 3D 下垂用于法线与高光 |

## 仓库结构

```text
cloth_simulation/
├── README.md
└── cloth-simulation.html   # 唯一源码入口
```
