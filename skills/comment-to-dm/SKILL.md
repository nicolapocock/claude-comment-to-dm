---
name: comment-to-dm
description: "Sets up an Instagram 'comment a word, get the freebie' automation: picks the keyword, writes the public reply, the follow check, the DM and the email ask in the user's own voice, then builds it in Zernio or ManyChat (or walks them through the clicks). Use when someone wants a comment-to-DM, keyword DM, auto DM, DM freebie or lead magnet for a post, or asks why their keyword automation isn't firing."
version: 1.0.0
author: getgitgirl
license: MIT
---

# comment to dm

Builds the comment-keyword → DM automation for an Instagram post. Someone comments a word, like GUIDE, and gets a DM with the freebie a few seconds later.

## First run: the setup interview

Look for `dm-setup.md` in the current project folder. If it exists, read it and skip to "Building an automation". If it doesn't, ask these questions ONE AT A TIME, in plain English, then save the answers to `dm-setup.md` (template: `references/dm-setup-template.md`) and show the user the file.

1. **Which tool do you use, or want to use?** ManyChat, Zernio, or not sure. If they're not sure, explain the trade-off in two lines:
   - ManyChat is the most common, and you set it up by clicking in its dashboard.
   - Zernio can be built for you directly through its Claude connector, and it has no contact cap.
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
- **Follow check message** (if they want one): short and friendly, e.g. "one tiny thing first, give me a follow and tap below and it's all yours".
- **The DM:** the link, plus one line on what to do with it first. Warm, not salesy. Don't put "save this" or "send this to a friend" in a DM, it reads as staged once someone's in a private chat.
- **Email ask** (if they want emails): say what they'll get and that they can unsubscribe anytime.

Show them all the copy and the settings in one short message. Wait for their OK before building anything.

### 4. Build it
- **Zernio** (if its connector is available in this session): follow `references/zernio.md`. Create it **paused**, and only switch it on when the user says go.
- **ManyChat:** follow `references/manychat.md`.
  - If you can control their browser and they've said you can, build it as a draft.
  - Otherwise walk them through it click by click, with the copy ready to paste.
  - Never click Go Live yourself.

### 5. Test before going live
1. Test it from a second Instagram account. Commenting on your own post doesn't trigger it.
2. Check every message arrives, and that the link opens on a phone.
3. Once the post is live, check the automation is attached to the right post (or works on any post, if it's set up that way).

### 6. Save a record
Write `dm-automations/<KEYWORD>.md` in their project (template: `references/automation-log-template.md`). Include the tool, the keyword, the post, all the copy, the settings, the status (paused, draft or live) and the test checklist. Never write that something is live when it's paused.

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
- Never switch an automation on without their explicit go.
- Never invent details about the freebie. If you don't know what's in it, ask.
- Never paste API keys, passwords or tokens into chat. If a tool needs a key, tell them where to add it themselves.
