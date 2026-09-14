# 🚨 AlertZone Desktop

<div align="center">
    <img src="./icon/icon.png" width="128" height="128" alt="AlertZone Desktop 图标" />
    <p>局域网前端 · 后台告警 · 原生弹窗通知</p>
</div>

AlertZone Desktop 是 AlertZone 的原生桌面客户端，通过局域网连接 AlertZone Server，
查看监测画面并接收告警。摄像头与人物检测由 Server 负责，Desktop 无需安装 YOLO。

## ✨ 功能

- **实时监测**：查看状态、人数、持续时间和 FPS，支持实时预览、地址记忆与断线重连。
- **后台告警**：关闭窗口后驻留托盘，告警时显示置顶小窗并播放提示音。
- **灵活提醒**：支持人物放大、实时画面、全屏红色和仅声音等告警方式，可调整弹窗位置、大小及提示音。
- **自动监测**：支持连续监测，自定义确认时间、退出告警时长和等待再次监测时间。
- **原生体验**：支持浅色、深色及跟随系统主题，提供 Windows 托盘和 macOS 菜单栏快捷操作。

## 📦 下载

当前版本：**1.2.3**。前往 [GitHub Releases](https://github.com/HaoKnight/AlertZone-Desktop/releases/latest) 下载安装包，
更新内容见 [更新日志](release_notes.md)。

- **Windows**：64 位安装版或便携版（免安装）。
- **macOS**：Apple M 芯片版或 Intel 芯片版。

使用前，请确保电脑与已开启局域网服务的 AlertZone Server 处于同一局域网。

## 🚀 使用

1. 启动 AlertZone Server，开启“局域网连接”。
2. 在 Desktop 输入服务器地址，例如 `http://192.168.1.20:8765`；仅填写 IP 时默认使用端口 `8765`。
3. 开启“启用告警”，在“告警设置”中调整显示方式、监测时间和声音；通过“弹窗位置”调整告警小窗。
4. 最小化窗口、点击“后台运行”或关闭窗口后继续接收告警，通过托盘／菜单栏恢复窗口或选择“退出”。

主窗口打开时，告警直接显示在主页；最小化或后台运行时使用告警小窗。
选择“仅提示音提醒”时只播放声音，并禁用弹窗位置设置。
托盘中的“启用声音”与告警设置同步，取消勾选立即静音，再次启用恢复此前的提示音类型。

## 🛠️ 源码运行

推荐 Python 3.11 或 3.12。在项目目录中激活虚拟环境后运行：

```bash
python -m pip install -r requirements.txt
python start.py
```

运行依赖为 PySide6，macOS 会额外安装 PyObjC Cocoa。
开发时可运行 `python src/dev_preview.py`，保存源码后自动重启界面。

运行测试：

```bash
python -m unittest discover -s tests -v
```

## 🏗️ 构建

本地打包须在目标操作系统上执行：

```bash
python -m pip install -r requirements-build.txt
python build.py --onedir
```

产物位于 `dist/`；需要单文件版本时使用 `--onefile`，排查启动问题时使用 `--console`。
