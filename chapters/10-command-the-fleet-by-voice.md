# Command the Fleet by Voice: Why Voice Dictation Triples the Instruction Throughput of a Parallel AI-Agent Workflow

> "We found that with speech recognition, the English input rate was 2.93 times faster ... than the keyboard." — Sherry Ruan et al., *Comparing Speech and Keyboard Text Entry for Short Messages in Two Languages on Touchscreen Phones* (2017)

It is the delivery week for Adrian's second client, and he has not typed a brief since Monday. Five lanes are running in five worktrees — the ingestion connector, the retrieval fixtures, the golden-question eval set, the admin export, the handoff document — each one carved out the way chapter 4 taught him, each one refused at the merge until its check goes green. What has changed is the sound of the room. He sits at the same kitchen table where he once drafted apologetic follow-ups to silent rejections, and he talks: a ninety-second spoken capsule sends lane three after the eval set; a one-sentence redirect pulls lane one out of a refactor nobody asked for; a verdict — "refused, the fixture check is red, rerun it" — goes into the log with a timestamp. Forty-one dispatches in the first two evenings, two merges refused by their own gates. It is the output of a small team, from one desk, and it costs what it honestly costs: five evenings and a Saturday morning of real focus — not a four-hour week. From the hallway his kids hand down their verdict: Daddy is talking to the computers.

Here is what should puzzle you about that scene. The agents were already doing all the typing in chapter 2. The worktrees were already isolated in chapter 4. Nothing about the fleet got smarter this week — the only thing that changed is the speed at which one man's judgment reaches it. So: if the agents do all the typing now, why did the operator's own words per minute just become the number that decides the week?

## The false belief: "Once the agents do the typing, my own throughput stops mattering"

This one is the natural conclusion of everything the playbook taught you, which is what makes it hard to spot. You retired the typing seats; the fleet produces; you decide — and deciding, the belief concludes, is not measured in words per minute. The error is the quiet assumption that judgment travels from your head to the fleet for free. It does not. Every piece of judgment has to be *serialized* — turned into words and transmitted — before any agent can act on it. The capsule brief is words. The redirect is words. The verdict, and the reason for it, is words. Manager mode did not delete the bottleneck; it moved the bottleneck into your chair. And in your chair, the transmission runs at typing speed — 40 to 60 words a minute for most engineers — while the same judgment spoken aloud moves at 150 to 200. The fleet's ceiling is you. This chapter is about widening the pipe.

## The concept: the dispatcher, and why command is speech-shaped

The seat you occupy when the fleet runs has an old name: the **dispatcher**. Watch one work and the first thing you notice is what he does not do: he does not drive. His entire output is a stream of short, precise transmissions over a radio — assignments out, confirmations in, corrections when a driver drifts — and the network's throughput is bounded by how many of those he can issue and verify in an hour. That is your job description now: an operator's output is orders and verdicts, and every one of them is speech-shaped — a paragraph of prose, not a page of code.

The numbers are unusually clean. A 136-million-keystroke study puts average typing at 52 words per minute; Ruan and colleagues measured speech at 153 versus 52 for the keyboard — 2.93 times faster, with a lower corrected error rate; and Foley, Casiez, and Vogel closed the obvious objection by testing *composition* — inventing the message on the spot, which is what briefing a lane is — and the roughly three-times ratio held (116.5 spoken versus 35.1 typed). One honest boundary, stated as bluntly as the gain: the multiple applies to *instruction throughput* — the outbound half of the loop — and to nothing else. Amdahl's Law caps the rest: if briefing is 30% of your orchestration hour, voice makes the whole hour about 1.25 times faster, not three. No microphone reads a diff for you, and the review pipe stays exactly as wide as your discipline.

## The framework: The Dispatch Loop

The dispatcher's cycle applied to a fleet of agents — a commander's output is orders and verdicts, and both are speech-shaped. Four steps, repeated as long as the lanes run.

1. **Brief by voice.** Compose the capsule brief — goal, files owned, constraints, done check — and speak it instead of typing it. A 200-word capsule drops from four minutes to ninety seconds. Speak the *intent* and let the agent resolve exact paths — identifiers are where dictation stumbles and what an agent with the repo in front of it does not need you to spell.
2. **Dispatch the lane.** Send the brief and detach — chapter 4's discipline, untouched. One temptation worth naming: because briefing is now cheap, you will be tempted to dispatch lanes you have not thought through. Cheap to transmit is not the same as ready to run.
3. **Review the return against its check.** Read the diff and run the check yourself — claims, never confidence. This half is deliberately not accelerated: if you dictate faster than you can honestly review, you have raised your intake and called it throughput. The gate decides what merges. The gate is deaf.
4. **Redirect or merge.** Issue the verdict aloud — a redirect cheap enough now to fire at the first wrong paragraph instead of the twentieth — and log it, one line, timestamped. Then the loop closes and the next brief begins.

Measure the loop in **dispatches per hour** — briefs, redirects, and verdicts issued per hour of orchestration. It counts the input only you can produce, and it cannot be inflated by the fleet's own volume.

On tools, in the order you should try them: your operating system ships a free dictation mode — start there tonight. Beyond the built-in: Wispr Flow is a polished cross-application dictation layer; superwhisper runs on-device, so no audio leaves your machine; Talon Voice goes furthest, full hands-free control. Keebye — my own product — is voice dictation built for parallel agent workstreams, one voice feeding several lanes; that sentence is the whole pitch, and every step of the Loop runs identically on the free built-in.

One straight sentence on privacy: dictation is audio, and audio goes wherever your tool sends it — confirm whether yours processes speech on-device or in the cloud *before* you speak anything sensitive, because a spoken brief is disclosed the moment it leaves your machine.

## Go deeper

- [Ruan et al. — *Comparing Speech and Keyboard Text Entry* (speech at 153 WPM vs. 52 typed — the 2.93x measurement in the epigraph)](https://doi.org/10.1145/3161187)
- [Dhakal et al. — *Observations on Typing from 136 Million Keystrokes* (the honest keyboard baseline: 52 WPM average across 168,000 people)](https://doi.org/10.1145/3173574.3174220)
- [Foley, Casiez & Vogel — *Comparing Smartphone Speech Recognition and Touchscreen Typing for Composition and Transcription* (the ratio holds even when you invent the message as you go)](https://doi.org/10.1145/3313831.3376861)

---

> **This is the free edition.** The full chapter — the rigor pass, the complete stories, and the ship-this exercise — is in the book. [Reserve the $39.99 launch price](https://aiescu.com/book?utm_source=github&utm_medium=10-command-the-fleet-by-voice) — free to reserve, nothing charged until it ships.

---

Prev: [← Chapter 9](09-show-up-sharp.md) · Next: [Chapter 11 — The Glass Workshop →](11-the-glass-workshop.md)
