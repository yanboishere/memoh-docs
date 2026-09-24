# Quick Start

Go from nothing to a working bot in about ten minutes: install the app, sign in, create your first bot, and reach it from a chat platform.

## Prerequisites

- A computer running macOS, Windows, or Linux.
- A [Memoh Cloud](https://app.memoh.net) account — you can create one during sign-in.

That is all. Memoh Cloud comes with hosted models (DeepSeek, Kimi, GPT, Claude, and more), so you do not need an API key to start.

## Step 1: Install Memoh

Download the app for your platform from the [download page](https://memoh.ai/desktop) — macOS (DMG), Windows (installer), or Linux (AppImage/deb/rpm) — and open it.

## Step 2: Sign in

On the connect screen, choose **Memoh Cloud** and sign in, or create an account.

::: tip Joining a team?
If your team already uses Memoh, enter the address your administrator gave you instead, then sign in with the account they issued.
:::

## Step 3: Create your first bot

1. Go to **Bots → New Bot**, give it a name and a display name.
2. On the bot's **General** tab, pick its chat model. Hosted models are ready to use; to bring your own API key instead, see [LLM Providers](../integrations/providers/llm.md).
3. Click the bot's **Chat** button and say hello. A reply confirms everything works.

Each bot has its own workspace, memory, and settings; see [Bot](./bot.md) for every tab.

## Step 4: Give it a real task

A bot is more than a chat window — it has a workspace with a real filesystem and terminal. Upload any document in the chat and try:

```text
Summarize this document into five key points and save the summary
as summary.md in your workspace. Do not modify the original file.
```

The bot reads the file, writes the result into its workspace, and reports back. Browse what it produced under **Files**.

## Step 5: Reach it from a chat platform

1. Open the bot's **Platforms** tab and click **Add**.
2. Pick a platform — Telegram, Slack, Discord, Feishu, DingTalk, WeCom, WeChat, QQ, LINE, and more — and paste that platform's credentials.
3. Message the bot from that platform. The first message creates a session; send `/help` to see the available slash commands.

From then on you can hand off a task from your phone and collect the result in the same conversation. Per-platform setup guides live under [Channels](../integrations/channels/index.md).

## What's next

| Goal | Read |
|------|------|
| Take the full tour: instructions, tasks, workspace, browser | [Get Started](./get-started.md) |
| Let the bot remember users across sessions | [Memory](./memory.md) |
| Run scheduled or recurring tasks | [Schedule](./schedule.md) |
| Give the bot files, shell access, and a browser | [Workspace](./container.md) |
| Let bots work on this computer | [Computers](./computers.md) |
| Add tools via MCP servers | [MCP](./mcp.md) |
| Teach the bot reusable procedures | [Skills](./skills.md), [Supermarket](./supermarket.md) |
| Control who can talk to the bot | [Access Control](./access.md) |

::: tip Need help?
Questions about plans, credits, or your account — or anything this site doesn't cover — are answered in the [Help Center](https://memoh.ai/help), where you can also reach the Memoh team.
:::
