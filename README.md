# claude comment to dm

you know the "comment GUIDE and i'll send it to you" posts? this is a claude skill that sets those up for you. it picks the keyword, writes the public reply, the follow check and the DM in your own voice, then builds it in zernio or manychat, or walks you through the clicks if it can't.

it's the same process i use for every freebie on [@getgitgirl](https://instagram.com/getgitgirl), with the stuff i learned the hard way built in.

> **status: early.** i've run this process on my own account since august, but this public version is new. tell me what breaks.

## what you need

- an instagram professional account (business or creator)
- a manychat or zernio account connected to it
- [claude code](https://claude.com/claude-code) (the code tab in the claude desktop app works) on a paid claude plan
- the freebie itself, as a link

## install

open claude code and paste:

```
install the comment-to-dm skill from github.com/nicolapocock/claude-comment-to-dm
```

or in terminal:

```bash
npx skills add nicolapocock/claude-comment-to-dm
```

## use it

say something like:

```
set up a comment-to-dm for my new reel. the keyword is GUIDE and the freebie is [your link]
```

the first time, it asks you a few questions (which tool, how your DMs sound, whether you want a follow check or emails) and saves your answers in a `dm-setup.md` file, so you only answer them once.

then it:

1. checks your keyword won't misfire on normal comments
2. writes the public reply, the follow check, the DM and the email ask in your voice
3. shows you everything and waits for your ok
4. builds it **paused** in zernio, or as a **draft** in manychat, or walks you through it step by step
5. gives you a test checklist, and saves a record of the automation in your project

it never switches anything on, or sends anything, without your go.

## zernio or manychat?

- **manychat** is the one most people use. you set it up by clicking in its dashboard, so claude either builds it in your browser (if you let it) or walks you through it.
- **zernio** has a claude connector, so claude can build the automation for you directly. it also has no contact cap, which matters once lots of people comment.

both have paid plans, check their sites for current pricing.

## things i learned the hard way (already in the skill)

- **contact limits:** when my manychat plan filled up, new commenters silently got nothing, no error anywhere
- **keyword clashes:** a common word like "hey" fires on every "hey love this"
- **two words, one automation:** put spelling variants in the same automation, or people get two DMs
- **test from a second account:** commenting on your own post never triggers it
- **emails:** they don't move themselves into your email tool, so export them regularly

## what it can't do yet

- it's only been tested with instagram
- zernio's connector setup isn't covered here, follow zernio's own docs for that
- manychat building in the browser depends on claude being able to control your browser. if it can't, you get click-by-click steps instead

made by [@getgitgirl](https://instagram.com/getgitgirl). MIT licensed, use it however you like.
