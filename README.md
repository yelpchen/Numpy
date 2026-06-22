# Numpy 学习笔记

这个项目用于记录我学习 Numpy 的过程，包括基础语法、数组操作、常用函数和练习代码。

## 项目内容

- `test.ipynb`：Jupyter Notebook 练习文件
- `安装 uv.md`：在 Ubuntu 上使用 `uv` 管理 Python 虚拟环境的笔记
- `.venv/`：项目虚拟环境目录

## 当前环境

- 系统：Ubuntu 24.04 LTS
- Python：3.12.3
- Numpy：2.4.6
- 编辑器：VS Code / Jupyter Notebook

## 运行方式

进入项目目录：

```bash
cd ~/文档/Project/Numpy
```

激活虚拟环境：

```bash
source .venv/bin/activate
```

验证 Numpy 是否可用：

```bash
python -c "import numpy as np; print(np.__version__)"
```

也可以直接在 VS Code 中打开 `test.ipynb`，选择当前项目的 Python/Jupyter 内核运行代码。

## 学习路线

### 1. Numpy 基础

- 导入 Numpy
- 创建数组
- 查看数组维度、形状和数据类型
- 使用 `arange`、`linspace`、`zeros`、`ones`、`full`

### 2. 数组索引和切片

- 一维数组索引
- 二维数组索引
- 切片操作
- 布尔索引
- 花式索引

### 3. 数组运算

- 数组和标量运算
- 数组之间的逐元素运算
- 广播机制
- 常用数学函数

### 4. 数组变形

- `reshape`
- `ravel`
- `flatten`
- `transpose`
- `concatenate`
- `stack`

### 5. 统计和聚合

- `sum`
- `mean`
- `max`
- `min`
- `std`
- `argmax`
- `argmin`

### 6. 综合练习

- 使用 Numpy 处理一组成绩数据
- 生成随机数组并做统计分析
- 模拟简单矩阵运算
- 对二维数组进行筛选和变形

## 示例代码

```python
import numpy as np

a = np.array([1, 2, 3, 4, 5])

print(a)
print(a.shape)
print(a.dtype)
print(a.mean())
```

## 学习记录

| 日期 | 内容 | 状态 |
| --- | --- | --- |
| 2026-06-22 | 创建 Numpy 学习项目 | 已完成 |
| 2026-06-22 | 学习 `import numpy as np` | 已完成 |

## 备注

后续可以把每个知识点拆成独立 Notebook，例如：

- `01_numpy_array.ipynb`
- `02_indexing_and_slicing.ipynb`
- `03_numpy_operations.ipynb`
- `04_statistics.ipynb`
