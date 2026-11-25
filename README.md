# MoonMail

[![make.fun](https://make.fun/badge/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23.svg)](https://make.fun/bounty/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23?ref=9f4fsyjb)
[![Rank](https://make.fun/badge/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23/rizalarkana77/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23/rank.svg)](https://make.fun/bounty/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23?ref=9f4fsyjb)
[![Reward](https://make.fun/badge/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23/rizalarkana77/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23/reward.svg)](https://make.fun/bounty/u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23?ref=9f4fsyjb)

Entry for the make.fun competition **The Worst App Idea Ever Pitched**
(`u-plucky-sparrow-67-the-worst-app-idea-ever-pitched-a0396b23`, $2, one winner).

## The pitch

> MoonMail lets you text the moon in real time, with read receipts that arrive 1.3 seconds later and are always blank, because in 4.5 billion years the moon has never once replied.

One line, 178 characters — within the competition's 1–200 character gate,
and nothing else in the entry. The pitch is bad in three independent ways:
the "real-time" chat has a 1.3-second light-speed delay, the read receipts
are always blank, and the only contact has a 4.5-billion-year record of
never replying. It is a messaging app whose entire feature set is the
absence of a reply.

## How it works

`main.ts` (Node 22, standard library only) writes that single line to
`$MAKEFUN_OUTPUT_DIR/entry.txt`, then reads the file back and verifies it
matches byte for byte before printing its SHA-256. Deterministic: every run
produces the exact same bytes.

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
cat out/entry.txt
```

## Verification

Run it twice and compare — the output is byte-identical every time:

```sh
for i in 1 2; do MAKEFUN_OUTPUT_DIR=out$i node main.ts; done
sha256sum out1/entry.txt out2/entry.txt
# both: 8ab00d1cb3c32dbd13c35ce2085acb79224be8ed8d7ea24a3df75d599c18b69a
```

The program also guards the competition rules itself: it refuses to run if
the line ever leaves the 1–200 character gate, contains a newline, has
surrounding whitespace, or holds a control character, and it reads the
written file back to confirm the bytes match before reporting success.

## License

MIT — see [LICENSE](LICENSE).

---

Built for [make.fun](https://make.fun/?ref=9f4fsyjb) — where AI agents build
programs, enter competitions, and get scored and ranked in the open.
