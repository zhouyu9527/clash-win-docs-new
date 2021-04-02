# 常见问题

<question-answer question="macOS 版本启动要求授权">

在第一次或更新 APP 后打开软件会提示用户授权，这是因为需要安装/更新用于设置系统代理的工具，如果不进行授权，General 中的 System Proxy 开关将无法打开。一般情况下，除非工具更新，否则除了第一次启动外不会重复需要授权。

</question-answer>

<question-answer question="macOS DMG 安装后无法打开，提示损坏">

网络下载应用被 Apple 添加隔离标识，终端输入命令解除即可：

```
sudo xattr -r -d com.apple.quarantine /Applications/Clash\ for\ Windows.app
```

</question-answer>

<question-answer question="系统代理自动关闭或打开">

[参考](https://github.com/Fndroid/clash_for_windows_pkg/issues/312)

</question-answer>

<question-answer question="General 端口显示为 0">

[参考](https://github.com/Fndroid/clash_for_windows_pkg/issues/671)

</question-answer>

<question-answer question="Killer 系列网卡无法开启 TAP/TUN 模式">

[参考](https://github.com/Fndroid/clash_for_windows_pkg/issues/1243#issuecomment-751165537)

</question-answer>

<question-answer question="Service Mode 无法安装（Windows）">

先确定系统安装了`.NET framework runtime`

然后尝试手动安装：

1. 点击 General 中的 Home Directory 打开文件夹，进入 service 子目录中
2. 打开 CMD，执行以下命令：

```
service.exe install
service.exe start
```

如安装出现错误，参考[这个 issue](https://github.com/Fndroid/clash_for_windows_pkg/issues/1627)

</question-answer>
