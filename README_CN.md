

# .github
一种用于统一管理多语言 pre-commit 钩子，并支持云端自动检测的工作流

### 介绍
'.github '实现了 C++ 和 Python 代码的格式化、静态检查和自动管理。通过确保团队代码的一致性，包括风格、命名、格式和潜在的bug检查，提高开发效率，并减少手动审查的成本，可以提高代码质量。


### 特征
- 支持本地格式化C++代码（.cpp/.ino/.h）
- 支持本地格式化python代码（.py）
- 支持本地python的静态检查
- 支持本地对YAML文件格式检查
- 支持云端虚拟机静态编译检查C++代码
- 支持云端虚拟机静态格式检查python代码
- 支持云端自动tag版本检查

### 使用方法
[下载](https://github.com/jiaziui/action.git)

#### 安装与使用
- 将 '.github' 文件夹复制到项目根目录
- 确保已安装 Python 和 pip
- 环境准备
-- 安装 pre-commit:
  ```bash
  pip install pre-commit
  ```
-- 检查是否安装成功:
  ```bash
  pre-commit --version
  ```
-- pre-commit 初始化
  ```bash
  pre-commit install --config .github/config/.pre-commit-config.yaml
  ```
-- 完成此步骤后，即可正常使用 pre-commit 进行本地代码格式化、静态检查

- 提交:
  ```bash
  git add .
  # 第一次加载需要相对较长的时间，请耐心等待
  git commit -m "commit message"
  # 上面的命令只检查通过 git 添加的文件，使用下面命令可以检查所有文件
  pre-commit run --all-files --config .github/config/.pre-commit-config.yaml
  # 本地格式化和检查完成后即可推送代码。
  git add .
  git commit -m "commit message"
  git push
  ```
#### 卸载
- pre-commit 卸载
-- 这可以阻止 pre-commit 的使用，也就是说，会屏蔽本地的格式化和检查功能。
  ```bash
  pre-commit uninstall
  ```