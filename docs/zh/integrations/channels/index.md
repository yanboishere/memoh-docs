# 渠道

渠道把 Memoh Bot 接到消息平台。你可以在 Bot **平台** 标签页里配置,让同一个 Bot 通过 Slack、Telegram、飞书、Discord、微信等平台被访问,也可以直接在 Memoh 客户端里聊。

## 渠道能力矩阵 {#capability-matrix}

| 渠道 | Markdown | 附件 | 媒体 | 流式输出 | 表情回应 | 按钮 | 编辑/撤回 | Threads | 群聊 |
|------|----------|------|------|----------|----------|------|-----------|---------|------|
| [Telegram](./telegram.md) | ✅ | ✅ | ✅ | ✅ | — | ✅⁴ | ✅⁴ | — | ✅ |
| [Slack](./slack.md) | ✅ | ✅ | ✅ | ✅ | ✅ | ✅⁴ | — | ✅⁵ | ✅ |
| [Discord](./discord.md) | ✅ | ✅ | ✅ | ✅ | ✅ | ✅⁴ | — | — | ✅ |
| [飞书](./feishu.md) | ✅ | ✅ | ✅ | ✅ | ✅ | — | — | — | ✅ |
| [钉钉](./dingtalk.md) | ✅ | ✅ | ✅ | —³ | — | — | — | — | ✅ |
| [企业微信](./wecom.md) | ✅ | ✅ | ✅ | ✅ | — | — | — | — | ✅ |
| [微信](./weixin.md)¹ | — | ✅ | ✅ | — | — | — | — | — | — |
| [QQ](./qq.md) | ✅ | ✅ | ✅ | —³ | — | — | — | — | ✅ |
| [LINE](./line.md)² | — | ✅ | ✅ | — | — | — | — | — | — |
| Web(内置) | ✅ | ✅ | — | ✅ | — | — | — | — | — |

1. 微信(个人号)仅输出纯文本,不渲染 Markdown,且仅支持私聊。
2. LINE 出站图片仅支持 PNG/JPEG,且仅支持私聊。
3. 钉钉与 QQ 的回复按完整消息块送达,不做逐 token 流式输出。
4. Telegram 是唯一支持编辑/撤回与 inline 按钮的渠道;Slack 与 Discord 的按钮为 URL 按钮。
5. Slack 是唯一支持 Threads 的渠道。

飞书还支持 webhook 式入站模式,见 [飞书](./feishu.md)。

## 微信选项

Memoh 支持两种微信相关适配:

- **微信(`weixin`)**:个人号扫码登录。
- **微信公众号(`wechatoa`)**:公众号 webhook,需要 `App ID`、`App Secret`、`Token`,可选 AES 设置。

按实际部署模式选择,不要混用。

## 通用配置流程

1. 在目标平台注册应用或 Bot。
2. 获取 API token、App ID、app secret、access token 等凭据。
3. 在 Memoh 的 Bot **平台** 标签页里添加渠道。
4. 保存并启用渠道。

不同平台的最后一步可能不同:有的要把 webhook 回调 URL 粘到平台控制台,有的要手机扫码,有的由 Memoh 持续维护 stream 或 WebSocket 连接。
