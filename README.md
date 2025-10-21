

# .github
A framework for managing and maintaining multilingual pre-commit hooks and a workflow for cloud-based detection in this area.

### Introduction
'.github 'has implemented code normalization, static checking, and automated management for Python and Arduino/C++ libraries. Ensure the consistency of the team's code in terms of style, naming, format, and potential bug checking, improve development efficiency, and reduce the cost of manual review.

### Features
- Support local formatting of C++ code files (.cpp / .ino / .h)
- Support local formatting of Python code files (.py)
- Support local static analysis for Python
- Support local YAML file format checking
- Support cloud-based virtual machine static compilation checks for C++ code
- Support cloud-based virtual machine static format checks for Python code
- Support automatic tag version checking in the cloud

### Usage
[download](https://github.com/jiaziui/action.git)

#### install and use
- Copy the '.github' folder to the root directory of your project
- Ensure you have Python and pip installed
- Environmental preparation

-- Install pre-commit:
  ```bash
  pip install pre-commit
  ```
-- Check if the installation was successful:
  ```bash
  pre-commit --version
  ```
-- pre-commit initialization
  ```bash
  pre-commit install --config .github/config/.pre-commit-config.yaml
  ```
-- Once you reach this step, you can use all the tool sets normally

- commit:
  ```bash
  git add .
  # The first loading takes a relatively long time. Please wait patiently
  git commit -m "commit message"
  # The above sentence only checks the files added by git. Use the following command to check all files
  pre-commit run --all-files --config .github/config/.pre-commit-config.yaml
  # Once the local check formatting is completed, it can be pushed up
  git add .
  git commit -m "commit message"
  git push
  ```
#### uninstall
- pre-commit uninstall
-- This can block the use of pre-commit, that is, block local formatting and checking
  ```bash
  pre-commit uninstall
  ```