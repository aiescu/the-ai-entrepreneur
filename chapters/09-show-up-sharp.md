# Show Up Sharp: Meetings Are the New Interviews — Why the Same-Day Summary Closes Deals Good Work Alone Can't

> "A meeting is nothing less than the medium through which managerial work is performed." — Andy Grove, *High Output Management* (1983)

The reply came from row seven of Adrian's prospect sheet — three weeks late, long after he had written the row off. A logistics-software company whose head of support had posted, in a public thread, that her team was answering the same forty questions on rotation while the real tickets aged. He had built them a demo the way he built the first one: their public help center through his pipeline, his eval gate in front of it. Silence. Then, on a Tuesday: "Saw your demo. Can we talk Thursday?" This is not the first contract — it is a scoping call with a company three times the size, for three times the surface. Real stakes, in a room he has never been in.

So he prepares the way he now prepares for anything that matters: he builds an artifact. One page — their problem in their own words at the top, quoted from the thread; his receipts in the middle, the live demo and the one fact he can defend without notes (his first delivery held a 90% retrieval bar in CI from first commit to handoff); the one next step he will propose at the bottom. On the call he opens with one sentence — "I'd like to record this so the summary I send you tonight is accurate — is that all right?" — and keeps a running note of exactly one kind of thing: decisions. The CTO pushes — what happens when the model is wrong? — and Adrian, who has an eval gate instead of an adjective, answers with the number, and watches the arms unfold. The call ends warm at 8:52. Warm is not a deal. By 10:40, before he lets himself sleep, the summary is sent: what was agreed, who owns what, the pilot's scope, the open question, the proposed start date. Two days later the reply quotes his own summary back at him: "Per your summary — let's start with the pilot."

The work got him the call. The document he wrote after everyone hung up is what closed it. How many of the best meetings of your career evaporated — warm call, real interest, then nothing — because nobody wrote them down?

## The false belief: "If the work is good, the meeting doesn't matter"

For an engineer this barely feels like a belief — it feels like a principle. The demo speaks for itself; the code is the argument; meetings are the theater the incompetent hide behind. The belief quietly assumes the meeting is a *presentation* — a place where finished work is displayed and judged. It is not. A scoping call, a final-round interview, a pilot review — these are places where things get *decided*: scope, ownership, dates, money, whether there is a next step at all. And a decision, unlike a demo, has no deployed URL. It exists only in the memories of the people on the call, and memory starts losing state the moment the meeting ends. The work being good gets you into the room. What happens to the room's decisions afterward is a separate engineering problem, and deals die in that gap.

## The concept: a meeting has no persistence layer — so ship it one

In the old game, somebody else ran the process around the high-stakes conversation: the company scheduled the loop, collected the feedback, sent the follow-up. In the new game, you are the company — either you engineer the conversation, or nobody does. The numbers on the gap are old and replicated: Ebbinghaus's forgetting curve — reproduced in shape by Murre and Dros in 2015 — shows the steepest memory loss comes immediately after learning, with only a minority of detail surviving to the next day; every person on your call walks out with a private copy of what was agreed, and every copy corrupts on its own schedule. Meanwhile the interest decays too: the Harvard Business Review lead-response study of 1.25 million leads found firms that made contact within an hour were nearly seven times as likely to qualify the lead as those an hour slower — and the audit's sadder finding is that the average responder took 42 hours. A buyer's attention is a decaying asset priced by the hour, and the bar is on the floor. The same-day summary replaces four diverging recollections with one shared, checkable record, written in your words and subject to the other side's correction. **The same-day summary is the meeting's deployed URL.**

## The framework: The Three-Artifact Call

Every consequential call ships three documents — one before, one during, one after. It inherits its logic from how you already ship software: a spec before, instrumentation during, a deploy after.

1. **The prep brief (before).** One page, three blocks: their problem in their own words (quoted from wherever they said it), your receipts (the two or three numbers and links from your chapter-5 ledger that bear on *their* problem), and the one next step you will propose. A call converges on a next step only if someone walks in holding one. Thirty minutes, the night before.
2. **The decision notes (during).** A running note that captures exactly one class of thing: decisions — what was agreed, by whom, by when. Not a transcript, not color. The only copy of a decision worth trusting is the one made while the words are still in the air.
3. **The same-day summary (after).** Sent before you sleep, while you are the freshest witness either side has. Five blocks, plain text: what was decided, who owns what, the scope as you understood it, the open questions, the proposed next step with a date — closed with one line inviting correction. It freezes the record before the copies diverge, lands while the interest is still warm, and becomes the document both sides work from.

One straight sentence on consent, because the capture step touches law: many jurisdictions require *all-party* consent to record a conversation, so ask in one sentence at the top of every call, every time — and if the answer is no, take the notes by hand; the framework works exactly the same.

On tools, disclosed properly: Pavleur — also my own product — is an AI meeting copilot and resume builder, the presentation layer for both games. The alternatives deserve the same volume: Otter.ai, Fireflies.ai, and Granola all capture and summarize meetings well, and a plain document with three headings — Agreed, Owns, Next — costs nothing and satisfies every step above. The framework needs no vendor at all, and no tool writes the substance — it frees your attention to supply it.

## Go deeper

- [Murre & Dros — *Replication and Analysis of Ebbinghaus' Forgetting Curve* (the 2015 replication: steepest loss right after, a minority of detail left by day one)](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0120644)
- [Oldroyd, McElheran & Elkington — *The Short Life of Online Sales Leads* (HBR: contact within an hour is ~7x more likely to qualify the lead; the average seller takes 42 hours)](https://hbr.org/2011/03/the-short-life-of-online-sales-leads)

---

> **This is the free edition.** The full chapter — the rigor pass, the complete stories, and the ship-this exercise — is in the book. [Reserve the $39.99 launch price](https://aiescu.com/book?utm_source=github&utm_medium=09-show-up-sharp) — free to reserve, nothing charged until it ships.

---

Prev: [← Chapter 8](08-win-the-old-game.md) · Next: [Chapter 10 — Command the Fleet by Voice →](10-command-the-fleet-by-voice.md)
