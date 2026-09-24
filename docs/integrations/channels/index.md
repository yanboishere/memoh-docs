# Channels

Channels connect Memoh bots to messaging platforms. Configure them from the bot **Platforms** tab so users can talk to the same bot through Slack, Telegram, Feishu, Discord, WeChat, and other platforms, as well as directly in the Memoh app.

## Channel capability matrix {#capability-matrix}

| Channel | Markdown | Attachments | Media | Streaming | Reactions | Buttons | Edit/unsend | Threads | Group chats |
|---------|----------|-------------|-------|-----------|-----------|---------|-------------|---------|-------------|
| [Telegram](./telegram.md) | ✅ | ✅ | ✅ | ✅ | — | ✅⁴ | ✅⁴ | — | ✅ |
| [Slack](./slack.md) | ✅ | ✅ | ✅ | ✅ | ✅ | ✅⁴ | — | ✅⁵ | ✅ |
| [Discord](./discord.md) | ✅ | ✅ | ✅ | ✅ | ✅ | ✅⁴ | — | — | ✅ |
| [Feishu (Lark)](./feishu.md) | ✅ | ✅ | ✅ | ✅ | ✅ | — | — | — | ✅ |
| [DingTalk](./dingtalk.md) | ✅ | ✅ | ✅ | —³ | — | — | — | — | ✅ |
| [WeCom](./wecom.md) | ✅ | ✅ | ✅ | ✅ | — | — | — | — | ✅ |
| [WeChat](./weixin.md)¹ | — | ✅ | ✅ | — | — | — | — | — | — |
| [QQ](./qq.md) | ✅ | ✅ | ✅ | —³ | — | — | — | — | ✅ |
| [LINE](./line.md)² | — | ✅ | ✅ | — | — | — | — | — | — |
| Web (built-in) | ✅ | ✅ | — | ✅ | — | — | — | — | — |

1. WeChat (personal) sends plain text only — Markdown is not rendered — and supports private chats only.
2. LINE sends outbound images as PNG/JPEG only and supports private chats only.
3. DingTalk and QQ deliver responses as complete blocks instead of token-by-token streaming.
4. Telegram is the only channel with message edit/unsend and inline buttons; the buttons on Slack and Discord are URL buttons.
5. Slack is the only channel that supports threads.

Feishu additionally supports a webhook-style inbound mode — see [Feishu Configuration](./feishu.md).

## WeChat Options

Memoh supports two different WeChat-related adapters:

- **WeChat (`weixin`)** is the personal-account style integration that relies on QR login.
- **WeChat Official Account (`wechatoa`)** is the official-account webhook integration that uses `App ID`, `App Secret`, `Token`, and optional AES settings.

Choose the one that matches your actual WeChat deployment model.

## General Setup Flow

1. Register an app or bot on the target platform.
2. Obtain credentials such as API tokens, app IDs, app secrets, or access tokens.
3. Add the channel from the bot **Platforms** tab in Memoh.
4. Save and enable the channel.

Depending on the platform, the final step may involve copying a webhook callback URL into the platform console, approving a QR login on mobile, or keeping a stream/WebSocket connection running through Memoh.
