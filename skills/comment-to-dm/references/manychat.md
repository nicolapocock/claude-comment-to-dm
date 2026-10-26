# Building it in ManyChat

You build this yourself in the browser (the desktop app's built-in browser, or the Claude in Chrome extension), in the user's logged-in ManyChat at app.manychat.com. The user doesn't click anything until Go Live.

**Important: the quick builder has no "save draft".** Its only button is Go Live. What you build lives in that open tab until someone presses it. So:
- Build it in its own tab, and leave that tab open for the user to review.
- Never navigate away from that tab or close it before they've decided, or the whole build is lost.
- Use a separate tab for anything else.

## Before you start
1. Open app.manychat.com in a new tab.
   - If it shows a login page, ask the user to log in themselves in that browser. Never type their password.
   - ManyChat's emailed sign-in link opens in their default browser, so if you're in a different browser, they need to sign in with Google, Facebook or Apple inside yours.
2. Close any upgrade popup with its X. Never click an upgrade or plan button.
3. Check the top banner. "Your new contacts aren't getting automations. You've hit your plan limit" means new commenters won't get anything. Stop and tell the user before building.
4. The Instagram account must be a professional account (business or creator), connected to ManyChat.

## Build it
The page layout moves every time you change an option (picking a post type collapses the post grid, toggles open new fields). **Take a fresh screenshot, or find the element again, before every click.** Prefer element references from `find` over coordinates.

1. On the home screen, open the quick automation **Auto-DM links from comments**.
2. **When someone comments on**, pick one:
   - "a specific post or reel" (choose it from the grid)
   - "any post or reel": fine when the keyword is unique
   - "next post or reel" if the post isn't up yet
3. **And this comment has → a specific word or words:** type the keyword. Separate variants with commas.
4. **Reply to their comments under the post:** toggle it on, then replace the 3 default replies with the approved reply and its variations.
5. **They will get → an opening DM:** select all, delete the default text, type the approved opening DM. Then replace the button label (e.g. "send it over").
6. **A DM asking to follow you before they get the link** (if wanted): toggle it on and paste the follow message. The button label is fixed by ManyChat.
7. **A DM asking for their email** (if wanted): toggle it on. In this builder it always comes BEFORE the link. If they'd rather it came after, say so and offer the full Flow Builder.
8. **And then, they will get → a DM with a link:** type the DM text, then click **Add A Link**. A popup asks for the button label and the URL. Fill both and click that popup's Save. That only adds the link to the form, it doesn't publish anything.
9. There's also an optional **follow up DM if they don't click the link**. Leave it off unless they asked for one.
10. Check the preview phone on the right. Its Post / Comments / DM tabs show each step.
11. Take a screenshot of the preview, show the user, and leave the tab open. **Don't press Go Live** unless they've told you to for this automation.
12. Once it's live, give them the test (comment from a second account). If something's wrong, open it from My Automations to edit or stop it.

## How to type into ManyChat
- Its message fields can drop letters under fast typing. Type in short chunks of about 25 to 30 characters, with a pause of about a second between them.
- After each field, zoom in and check the text, emoji included.
- If anything is wrong, select all in that field, delete it and retype the whole thing. Don't try to patch one letter.
- To replace default text: click the field, press cmd+a, press Delete, then type.

## If you get stuck
If you can't get past a step (a popup you can't close, a page that won't load, a permission prompt), say what you see. Then give the user click-by-click steps for the rest, with the copy ready to paste.
