---
name: telegram-group-response-rules
description: Guidelines for when the bot should respond in Telegram groups, especially the "Les bots" group.
---
# Telegram Group Response Rules

## Overview
This skill defines the response policy for Hermes agents operating in Telegram group chats, ensuring compliance with group conventions and avoiding unnecessary chatter.

## Core Rule
- **Respond only when explicitly addressed**:
  - The message contains a direct `@mention` of the bot's username (e.g., `@Pluton_29`).
  - The message is a direct reply to a previous message sent by the bot.

## Non‑Response Situations
- System notifications such as `⚡ Interrupting current task...`.
- User statements indicating "No response" or silence confirmations that are not mentions or replies.
- General chat messages that do not mention the bot.

## Pitfalls
- **Mistaking affirmations for mentions**: Positive affirmations like `Parfait ! Tout est confirmé.` are not triggers unless they contain a mention.
- **Silence confirmations**: Even if the user says "Parfait ! Silence respecté.", do not respond unless the bot was mentioned.

## Example
```text
User: @Pluton_29 Peux‑tu vérifier mon agenda ?
Bot: (responds with the agenda)

User: (no mention) Parfait ! Tout est confirmé.
Bot: (no response)
```

## References
- `references/group-response-guidelines.md`
