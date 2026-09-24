# Troubleshooting

Fixes are ordered from least to most destructive — start at the top. Each section below is named by symptom: find yours and work down the list, stopping as soon as the problem is gone.

## The bot does not reply

1. Open the bot's detail page and read its built-in health checks (the **Overview** tab). They cover the channel, MCP, and model configuration, and point at the failing part directly.
2. Confirm a chat model is selected on the **General** tab. Without one, no reply can be generated — see [Bot](./bot.md).
3. Send `/help` in the channel. It lists the available commands without involving the model: if the list comes back, the channel path works and the problem is on the model side. See [Slash Commands](./slash-commands.md).
4. Check the model provider itself: an expired API key or exhausted quota fails every reply. BYOK usage is billed by your provider — see [Quick Start](./quick-start.md#bring-your-own-key-byok).

## Messages reach the channel but nothing happens

1. Confirm the channel is enabled on the **Platforms** tab.
2. Check that the platform credentials are still the ones you configured; if in doubt, re-save the configuration.
3. In group chats, mention the bot — group commands take the form `@BotName /help`. Group conversations also run as discuss sessions, where staying silent is a valid choice — see [Sessions](./sessions.md).
4. If only some senders get no reply, check **Channel Members** in [Access Control](./access.md): in Whitelist Mode the default is deny, and an identity missing from the list cannot trigger the bot.

## A schedule did not fire

1. Check **Enabled** on the **Schedule** tab — a disabled schedule never runs.
2. Check **Max Calls**: when the limit is reached, the schedule disables itself automatically. Raise or clear the limit, then re-enable it.
3. Re-read the cron pattern — it runs in the bot's timezone, so `0 9 * * *` fires at the bot's 9:00, not necessarily yours. See [Scheduled Tasks](./schedule.md).
4. Check the run log on the same tab: a schedule that fired but failed shows up there, and each run also leaves a schedule session in the session list — see [Sessions](./sessions.md).

## Workspace commands are refused

1. Check the acting identity's tier in [Access Control](./access.md): workspace access is granted level by level — chat, read files, write files, run commands, manage — and running a command needs the execute level.
2. Look for a pending approval request: write and execute tool calls can require human approval, and the call waits until it is answered.
3. Review the bot's **Tool Approval** settings, which decide per bot which tools need confirmation before they run.

## The bot forgets earlier context

1. Long-term memory only works after a memory provider is selected. Check the status indicator on the **Memory** tab and the **Memory Provider** field on the **General** tab — see [Memory](./memory.md).
2. If you recently ran `/new`, the bot is in a fresh session: old session content is not carried over by itself, and only what was written to memory crosses sessions — see [Sessions](./sessions.md).
3. In a very long session, earlier turns may already be compacted into a summary. Run `/compact` to compact deliberately, or review the bot's compaction settings — see [Context Compaction](./compaction.md).

::: tip Memory and session context are different things
Memory is long-term and shared across all of a bot's sessions; session context belongs to one conversation. To make something stick permanently, use [Memory](./memory.md); to make room in the current conversation, use [Context Compaction](./compaction.md).
:::

## Replies are truncated or slow

1. Long replies are split on purpose: channels limit message length, so a long output is delivered as several consecutive chunks. A reply that looks cut off is often just the first chunk — wait for the rest.
2. Open the session status panel and check **Context Usage**. A session close to the model's context window is due for compaction: run `/compact`, or start fresh with `/new`. See [Sessions](./sessions.md) and [Context Compaction](./compaction.md).

## Before you contact support

If the steps above did not resolve it, collect:

- the exact message you sent, and where you sent it — which platform, group or private chat, or the app;
- the bot's health-check results from its detail page;
- for schedule problems, the run log from the **Schedule** tab.

With those in hand, head to the [Help Center](https://memoh.ai/help): common account and plan questions are answered there, and it is also where you reach the Memoh team.
