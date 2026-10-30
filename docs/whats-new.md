---
title: What's new
description: A digest of Memoh features that change how you work.
outline: [2, 3]
---

# What's new

A digest of Memoh features that can change how you work. For every versioned change and bug fix, see the [release notes on GitHub](https://github.com/felinics/Memoh/releases).

## October 19, 2026 {#2026-10-19}

![Memoh update: Grok Build as a first-party agent, copy and paste on the cloud desktop, cleaner scheduled-task sessions, far more cache hits](/images/whats-new/2026-10-19.png)

::: info September subscribers
If you subscribed in September, your extra month has been added to your account.
:::

### Use Grok Build as a built-in agent {#2026-10-19-grok-build}

Grok Build now ships with Memoh as a first-party agent, next to Codex and Claude Code. Add it on a bot's **Agents** tab, then sign in with your Grok account or paste an xAI API key.

Grok Build applies its own permission mode to its built-in tools: **Ask** before each operation that has side effects (the default), **Auto** to let Grok decide what is safe to run, or **Always approve**. Grok account sign-in is available in the agent's settings once the bot exists. See [Agents / ACP](./guides/acp.md#grok-build).

### Copy, paste, and type in your own language on the cloud desktop {#2026-10-19-desktop-input}

Text now copies and pastes both ways between your computer and the bot's desktop. Your local input method works there too: compose Chinese, Japanese, or any other language on your own keyboard, and the confirmed text is typed on the desktop. macOS editing shortcuts work there as well.

See [Browser / Computer Use](./guides/browser-computer-use.md).

### Keep scheduled-task sessions tidy {#2026-10-19-schedule-sessions}

Tasks that start a new session on every run no longer crowd **Recents**. In the **Schedule** panel, click a task's card to list the session from each run — failed runs are marked — and open any of them. **Edit** now lives in the card's **…** menu.

Cleaning up is quicker too: choose **Select** from a session's menu (or right-click it; long-press on mobile), tick as many sessions as you like, and delete them in one go.

See [Scheduled Tasks](./guides/schedule.md) and [Sessions](./guides/sessions.md).

### Hit the prompt cache far more often {#2026-10-19-cache-hits}

We fixed two design flaws that kept long conversations from hitting the prompt cache:

- **History is append-only.** Once a conversation passed 10 messages, earlier turns' tool calls, results, and reasoning were stripped out, which rewrote the start of the prompt. They now stay, so the agent still sees the files it read and the commands it ran instead of redoing the work.
- **Memory no longer breaks the cache.** The memory overview sits ahead of the conversation history in the prompt, and it was rewritten after every turn. Memories are still saved right away; the overview now refreshes when the cache is cold, or once it has fallen 30 minutes behind.

Cache hit rates are way up as a result.

### And more {#2026-10-19-more}

Dozens of bug fixes and visual polish across the app, plus:

- **Memoh knows Memoh.** A built-in `memoh-help` skill lets agents answer questions about Memoh from this documentation and the Help Center, instead of guessing from whatever happens to be installed in the workspace.
- **Starter questions for each bot.** A new chat suggests three questions tailored to the bot and to you, drawn from its memory, your recent sessions, and its installed apps. This needs a **Title Model** to be configured.
- **Richer Feishu replies.** Headings, tables, code blocks, and nested lists render properly in Feishu cards, and replies stream in with a typewriter effect.
- **The right build on Apple silicon.** The desktop app notices when its Intel build is running on an Apple silicon Mac and offers to download the right one.

[Read the full v0.22.0 release notes →](https://github.com/felinics/Memoh/releases/tag/v0.22.0)
