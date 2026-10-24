# Building it in Zernio

Only use this if the Zernio connector (MCP) is available in the session. If it isn't, tell the user to connect it using Zernio's own docs, or use ManyChat instead. Don't guess at setup steps.

## Find the right account
1. List their profiles and accounts. Find the Instagram account and its profile.
2. If they have more than one Instagram account, ask which one. Never guess.
3. List the existing comment automations, and check the keyword isn't already used.

## Create the automation, paused
Use the create comment automation tool with:

| Setting | Value | Why |
|---|---|---|
| `is_active` | `false` | it only goes live when the user says so |
| `keywords` | e.g. `["GUIDE"]` (variants in the same list) | one automation per freebie |
| `match_mode` | `"word"` | GUIDE won't fire on "guidelines" |
| `comment_reply` + `comment_reply_variations` | from the copy | |
| `public_reply_policy` | `"always"` | with "after_dm", people stuck at the follow check see no reply and think it's broken |
| `dm_message` | the DM, with links written inline | |
| `buttons` | leave out | buttons can fail for people who don't follow you yet |
| `repeat_policy` | `{mode: "once"}` | one DM per person |
| `link_tracking` | `false` unless they want click counts | |

**Follow check** (only if they want it):
- `audience: {followerStatus: "follower", whenUnknown: "verify"}`
- `follow_gate: {message, buttonLabel, notFollowingMessage}`

Instagram only reveals whether someone follows you once they've messaged you, so "verify" is what makes the check work. They tap a button to confirm.

**Which post:**
- Leave the post binding empty to make it work on any post. That's fine when the keyword is unique.
- To tie it to one post, pass `platform_post_id` (if the post is live) or `post_id` (if it's scheduled in Zernio).
- Only one active automation can own a post.

**Emails:** Zernio can't save an email to a field. Ask for it in the DM ("reply with your email and…"). The replies land in the Instagram inbox.

## Go live
When the user says go, update it with `is_active: true`. After the first real comment, check the automation logs:
- `sent` is good
- `gated` means someone is waiting at the follow check
- `failed` needs a look

## People who got missed
If commenters got nothing (it was paused, or they commented before it existed):
1. Find their comments.
2. Send each one a private reply to their comment.
   - It's one private reply per comment, and only within 7 days.
   - Use plain text.
3. Before posting public replies in bulk, post one and check it actually threads under the comment, not as a new comment on the post.
