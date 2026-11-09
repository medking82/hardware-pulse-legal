# Hardware Pulse（Microsoft Store 版）隐私政策

[English](PRIVACY.md) · [简体中文](PRIVACY.zh-CN.md)

最后更新：2026-10-31

Hardware Pulse 在你的电脑上读取硬件传感器，并在本机显示。它没有账户系统，不含分析、广告或遥测，也不会上传传感器读数、硬件型号、自定义名称、截图或使用记录。

## 在你电脑上处理的数据

- **传感器读数。** CPU、GPU、内存、存储、风扇和网络读数都在本机读取。当前快照保存在你的用户配置文件中；Pro 完整传感器的快照保存在 `%ProgramData%\HardwarePulseSensors`。网络读数只使用网卡的字节计数，从不检查数据包内容。
- **屏幕取样（可选）。** 低干扰和局部对比度会在内存中测量桌面面板背后屏幕区域的亮度，用来调整文字。图像不会被保存或传送。这些功能运行时，Windows 会把 Pulse 排除在截图之外；截图模式会解除这一排除 15 秒。
- **设置与日志。** 设置、额度刷新计划和简短的诊断日志保存在 `%LocalAppData%\HardwarePulse`。诊断日志只包含状态类别和时间，从不包含凭据或额度数值。

## 网络连接

- **AI 额度（每个服务分别选择开启）。** Codex 和 Claude 读取你已有的本机登录，并只把其令牌发送到 chatgpt.com 或 api.anthropic.com 的固定额度地址。Antigravity 通过环回地址从其本地语言服务器读取。DeepSeek 使用你输入的 API 密钥，该密钥以你当前 Windows 用户的 DPAPI 加密，只发送到 `https://api.deepseek.com/user/balance`。每个服务都会收到你的 IP 地址和 User-Agent。Pulse 不会调用模型、购买或更改账户。
- **下载 PawnIO（Pro，仅在你按下「安装 PawnIO 驱动」时）。** 官方安装程序从 github.com 下载：先从上游发布下载，失败时改用[本仓库中未经修改的镜像](https://github.com/medking82/hardware-pulse-legal/releases/tag/pawnio-2.2.0)。GitHub 会收到你的 IP 地址和 User-Agent。只有在文件的 SHA-256 与官方文件一致时，才会运行。
- **Microsoft Store。** Pro 授权检查和购买使用 Microsoft Store 服务，受 Microsoft 隐私声明约束。Pulse 只会得知你是否拥有 Pro 附加内容。

## 由你启动的系统更改

- **安装 PawnIO 驱动**：通过 Windows 管理员提示，安装 namazso 开发的 PawnIO 驱动。
- **开通 FPS**：通过管理员提示，请 Windows 把你的账户加入内置的 Performance Log Users 组，这样无需以管理员身份运行 Pulse 也能读取 FPS。你可以随时在「计算机管理」中把账户从该组移除。

## 联系方式

如有问题：support@hankee.com
