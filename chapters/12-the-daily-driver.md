# The Daily Driver: The Settled Five-Layer Stack for Shipping AI as One Person — Stop Shopping, Start Driving

> "The answer is less. Do less than your competitors to beat them." — from 37signals, *Getting Real*

The night Adrian's third build begins, choosing his tools takes eleven minutes. He opens a one-page file he keeps next to the prospect sheet — five lines, one default per layer, dated, amended twice — reads it, carves out the lanes, and starts briefing. It was not always eleven minutes. Between the first contract and the second there was a night he has never told anyone about: forty-one browser tabs, every one open to the same decision — which vector database to standardize on. A thread arguing pgvector was a toy. A thread arguing the thread calling pgvector a toy was a paid shill. A comparison matrix with nine columns and no verdict. He had a delivered contract behind him, a deployed system, an eval gate that had caught a real regression — and he sat frozen in front of a tool choice for three evenings, because the paralysis had a story underneath it he had never said out loud: *everyone shipping real AI already knows the stack, and I have to reverse-engineer the whole thing, alone, before I'm allowed to build the next one.*

What ended it was not a verdict hiding in tab thirty-nine. It was the night he closed all forty-one and wrote the one-page file instead — one default per layer, chosen from what he had already shipped with, not from what the forums feared — and treated the page like any other standard he had written: versioned, obeyed, amended only on evidence. You have your own version of the forty-one tabs. Here is the question this last chapter answers: what if the reason you keep re-deciding your tools is not that the decision is hard, but that nobody handed you the boring, finished list — so you assumed there wasn't one?

## The false belief: "I have to figure out the stack alone"

The forty-one tabs have a sentence running underneath them: *I have to figure out the stack alone.* Every layer is a decision, every decision has a loud contrarian, and until I've read all of them I'm not qualified to commit. The belief is seductive for the same reason the certification reflex was: it converts fear into a to-do list. Researching tools *feels* like work. But it is procrastination with a spreadsheet open, and it has a specific tell — it never ends. The stack is not a secret guarded by people further along than you. It is a short list of layers, each with one good-enough default, that any working AI shop would tell you over coffee in ten minutes. You do not assemble the stack by researching it to completion. You assemble it by using it, and you use it by picking a default and committing.

## The concept: the stack, and the daily driver as a settled default set

A **stack** is the ordered set of layers a workflow runs on — historically the LAMP stack, the four-word answer a 2004 web developer could give to "what do you build on?" without a nine-column matrix. Its power was social: it let a whole industry stop re-litigating the base layers. A **daily driver** is the car you actually drive every day — reliable, unglamorous, boring on purpose — as opposed to the project car you theorize about and rarely start. A daily-driver stack applies that to tools: one default per layer, committed, so your attention goes to shipping instead of shopping. Optimization comes later, from friction you actually hit in production — never from a forum thread about friction someone else hit. The practitioners closest to the frontier agree: Anthropic's own guidance on building agents reports that the most successful implementations use simple, composable patterns, adding complexity only when it demonstrably improves outcomes.

## The framework: The Daily Driver Stack

Five layers, one default each — and an honest weighting: the build and ship layers are the load-bearing ones; layers three through five are the tools of the era covered in full by chapters 8-10, so each gets one line and a pointer home. Where a default is a tool I build myself, the list says so plainly, because a recommendation you can't weigh is just an advertisement.

1. **The build layer — an agentic coding environment.** Claude Code as the core: read the codebase, run commands, drive the parallel agents of chapters 2 and 4 behind the verifiable checks of chapter 6. Not mine to sell; pick the environment you'll actually live in, and commit.
2. **The ship layer — repo, deploy, eval-CI.** Public repo, a one-command deploy target, and the chapter-6 eval gate wired into CI so no regression reaches production. Proof and its defense, automated. Not mine either; entirely yours to own.
3. **The old-game layer — the paycheck bridge (see chapter 8).** An interview-prep copilot for the bridge you run on purpose. The default is **GeekBye** (my own product, disclosed in chapter 8) — and chapter 8 carries this layer in full: the Rehearsal Loop, the non-owned alternatives, and the ethics of the room.
4. **The presentation layer — show up sharp (see chapter 9).** A meeting copilot, plus the resume regenerated from your ledger. The default is **Pavleur** (also my own product, chapter 9) — with the Three-Artifact Call, the consent rule, and the alternatives at equal footing in its home chapter.
5. **The fleet layer — command more than one agent (see chapter 10).** Voice dictation for the days you drive several lanes at once. The default is **Keebye** (mine as well, chapter 10) — with the Dispatch Loop, the honest limits of the three-times number, and the privacy caveat in its home chapter.

Three of the five defaults are mine, each disclosed in its home chapter with the non-owned alternatives beside it at equal size — because the honest version of a recommendation is the one that survives you knowing who profits from it. One line governs all five layers: no tool writes the substance — it frees your attention to supply it. Stand the two core layers up first, and the forty-one tabs close themselves. The engineer who ships is the one who stopped deciding and started driving.

## The ladder, reprised: where you are standing

The introduction handed you the book's map — **The Operator's Ladder**, five stages: **Decide**, **Leverage**, **Prove**, **Sell**, **Compound** — every rung something you run and can verify, never a title someone else grants. By this chapter you have walked all five: the identity decision signed (chapters 0-1), a fleet briefed and reviewed in parallel lanes (chapters 2-4, now at the speed of speech per chapter 10), a deployed system behind a glass front (chapters 5-6 and 11), calls that close on artifacts (chapters 7 and 9), and both games running at once on a settled stack (chapters 8-12). Adrian's inventory fits in one breath, and every item on it can be checked: one engineer, three clients, a fleet, a gate, standards he wrote himself, a bridge paycheck kept on purpose, a ladder he built. He is not rich. He is early — which he now knows is a position, not a verdict.

## Go deeper

- [Anthropic — *Building Effective AI Agents* (the case for simple, composable patterns over complex frameworks)](https://www.anthropic.com/research/building-effective-agents)
- [Adam Wiggins — *The Twelve-Factor App* (the enduring methodology for deployable, maintainable services — the ship layer, done right)](https://12factor.net/)
- [Dexter Horthy — *12-Factor Agents* (the twelve-factor discipline extended to LLM systems: own your prompts, your context window, your control flow)](https://github.com/humanlayer/12-factor-agents)

---

> **This is the free edition.** The full chapter — the rigor pass, the complete stories, and the ship-this exercise — is in the book. [Reserve the $39.99 launch price](https://aiescu.com/book?utm_source=github&utm_medium=12-the-daily-driver) — free to reserve, nothing charged until it ships.

---

Prev: [← Chapter 11](11-the-glass-workshop.md) · Back to: [README / Table of Contents ↑](../README.md)
