# UAssetGUI
[![Release](https://img.shields.io/github/v/release/atenfyr/UAssetGUI.svg?style=flat-square)](https://github.com/atenfyr/UAssetGUI/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/atenfyr/UAssetGUI/total.svg?style=flat-square)](https://github.com/atenfyr/UAssetGUI/releases)
[![Issues](https://img.shields.io/github/issues/atenfyr/UAssetGUI.svg?style=flat-square)](https://github.com/atenfyr/UAssetGUI/issues)
[![CI Status](https://img.shields.io/github/actions/workflow/status/atenfyr/UAssetGUI/build.yml?label=CI)](https://github.com/atenfyr/UAssetGUI/actions)
[![License](https://img.shields.io/github/license/atenfyr/UAssetGUI.svg?style=flat-square)](https://github.com/atenfyr/UAssetGUI/blob/master/LICENSE.md)

UAssetGUI 是一个为手动低级检查和修改虚幻引擎游戏资产而设计的工具。

<img src="https://i.imgur.com/cibmlbW.png" align="center">

## 安装
你可以在[本仓库的发布页面](https://github.com/atenfyr/UAssetGUI/releases)找到 UAssetGUI 的预编译二进制文件。

## 命令行参数
你可以使用命令行参数运行程序来执行各种任务，例如不打开 GUI 的情况下导出和导入 UAssetAPI JSON。

在以下情况中，引擎版本可以指定为 EngineVersion 枚举项（例如，`VER_UE4_23` 表示 4.23，`VER_UE5_0` 表示 5.0 等）或整数（例如，`23` 表示 4.23，`29` 表示 5.0 等）。指定映射集是可选的，但如果指定，必须是 Mappings 配置目录中的文件名（不带扩展名）。

### 导出到 JSON
```
UAssetGUI tojson <源文件> <目标文件> <引擎版本> [映射名称]
```

示例 1：`UAssetGUI tojson A.uasset B.json VER_UE5_1`

示例 2：`UAssetGUI tojson A.uasset B.json 27 Astro`

### 从 JSON 导入
```
UAssetGUI fromjson <源文件> <目标文件> [映射名称]
```

示例 1：`UAssetGUI fromjson B.json A.umap`

示例 2：`UAssetGUI fromjson B.json A.umap Outriders`

### 在 GUI 中打开特定文件
```
UAssetGUI [文件名] [引擎版本] [映射名称]
```

示例 1：`UAssetGUI`（仅打开 GUI 而不打开文件）

示例 2：`UAssetGUI test.uasset`

示例 3：`UAssetGUI test.uasset 23`

示例 4：`UAssetGUI test.uasset VER_UE5_4 Bellwright`

## 编译
如果你想自己编译 UAssetGUI，请继续阅读：

### 先决条件
* Visual Studio 2022 或更高版本
* Git

### 初始设置
1. 克隆 UAssetGUI 仓库：

```sh
git clone https://github.com/atenfyr/UAssetGUI.git
```

2. 切换到新的 UAssetGUI 目录：

```sh
cd UAssetGUI
```

3. 拉取所需的子模块：

```sh
git submodule update --init
```

4. 在 Visual Studio 中打开 `UAssetGUI.sln` 解决方案文件，在解决方案资源管理器中右键点击 UAssetGUI 项目，然后点击"设为启动项目"。

5. 在解决方案资源管理器中右键点击解决方案名称，然后按"还原 Nuget 包"。

6. 按"启动"按钮或按 F5 编译并打开 UAssetGUI。

## 贡献
无论是通过拉取请求还是问题报告，您的任何贡献都将不胜感激。

如果您有显示"无法保持二进制相等性"的虚幻引擎 .uasset 文件，请随时在 [UAssetAPI 问题页面](https://github.com/atenfyr/UAssetAPI/issues) 提交问题，并附上相关资产的副本、游戏名称、烘焙所用的虚幻版本以及游戏的映射文件（如果需要）。

## 许可
UAssetAPI 和 UAssetGUI 在 MIT 许可下分发，您可以在 [LICENSE 文件](LICENSE) 中查看详细信息。
