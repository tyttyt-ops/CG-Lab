# CG-Lab

计算机图形学实验项目

## 项目结构

```
CG-Lab/
├── src/
│   └── Work0/              # 实验0：Taichi重力粒子系统
│       ├── config.py        # 配置参数
│       ├── main.py          # 主程序
│       ├── physics.py       # 物理系统
│       └── __init__.py
├── .gitignore              # Git忽略文件
├── .python-version         # Python版本
├── README.md               # 项目说明
├── pyproject.toml          # 项目配置
└── uv.lock                 # 依赖锁定文件
```

## 实验0：Taichi重力粒子系统

### 功能
- 使用Taichi库实现GPU加速的粒子系统
- 鼠标引力交互
- 粒子边界碰撞检测

### 运行方法

1. 安装依赖
```bash
pip install taichi
```

2. 运行程序
```bash
python src/Work0/main.py
```

### 配置参数

在 `src/Work0/config.py` 文件中可以调整以下参数：
- `NUM_PARTICLES`：粒子总数（卡顿请调小此数值，如 2000）
- `GRAVITY_STRENGTH`：鼠标引力强度
- `DRAG_COEF`：空气阻力系数
- `BOUNCE_COEF`：边界反弹能量损耗
- `WINDOW_RES`：窗口分辨率
- `PARTICLE_RADIUS`：粒子绘制半径
- `PARTICLE_COLOR`：粒子颜色

## 环境要求

- Python 3.12+
- Taichi 1.7.4+
