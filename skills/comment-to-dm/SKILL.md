---
name: comment-to-dm
description: "Builds an Instagram 'comment a word, get the freebie' automation FOR the user: picks the keyword, writes the public reply, follow check, DMs and email ask in their voice, then builds the whole thing in ManyChat (in Claude's browser) or Zernio (via its connector), so the user only reviews it and presses Go Live. Use when someone wants a comment-to-DM, keyword DM, auto DM, ManyChat automation, DM freebie or lead magnet for a post, or asks why their keyword automation isn't firing."
version: 1.0.0
author: getgitgirl
license: MIT
---

# comment to dm

Builds the comment-keyword → DM automation for an Instagram post. Someone comments a word, like GUIDE, and gets a DM with the freebie a few seconds later.

**You do the building, not the user.** The user's whole job is to answer a few questions, OK the copy, press Go Live (or tell you to), then test it. Only fall back to click-by-click instructions when you genuinely can't reach the tool.

Paths starting `references/` are relative to this skill's own folder, not the user's current folder.

The user's files live in `~/.comment-to-dm/`, so they work from any folder:
- `~/.comment-to-dm/dm-setup.md`: their answers to the setup interview
- `~/.comment-to-dm/automations/<KEYWORD>.md`: one record per automation

## First run: the setup interview

Look for `~/.comment-to-dm/dm-setup.md`. If it exists, read it and skip to "Building an automation". If it doesn't, ask these questions ONE AT A TIME, in plain English, then save the answers there (template: `references/dm-setup-template.md`) and show the user the file.

1. **Which tool do you use, or want to use?** ManyChat, Zernio, or not sure. If they're not sure, explain the trade-off in two lines:
   - ManyChat is the most common. You build it for them in your browser while they're logged in.
   - Zernio you build through its Claude connector, no browser needed, and it has no contact cap.
   - Both have paid plans, so tell them to check current pricing themselves. Never quote prices.
2. **Your Instagram handle.**
3. **How do your DMs sound?** Ask them to paste 2 or 3 DMs or captions they've written. Work out their tone from those (casual or polished, emoji or not, lowercase or normal case) and write it down. Don't ask them to describe their voice, people can't.
4. **Emoji:** any they always use, or never use?
5. **Follow check:** do they want people to follow before they get the freebie? Explain it in one line: you get more followers, but some people drop off at that step.
6. **Emails:** do they want to collect emails? If yes, which email tool and which tag or list the emails should go into.
7. **Things to never say:** words, claims or phrases they hate.

## Building an automation

### 1. Get the details
Ask for whatever is missing:
- the freebie (a link: Google Doc, PDF, Notion page, GitHub repo)
- the post it's for, and whether that post is live yet
- the keyword, if they already said one in the video or caption

### 2. Pick the keyword
- One word, uppercase, easy to spell, like GUIDE, PROMPT or EDIT.
- Avoid words people type anyway ("hey", "love", "yes"). They fire on normal comments.
- It must match the video and caption EXACTLY, or real commenters won't trigger it. If the post is already filmed, use the word they actually said.
- Put spelling variants in the same automation (FRAMES + HYPERFRAMES), never in two, or one comment gets two DMs.

### 3. Write the copy, in their voice from `dm-setup.md`
- **Public reply under the comment,** plus 2 variations so it doesn't look robotic, e.g. "check your dms", "just sent it over", "it's in your dms".
- **Opening DM (ManyChat only):** one short line whose only job is getting a tap, with a button, e.g. "you commented GUIDE, tap below and i'll send it straight over" + button "send it over". Zernio doesn't need this step.
- **Follow check message** (if they want one): short and friendly, e.g. "one tiny thing first, give me a follow and tap below and it's all yours".
- **The DM:** the link, plus one line on what to do with it first. Warm, not salesy. Don't put "save this" or "send this to a friend" in a DM, it reads as staged once someone's in a private chat.
- **Email ask** (if they want emails): say what they'll get and that they can unsubscribe anytime.

Show them all the copy and the settings in one short message. Wait for their OK before building anything.

### 4. Build it yourself
- **ManyChat:** follow `references/manychat.md`.
  - Use your browser tools: the desktop app's built-in browser, or the Claude in Chrome extension.
  - If the user is logged out, ask them to log in to ManyChat in that browser themselves. Never type their password.
  - Build the whole automation in its own tab and leave that tab open for review. ManyChat's quick builder has no draft save, so closing or leaving the tab loses it.
  - Fall back to click-by-click steps only if you can't reach ManyChat at all. Say why.
- **Zernio** (if its connector is available in this session): follow `references/zernio.md`. Create the automation **paused**.

### 5. Hand it over for the go
An automation can't be tested until it's live: ManyChat's quick builder has no draft, and a paused Zernio automation doesn't fire. So the order is review, go live, then test straight away.

1. **Review:** tell them in a few lines what you built (keyword, which post, follow check on/off, email on/off), and show the preview (a screenshot of ManyChat's preview phone, or the Zernio settings).
2. **Go live:** they press **Go Live**, or tell you to. You may press it (ManyChat) or switch it on (Zernio) only when they've said so in this conversation, for this automation.
3. **Test straight away:**
   - They comment the keyword from a second Instagram account. Commenting on your own post doesn't trigger it.
   - They check the public reply shows up, every DM arrives, and the link opens on a phone.
   - Once the post is live, check the automation is attached to the right post (or works on any post).
4. **If anything's wrong,** fix it right away. If it's sending something broken, pause it first (ManyChat: stop it; Zernio: `is_active: false`), then fix it.

### 6. Save a record
Write `~/.comment-to-dm/automations/<KEYWORD>.md` (template: `references/automation-log-template.md`). Include the tool, the keyword, the post, all the copy, the settings, the status (paused, built and waiting for go live, or live) and the test checklist. Never write that something is live when it's paused.

## Emails
- Zernio doesn't save emails to a field. People reply with their email in the Instagram inbox, and the user exports them by hand.
- ManyChat saves emails to the contact, but they stay in ManyChat until they're exported or connected to an email tool.
- Either way, remind them to move the emails into their email tool regularly, with the tag from `dm-setup.md`, and to only email people who actually agreed to it.

## "It isn't firing"
Check in this order:
1. **The plan's contact limit (ManyChat).** When it's full, new commenters silently get nothing. Look for a banner in the dashboard.
2. **Is the automation on?** Is it attached to the right post (or set to work on any post)?
3. **Does the keyword match the caption exactly?** Check the match setting too: whole word vs anywhere in the comment.
4. **Is someone stuck at the follow check?** Their DM may be in Message Requests.
5. **Is the same keyword live in two automations or two tools?**
6. **Was the test comment from the account itself?** That never triggers it.

## Rules
- Never send a DM, comment or reply on the user's behalf without their OK on the exact text.
- Never switch an automation on (Go Live) without their explicit go for that automation.
- Never type passwords or payment details. Never change plans, billing or account settings.
- Never invent details about the freebie. If you don't know what's in it, ask.
- Never paste API keys, passwords or tokens into chat. If a tool needs a key, tell them where to add it themselves.
