## 环境要求

- **Python**：3.12+
- **Taichi**：1.7.4+
- **操作系统**：Windows 10+ / macOS / Linux

## 安装依赖

### 使用pip安装

```bash
pip install taichi
```

### 使用uv安装（推荐）

```bash
uv add taichi
```

## 运行方法

### 实验0：Taichi重力粒子系统

```bash
python src/Work0/main.py
```

运行后会弹出一个窗口，显示粒子系统。你可以在窗口中移动鼠标，粒子会受到鼠标的引力影响。

## 项目结构

```
CG-Lab/
├── src/
│   └── Work0/           # 实验 0：Taichi Gravity Swarm
│       ├── __init__.py
│       ├── config.py     # 配置参数
│       ├── main.py       # 主程序
│       └── physics.py    # 物理计算
├── .gitignore
├── .python-version
├── README.md
├── pyproject.toml       # 项目配置和依赖
├── tesst.py
└── uv.lock
```

## 实验说明

### 实验0：Taichi重力粒子系统

#### 功能
- 使用Taichi库实现GPU加速的粒子系统
- 鼠标引力交互：粒子会被鼠标吸引
- 粒子边界碰撞检测：粒子碰到边界会反弹
- 实时渲染：使用Taichi的GUI模块实时渲染粒子

#### 效果
![v10cO8zT_converted](https://github.com/user-attachments/assets/e2191270-6e08-4cda-82b0-f62ee441a821)

#### 实现原理
1. **数据结构**：使用Taichi的`Vector.field`在显存中存储粒子的位置和速度
2. **物理计算**：使用Taichi的`@ti.kernel`装饰器实现并行计算
3. **渲染系统**：使用Taichi的`GUI`模块绘制粒子
4. **交互系统**：通过鼠标位置控制引力中心

## 配置参数

在 `src/Work0/config.py` 文件中可以调整以下参数：

| 参数名 | 默认值 | 说明 |
|-------|-------|------|
| `NUM_PARTICLES` | 10000 | 粒子总数（卡顿请调小此数值，如 2000） |
| `GRAVITY_STRENGTH` | 0.001 | 鼠标引力强度 |
| `DRAG_COEF` | 0.98 | 空气阻力系数 |
| `BOUNCE_COEF` | -0.8 | 边界反弹能量损耗 |
| `WINDOW_RES` | (800, 600) | 窗口分辨率 |
| `PARTICLE_RADIUS` | 1.5 | 粒子绘制半径 |
| `PARTICLE_COLOR` | 0x00BFFF | 粒子颜色（天蓝色） |

## 技术特点

1. **GPU加速**：使用Taichi库将计算任务转移到GPU，大幅提升性能
2. **并行计算**：利用GPU的并行计算能力，同时处理大量粒子
3. **实时渲染**：实时更新和渲染粒子状态
4. **交互体验**：通过鼠标交互控制粒子行为
5. **可扩展性**：模块化设计，易于添加新的实验和功能

## 开发指南

### 添加新实验

1. 在 `src/` 目录下创建新的实验文件夹，如 `Work1/`
2. 在新文件夹中创建必要的文件：
   - `__init__.py`：包初始化文件
   - `config.py`：配置参数
   - `main.py`：主程序
   - `physics.py`：物理系统（如果需要）
3. 在 `README.md` 中添加新实验的说明

### 代码规范

- 使用4个空格进行缩进
- 遵循PEP 8代码风格
- 添加适当的注释和文档字符串
- 使用有意义的变量和函数名

## 注意事项

- 首次运行时，Taichi 会编译 GPU 内核，可能需要一些时间
- 确保您的 GPU 支持 Taichi（大多数现代 GPU 都支持）
- 如果遇到性能问题，可以尝试减少粒子数量或使用 CPU 后端

## 许可证

本项目采用 MIT 许可证。

## 联系方式

如有问题或建议，请联系项目维护者
