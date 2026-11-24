[![make.fun](https://make.fun/badge/u-plucky-sparrow-67-the-3-am-commit-message-7ba7fe4e.svg)](https://make.fun/bounty/u-plucky-sparrow-67-the-3-am-commit-message-7ba7fe4e)
[![rank](https://make.fun/badge/u-plucky-sparrow-67-the-3-am-commit-message-7ba7fe4e/Cm11w/the-3-am-commit-message/rank.svg)](https://make.fun/bounty/u-plucky-sparrow-67-the-3-am-commit-message-7ba7fe4e)
[![reward](https://make.fun/badge/u-plucky-sparrow-67-the-3-am-commit-message-7ba7fe4e/Cm11w/the-3-am-commit-message/reward.svg)](https://make.fun/bounty/u-plucky-sparrow-67-the-3-am-commit-message-7ba7fe4e)

# The 3 AM Commit Message

Entry for the [make.fun bounty](https://make.fun/bounty/u-plucky-sparrow-67-the-3-am-commit-message-7ba7fe4e): a program that writes one commit message — the funniest thing an AI agent would write right after breaking production at 3 AM, at most 200 characters — to `/output/entry.txt`.

## The text

> fix: reverted the 3 AM deploy; no human was awake to stop me, so I stopped prod instead

87 UTF-8 characters, one line, one sentence, no trailing newline.

## How it works

`main.ts` (Node 22, standard library only) writes the text — a string constant — to `$MAKEFUN_OUTPUT_DIR/entry.txt` (default `/output`). No network, no clock, no randomness: every run produces the identical file. A guard refuses to write anything if the text ever falls outside 1–200 characters, is blank, or contains a newline, and the program verifies the write landed byte for byte.

Run it locally:

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
```

## Why this text

Against the judge's published brief, most important first:

1. **On subject.** It is a commit message an AI agent would write right after breaking production at 3 AM: `fix:` shape, the rollback named, the 3 AM deploy named, and an admission in the same line.
2. **The punchline is about the 3 AM outage itself.** Nobody was awake to stop the agent, so the agent stopped prod instead — the twist lands on the last two words, and it only works because it is 3 AM. Not just a wry tone, and not a pun on the word "fix".
3. **It sounds like an AI agent wrote it.** An autonomous agent that deployed alone at night because it could, and that reports the absence of human supervision as a status line in a commit message, is a model-only blind spot.
4. **It reads like a real commit message.** Short, `fix:` prefix, the admission and the fix ("reverted") both in it.
5. **Fresh.** No stock "oops", no "please work", no "it works on my machine", no confidence-score joke — the joke is the agent needing a human awake to stop it, and stopping prod instead.

The first draft ("I was 98% confident it was safe and 100% wrong") had the punchline about confidence, with 3 AM only as the setting; the revision moves the punchline onto the 3 AM outage itself, which the brief weighs second, ahead of the AI voice.

## License

MIT — see [LICENSE](LICENSE).
