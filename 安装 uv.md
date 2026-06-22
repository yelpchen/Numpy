在 Ubuntu 上使用 `uv` 管理 Python 虚拟环境非常高效，它比传统的 `python -m venv` 和 `pip` 快得多。核心流程分为三步：**安装 uv、创建项目及虚拟环境、激活使用**。

### 1. 安装 uv

推荐使用官方安装脚本，这是最简单的方式，无需额外配置。打开终端，执行以下命令：

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

安装完成后，为了让 `uv` 命令生效，需要**重新打开终端**，或执行以下命令刷新环境变量：

```bash
source ~/.bashrc
```

最后，验证是否安装成功：

```bash
uv --version
```

如果能看到版本号（例如 `uv 0.6.0`），就说明安装好了。

### 2. 进入项目并创建虚拟环境

`uv` 的做法是将虚拟环境（默认是 `.venv` 文件夹）直接放在项目根目录下，方便管理。

首先，进入你的项目文件夹。如果还没有项目目录，可以先创建一个：

```bash
# 创建并进入项目目录（请将 my-project 替换为你的项目名）
mkdir my-project && cd my-project
```

然后，使用 `uv venv` 命令创建虚拟环境：

```bash
# 创建虚拟环境，默认会使用你系统当前的 Python 版本
uv venv
```

如果想**指定某个 Python 版本**来创建环境，也很方便。`uv` 甚至会自动下载并安装你指定的、但系统中尚未安装的 Python 版本：

```bash
# 例如，创建一个使用 Python 3.12 的虚拟环境
uv venv --python 3.12
```

执行后，你会看到类似 `Creating virtual environment at: .venv` 的提示，项目根目录下会生成一个 `.venv` 文件夹。

### 3. 激活并使用虚拟环境

虚拟环境创建好后，按照 Linux 下通用的方法激活它：

```bash
source .venv/bin/activate
```

激活成功后，终端提示符前面会出现 `(.venv)`，表示你已进入隔离的开发环境。

之后，你就可以在这个环境下安全地安装项目依赖了，所有操作都会被限制在当前虚拟环境中：

```bash
# 安装依赖（速度比 pip 快很多）
uv pip install requests
```

当工作完成后，退出虚拟环境：

```bash
deactivate
```

### 小贴士

*   **更快地运行脚本**：如果想在虚拟环境中运行一个脚本但又不想手动激活环境，可以直接用 `uv run` 命令。例如：`uv run python my_script.py`，`uv` 会自动找到并激活项目下的 `.venv` 环境。
*   **删除环境**：如果需要彻底清理，直接删除项目根目录下的 `.venv` 文件夹即可，非常干净。