# Working with Bots

[Quick Start](./quick-start.md) gets a bot running; this page is about working with one well — what to delegate, how to phrase it, where rules should live, and when one bot should become two. It links to the setup pages instead of repeating them.

## What to hand off

A task is a good fit for a bot when three things hold:

- **A clear outcome.** You can say what should exist when the work is done — a file, a message, a table.
- **Reachable sources.** The files, sites, or conversations involved are ones the bot can actually get to: uploaded into its workspace, connected as a channel or service, or public.
- **A checkable result.** You can tell at a glance whether the output is right, so reviewing stays cheap.

When all three hold, start read-only anyway: let the bot read and organize first, review a few outputs, then grant more. Every scenario in [Use Cases](./use-cases.md) begins this way.

## State the request

A good request answers five questions — outcome, source, constraints, format, checkpoint. The table is in [Quick Start](./quick-start.md#step-4-give-it-a-task); here is what the difference looks like in practice.

::: warning Vague
> Keep an eye on tech news and send me anything interesting.
:::

No source (which sites or repositories?), no delivery time, and "interesting" is a judgment the bot has to make for you. Every digest becomes a coin flip.

**Instead:**

::: tip Specific
> Every weekday at 8am, summarize releases and notable issues from the repositories I follow over the last 24 hours, and send them to me as one digest. Cite a source for every item; if something is uncertain, say so instead of guessing.
:::

::: warning Vague
> Clean up this spreadsheet.
:::

"Clean" is undefined: which rows count as dirty, may the original file change, and what should come back? The bot has to guess three times before it starts.

**Instead:**

::: tip Specific
> Remove every row with an empty email column from the CSV I just uploaded. Give me the cleaned file and tell me how many rows you dropped. Do not modify the original file.
:::

The pattern in both rewrites: name the sources, bound the actions, and make the result something you can verify in one look.

## Where rules live

Two kinds of instruction, two homes:

- **Permanent rules** belong in the bot's instructions on its detail page — its role, format standards, standing constraints. They apply to every future session.
- **One-off asks** belong in the message — today's file, this week's exception.

When a correction should stick, promote it: phrase it as a durable rule and move it into the instructions, exactly as [Quick Start](./quick-start.md#step-7-review-then-make-it-stick) step 7 shows. When a whole routine repeats, save it as a [Skill](./skills.md) so one sentence invokes it; preferences the bot should recall on its own belong in [Memory](./memory.md).

## When to split bots

One bot, one job. A bot with a single focused job accumulates context that keeps helping it; a do-everything bot dilutes its own instructions and memory. Both [Quick Start](./quick-start.md) and the [Overview](./overview.md) make the same point, so here is only the practical test: when a new request has a different audience, different sources, or needs different permissions than the bot's current job, create a second bot.

Each bot gets its own workspace, memory, channels, and permission boundary, and bots cannot see into each other. Splitting also keeps permissions honest — the bot that only reads release notes never needs the right to execute commands.

## Approval habits

Grant the level a job needs and no more — workspace access is tiered from chat through read, write, execute, and manage; see [Access Control](./access.md).

In practice:

1. Start new routines read-only and keep write and execute tool calls behind approval.
2. Review the first few runs before widening anything.
3. Keep actions that leave the workspace — messages to other people, anything external — behind approval even after the routine feels safe.

This is the same path the [Use Cases](./use-cases.md#from-example-to-routine) checklist walks: approving a few requests costs far less than undoing a wrong write.
