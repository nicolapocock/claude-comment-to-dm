# claude comment to dm

you know the "comment GUIDE and i'll send it to you" posts? i don't build mine anymore. claude builds the whole manychat automation for me, the keyword, the replies, the follow check, the DMs, the email step, and i just read it and press go live. sometimes i just tell claude to press it.

people are selling courses on this. this one's free.

> **status: early.** it's the exact process i use on [@getgitgirl](https://instagram.com/getgitgirl), but this public version is new. tell me what breaks.

## what it does

you tell claude something like:

```
set up a comment-to-dm for my new reel. keyword GUIDE, the freebie is [your link]
```

and claude:

1. checks the keyword won't fire on normal comments
2. writes the public reply, the follow check, the DMs and the email ask in your voice
3. shows you all of it and waits for your ok
4. opens manychat in its browser and **builds the whole automation for you**, saved as a draft
5. tells you exactly what to test, then you press go live, or tell claude to

you don't click through manychat at all.

## what you need

- the claude desktop app on a paid claude plan, using the code tab (that's claude code)
- claude's browser, so it can work in manychat: the built-in browser in the desktop app, or the claude in chrome extension
- a manychat account, connected to your instagram professional account, and logged in inside that browser
- the freebie itself, as a link

or, if you use **zernio** instead of manychat, claude builds it through zernio's claude connector, no browser needed.

## install

open claude code and paste:

```
install the comment-to-dm skill from github.com/nicolapocock/claude-comment-to-dm
```

or in terminal:

```bash
npx skills add nicolapocock/claude-comment-to-dm -g
```

(the `-g` installs it for every folder, not just the one you're in)

## the first time

claude asks you a few quick questions (which tool, a couple of DMs you've written so it gets your voice, your emoji, whether you want a follow check or emails) and saves the answers in `~/.comment-to-dm/dm-setup.md`. you only answer once, every automation after that just uses it.

## things i learned the hard way (already built in)

- **contact limits:** when my manychat plan filled up, new commenters silently got nothing. claude checks for that banner first
- **keyword clashes:** a common word like "hey" fires on every "hey love this"
- **two words, one automation:** spelling variants go in the same automation, or people get two DMs
- **test from a second account:** commenting on your own post never triggers it
- **manychat drops letters** when it's typed into fast, so claude types in small chunks and checks every message before saving
- **emails** don't move themselves into your email tool, so export them regularly

## what it can't do yet

- it's only been tested with instagram
- if claude can't get into manychat in its browser (logged out, or a popup in the way), it'll tell you and walk you through the clicks instead
- zernio's connector setup isn't covered here, follow zernio's own docs for that

made by [@getgitgirl](https://instagram.com/getgitgirl). MIT licensed, use it however you like.
