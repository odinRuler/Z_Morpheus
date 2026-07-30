---
name: apple-macos
description: "macOS Apple ecosystem integrations: Notes, Reminders, FindMy, iMessage, computer-use automation. Each subsection drives the corresponding Apple app purely from the terminal — no GUI scripting except computer-use."
version: 1.0.0
author: Hermes Agent
license: MIT
platforms: [macos]
metadata:
  hermes:
    tags: [macOS, Apple, Notes, Reminders, FindMy, iMessage, desktop, automation]
    related_skills: []
prerequisites:
  commands: [memo, remindctl, imsg, peekaboo]
---

# Apple macOS Ecosystem Integrations

This umbrella covers five Apple-only integrations. All five talk to the Apple ecosystem via the terminal — pick the subsection that matches the user's intent. **These skills require macOS** — see `platforms: [macos]`; they will NOT load on Linux/Windows.

Required first-time grants:
- Notes.app → System Settings → Privacy → Automation (memo)
- Reminders.app → System Settings → Privacy → Automation (remindctl)
- Messages.app → System Settings → Privacy → Full Disk Access (imsg)
- FindMy.app → System Settings → Privacy → Screen Recording (peekaboo / screencapture)
- computer_use → Screen Recording + Accessibility

---

## §A — Apple Notes via memo (formerly apple-notes)

`memo` CLI manages Apple Notes — create, search, edit, export. Notes sync via iCloud.

```bash
brew tap antoniorodr/memo && brew install antoniorodr/memo/memo  # install

memo list                   # all notes
memo list --folder Inbox
memo search "project plan"
memo show <id>
memo create --title "Idea" --body "text"
memo edit <id> --body "new text"
memo delete <id>
memo export <id> --format markdown
memo export <id> --format html
```

Triggers: user asks to create / view / search Apple Notes. Do NOT use for Obsidian (use `obsidian` skill) or Bear (separate app).

## §B — Apple Reminders via remindctl (formerly apple-reminders)

`remindctl` manages Apple Reminders — add, list, complete. Syncs via iCloud.

```bash
brew install steipete/tap/remindctl  # install

remindctl status         # check auth
remindctl authorize      # request Reminders access
remindctl list           # all reminders
remindctl list --today
remindctl add "Buy milk" --due 2026-12-31 --list "Groceries"
remindctl complete <id>
remindctl delete <id>
```

Triggers: user mentions "reminders", "Reminders app", wants a personal to-do on their iPhone. Do NOT use for cronjob alerts, calendar events, or project/task tracking (GitHub Issues, Notion). If user says "remind me" but means an agent alert → clarify first.

## §C — Find My via FindMy.app (formerly findmy)

Apple doesn't expose a FindMy CLI, so this skill drives the GUI with `screencapture` and optional `peekaboo` for better UI automation.

```bash
brew install steipete/tap/peekaboo  # optional, recommended

osascript -e 'tell application "FindMy" to activate'
# then screencapture or peekaboo to read device locations
peekaboo screens  # list UI elements with coordinates
screencapture -x ~/findmy-snapshot.png && vision_analyze(...)
```

User asks "where is my [device/cat/keys/bag]?", "find my iPhone", wants AirTag tracking → use this. Good for: pet/item location checks via AirTag, monitoring movement over time.

## §D — iMessage via imsg (formerly imessage)

`imsg` reads and sends iMessage/SMS via Messages.app.

```bash
brew install steipete/tap/imsg  # install

imsg list               # recent conversations
imsg history <chat-id>  # read a thread
imsg send <handle> "Hey — I'll be there in 10"   # phone number or Apple ID
imsg attach <handle> /path/to/photo.jpg "Thought you'd like this"
```

User asks to send an iMessage / read Messages.app history. Does NOT support group chat management or bulk messaging — always confirm before sending to more than one recipient. For non-Apple messaging (Telegram/Discord/Slack/WhatsApp) use the appropriate gateway channel.

## §E — macOS Computer Use (formerly macos-computer-use)

You have a `computer_use` tool that drives the Mac **in the background** — does NOT move the user's cursor, steal keyboard focus, or switch Spaces. The user keeps typing in their editor while you click around Safari in another Space.

Canonical workflow:

```
1. computer_use(action="capture", mode="som", app="Safari")
   → screenshot with numbered overlays on every interactable element
2. computer_use(action="click", target="<label-from-overlay>")
3. computer_use(action="type", text="...")
4. computer_use(action="scroll", direction="down")
```

Works with any tool-capable model (Claude/GPT/Gemini/open). Lets you operate any macOS app programmatically — including apps with no CLI or API.

Security model: the tool is bound by the same system permissions as the terminal running it. You can only interact with UI the user themselves could navigate manually.
