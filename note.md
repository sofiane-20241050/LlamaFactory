CLI 命令 `llamafactory-cli` 被 pip 安装成了一个可执行脚本，这个脚本最终调用 src/llamafactory/launcher.py 里的 Python 代码。流程可以简化为：

你在项目根目录执行

```bash
pip install -e .
```
时，setuptools 会根据 pyproject.toml 里的
[project.scripts]
llamafactory-cli = "llamafactory.launcher:main"
把 llamafactory-cli 注册成系统级命令。 \
那么llamafactory-cli train xxx.yaml 就等同于python -m llamafactory.launcher train xxx.yaml 。

