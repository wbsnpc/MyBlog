---
title: volta安装及使用
date: 2024-07-26 16:05:10
tags: ['volta','node','工具','前端']
categories: 教程
---
# 一、前言

### 什么是Volta

 `Volta` 是一种管理 JavaScript 命令行工具的便捷方式。

 `volta` 的特点：

* 速度

* 无缝，每个项目的版本切换

* 跨平台支持，包括 Windows 和所有 Unix shell

* 支持多个包管理器

* 稳定的工具安装-无需每次升级都重新安装!

* 可扩展性挂钩用于特定于站点的定制

### 为什么选择Volta

使用 Volta，您可以一次选择 Node 引擎，然后不再担心它。您可以在项目之间切换，而不必手动切换 nodejs 版本。你可以在工具链中安装 npm 二进制包，而不必定期重新安装它们，或者弄清楚它们停止工作的原因。

# 二、正文

### 快速设置和切换Node版本

获取并使用特定版本的Node:

```
volta install node@14
```

Volta 允许你用一个命令为一个项目选择节点引擎和包管理器:

```
volta pin node@12
```

Volta 将 Node 引擎的准确版本保存在 `package.json`，这样你就可以把你的选择提交给 git。从那时起，每次在项目目录中运行 Node 时，Volta 都会自动切换到您选择的同一版本 的 Node。类似的。所有的合作者都可以通过在他们的开发机器上安装 Volta 来做同样的事情。

### 安装Volta

在安装 Volta 前， 如果有使用其它的 nodejs 管理工具/nodejs，可以提前卸载（非必须）。

#### Unix 安装

在大多数 Unix 系统(包括 macOS)上，您可以使用一个命令安装 Volta:

```shell
curl https://get.volta.sh | bash
```

对于 bash, zsh 和 fish，这个安装程序将自动更新控制台启动脚本。如果您希望防止修改控制台启动脚本，请参阅跳过 Volta 设置。要手动配置你的 shell 使用 Volta，编辑你的控制台启动脚本如下:

- 将 `VOLTA_HOME` 变量设置为 `$HOME/.volta`  

- 将 `$VOLTA_HOME/bin` 添加到 PATH 变量的开头

#### Window安装

对于 Windows，下载并运行 Windows 安装程序并按照说明操作。

> Volta 的功能依赖于创建符号链接，所以你必须：
> 
> - 启用开发者模式(推荐)
> 
> - 以提升的权限运行 Volta(不推荐)

### 管理工具链

可以使用两个命令控制由 Volta 工具链管理的工具: `Volta install` 和 `Volta uninstall`。

#### 安装 node 引擎

要将工具安装到工具链中，需要设置该工具的默认版本。Volta 将始终使用这个默认值，除非您在一个已配置 Volta 使用不同版本的项目目录中工作。当您选择默认版本时，Volta 也会将该版本下载到本地缓存中。

例如，您可以选择 node 的确切版本作为默认版本:

```shell
volta install node@14.15.5
```

不需要指定一个精确的版本，在这种情况下，Volta 会选择一个合适的版本来匹配你的请求:

```shell
volta install node@14
```

也可以指定最新版本，或者甚至完全不选择版本，Volta 将选择最新的 LTS 版本:

```shell
volta install node
```

运行了这些命令中的一个，在 PATH 环境(或 Windows 中的 PATH)中由 Volta 提供的节点可执行文件将在默认情况下自动运行选择的 node 版本。

同样地，你可以使用 `volta install npm` 和 `volta install Yarn` 分别选择 npm 和 Yarn 包管理器的版本。这些工具将使用您选择的 Node 的默认版本运行。



### 管理项目

Volta 允许团队或协作者社区标准化他们在项目中使用的开发工具。 

#### 固定 Node 引擎

volta pin 命令允许你为项目选择 Node 引擎和包管理器版本:

```shell
volta pin node@12.20
volta pin yarn@1.19
```

Volta 会把这个放在你的 package.json，这样你就可以把你选择的工具提交到版本控制:

```json
"volta": {
  "node": "12.20.2",
  "yarn": "1.19.2"
}
```

这样，每个使用 Volta 在项目上工作的人都会自动获得您选择的相同版本。

```shell
node --version # 12.20.2
yarn --version # 1.19.2
```



### Volta 命令

```powershell
Volta 1.1.1
The JavaScript Launcher ⚡

    To install a tool in your toolchain, use `volta install`.
    To pin your project's runtime or package manager, use `volta pin`.

USAGE:
    volta [FLAGS] [SUBCOMMAND]

FLAGS:
        --verbose    Enables verbose diagnostics
        --quiet      Prevents unnecessary output
    -v, --version    Prints the current version of Volta
    -h, --help       Prints help information

SUBCOMMANDS:
    fetch          Fetches a tool to the local machine
    install        Installs a tool in your toolchain
    uninstall      Uninstalls a tool from your toolchain
    pin            Pins your project's runtime or package manager
    list           Displays the current toolchain
    completions    Generates Volta completions
    which          Locates the actual binary that will be called by Volta
    setup          Enables Volta for the current user / shell
    run            Run a command with custom Node, npm, pnpm, and/or Yarn versions
    help           Prints this message or the help of the given subcommand(s)
```

`volta fetch` 将工具缓存到本地机器以供离线使用

`volta install` 设置工具的默认版本

`volta uninstall` 从工具链中卸载工具

`volta pin` 固定项目的运行时或包管理器

`volta list` 显示当前工具链

`volta completions` 命令补全

`volta which` 查看 volta 安装的工具的目录

`volta setup` 为当前用户/shell 启用 volta

`volta run` 运行带有自定义Node、npm、pnpm和/或Yarn版本的命令

`volta help` 输出帮助信息
