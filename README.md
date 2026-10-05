# zcode-youtube-agent-skill

Eleven ZCode skills that run a YouTube channel. Free, MIT, no signup, no API key, nothing to
connect. Ported from
[Jakeschincariol/chatgpt-youtube-agent-skill](https://github.com/Jakeschincariol/chatgpt-youtube-agent-skill)
for ZCode.

One skill writes your script off 21 hook formulas and scores the hook before you waste a take on
it. One lints the title and the thumbnail as a single pairing. One reads your audience-retention
export and tells you the exact second people left and what you were saying when they did. One
turns a transcript into an edit decision list. One finds the Shorts already hiding inside a long
video. One goes and finds what is working in your niche and ranks it by how far each video beat
its own channel, not by how big the channel is.

**Nothing gets published until you do it.** These skills write. You upload.

## Install

In ZCode, open **Plugin Marketplace → Add → Add Plugin Marketplace** and paste this repo's URL:

```
https://github.com/sayedagd/zcode-youtube-agent-skill
```

Then find **YouTube Agent** under that marketplace in **Personal** and click **Install**. After
installing, pick a skill (for example `yt-script`) from the composer picker in a new task.

Requirements: Python on your PATH (any modern Python 3; the six tools use only the standard
library).

## The eleven

| skill | what it does |
|---|---|
| `yt-script` | writes the script off 21 hook formulas, scores the hook |
| `yt-package` | title and thumbnail linted as one pairing |
| `yt-viral` | finds what is working in your niche, ranked by channel-relative lift |
| `yt-retention` | reads your retention export, names the second people left |
| `yt-edit` | transcript to an edit decision list, dead air flagged |
| `yt-plan` | the week's upload schedule |
| `yt-comment` | drafts replies in your voice |
| `yt-seo` | description, tags, and search surface |
| `yt-chapters` | chapter markers off the transcript |
| `yt-shorts` | finds the Shorts hiding in a long video |
| `yt-audit` | reads a channel and says what is actually wrong |

## Your voice

Copy `templates/voice.md` to `~/.zcode/youtube/voice.md` and fill it in. Every skill reads it.
Or send three of your own videos and say "write my voice profile from these".

## The tools

Six dependency-free Python scripts, no packages to install: `hookscore.py`, `title.py`,
`deadair.py`, `chapters.py`, `retention.py`, `swipe.py`. They ship next to the skills that use
them.

## Changes from upstream

- Voice profile location `~/.codex/youtube/voice.md` → `~/.zcode/youtube/voice.md`.
- Tool examples use `python` instead of `python3` (Windows hosts often alias `python3` to the
  Microsoft Store stub).
- Cross-references between skills use skill names instead of `/yt-*` slash commands.

The Python scripts and `hooks.json` (the 21-formula data file) are byte-identical to upstream.

MIT — see `LICENSE` (copyright belongs to the upstream author).
