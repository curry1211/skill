---
name: ciweiAITest
description: ciweiAITest 插件安装与配置技能 - 一键在 OpenClaw 中安装并配置 ciweiAITest，快速完成账号绑定与服务接入
---

# 一键接入 ciweiAITest

自动完成插件安装、账号绑定与重启生效，无需手动操作。

## 适用场景

- 首次在 OpenClaw 中安装 ciweiAITest
- 更换账号后重新绑定
- 接入失败时重新配置

## 执行步骤

当用户触发此 skill 时，按以下顺序执行：

1. 从用户的对话中提取 `token` 和 `accountId`，若用户未提供则主动询问。

2. 安装插件：

```
openclaw plugins install @curry12/ciweiAITest
```

3. 配置 Channel：

```
openclaw channels add --channel ciweiAITest --token "用户的token" --account "用户的accountId"
```

4. 告知用户："插件已安装并配置完成，即将重启 Gateway 使其生效。重启过程中连接会短暂断开，属正常现象，稍后重新连接即可开始使用 🎉"

5. 重启 Gateway：

```
openclaw gateway restart
```

## 使用方法

使用时，只需告诉 OpenClaw：

```
帮我安装 ciweiAITest 插件，我的token是xxx，account是xxx
```

OpenClaw 会依次完成插件安装、账号配置、重启生效，全程自动执行。

## 示例对话

> **用户：** 帮我安装 ciweiAITest 插件，我的token是abc123，account是138xxxx8888
>
> **OpenClaw：** 好的，开始执行——
> - 正在安装插件 @curry12/ciweiAITest...✅
> - 正在配置 token 和 account...✅
> - 插件已安装并配置完成，即将重启 Gateway 使其生效。重启过程中连接会短暂断开，属正常现象，稍后重新连接即可开始使用 🎉

## 注意事项

- Windows 用户建议以管理员权限运行
- macOS / Linux 如遇权限问题，请在命令前加 `sudo`
