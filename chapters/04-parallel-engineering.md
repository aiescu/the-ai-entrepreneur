# Parallel Engineering: How to Clone Yourself Across Isolated Agent Lanes When You Can Only Be in One Place at a Time

> "Adding manpower to a late software project makes it later." — Frederick P. Brooks Jr., *The Mythical Man-Month* (1975)

It's nine on a Tuesday and you have two jobs in front of you, both yours, both due. One is a migration: move a service off the deprecated payments client, mechanical and tedious and touching a dozen files. The other is a feature you actually want to build, a small export endpoint with its own tests. The greedy thought arrives on its own: why not run both at the same time, two agents, one evening, and go to bed with two things shipped? You tried exactly that last week — opened two agents in the same folder, gave them a job each, and came back to a working tree where both had edited the same config file, each convinced it was right, the diff a knot you spent an hour untangling.

So tonight you do the human thing, which is to pick. You are not slow and you are not disorganized. You are obeying a rule so deep you have never said it out loud — that you are one person, at one keyboard, and one person can only be in one place at a time. But the knot last week wasn't caused by the number of your hands. It was caused by two workers sharing one desk.

Here is the question this chapter exists to answer: what if the thing stopping you from running five jobs at once was never that you have one head, but that you kept making the workers share a room?

## The false belief: "I can only be in one place at a time"

Name the rule that ran under your whole evening, even if you've never put it in words: *I can only be in one place at a time.* One body, one keyboard, one train of thought that snaps the moment you split it. It feels less like a belief than a law of physics, because for your entire career it was one — the work happened where your hands were. The belief survived agents by mutating: *fine, an agent can type without me, but I still have to watch it.* Two agents need two sets of eyes you don't have, and you're back to one at a time. The hidden premise — the whole load-bearing wall — is that parallel work requires your *simultaneous presence*. Strip it out and the fear collapses, because you already know it's false: you don't hover over two database queries or two CI jobs. You launch them, they run without you, and you look when the results land. The reason you can't do that with two agents isn't a fact about your attention. It's a fact about how you set the work up.

## The concept: shared-nothing lanes, and why Brooks's Law spares the fleet

Human parallelism has a bad reputation for a reason. In 1975 Fred Brooks wrote down the law that carries his name: *adding manpower to a late software project makes it later.* The mechanism is arithmetic — every new person has to coordinate with everyone already on the task, and the number of those links grows with the headcount *squared*. Humans on a shared task are slow to parallelize because they *share state*: the same codebase, the same assumptions, the same half-finished decision one made this morning that the others have to be told about. Last week's knot was Brooks's Law in miniature at a headcount of two.

The move that changes everything is stolen from how large systems are built: **shared-nothing** architecture — machines that hold no memory or disk in common, so no two ever contend for the same resource. Parallelism stops being hard the instant the workers share nothing they both can change. The tool that gives you this is a **git worktree**: from one repository, git checks out more than one branch at a time, each into its own directory with its own working files, its own `HEAD`, its own index. An agent in one worktree cannot touch the config file an agent in the other is editing, because in its universe that edit doesn't exist yet. You haven't cloned your judgment — there's still only one of you, and that's the point. You've cloned your *hands*, into rooms that share no desk, and Brooks's Law has nothing to bite.

## The framework: The Clone Protocol

You don't get parallel leverage by opening more terminals. You get it by giving each clone a sealed room, a complete brief, and a gate it has to pass before its work counts. **The Clone Protocol** is five steps that make a lane safe to run while you're not watching:

1. **Isolate the lane.** Before any agent runs, give it a universe it can't escape: its own git worktree on its own branch, a disjoint set of files no other lane may touch. The test for whether work is ready to parallelize is exactly this — can you carve it into lanes with no overlapping files? If you can't, the work is coupled, and coupled work stays serial.
2. **Write the capsule brief.** The context you hand the agent is its entire world; it can't walk down the hall to ask. The brief must carry the goal, the files it owns, the constraints, and above all the *verifiable done condition* — the test that must pass, the build that must go green. If you can't write a crisp capsule, the work isn't ready to fan out.
3. **Dispatch and detach.** Launch the lane and take your hands off it. Hovering feels like diligence and is the opposite — a human flicking between lanes attends to each for under a minute before the next flick pulls him away. Run the lanes asynchronously and let the work notify you: a finished run, a green check, a pull request opened. The unit of your attention is the completed lane, not the keystroke.
4. **Verify adversarially.** When a lane reports success, review its *claims*, never its confidence. An agent narrates "all tests pass" in the same even tone whether it ran the tests or imagined them. Don't read the summary — read the diff, and run the check yourself against fresh output.
5. **Merge one lane at a time.** This is where parallel work becomes serial again, on purpose, because the merge is where your judgment lives and judgment doesn't fan out. Bring the lanes home one at a time through the same gate. If two lanes did touch overlapping ground, you pay the reconciliation once, in the open, with your eyes on it — not as a knot two agents tied while you were gone.

The fleet produces in parallel. You decide in sequence. You bookend the parallelism with judgment and let the middle run wide — which is exactly why you can run several at once: it never tried to clone the part of you that can't be cloned.

## Go deeper

- [Anthropic — *How we built our multi-agent research system* (a lead agent fanning work out to parallel subagents, and the honest limits of when it pays)](https://www.anthropic.com/engineering/multi-agent-research-system)
- [Git — *git-worktree* documentation (the official reference for checking out multiple branches into isolated working directories)](https://git-scm.com/docs/git-worktree)

---

> **This is the free edition.** The full chapter — the rigor pass, the complete stories, and the ship-this exercise — is in the book. [Reserve the $39.99 launch price](https://aiescu.com/book?utm_source=github&utm_medium=04-parallel-engineering) — free to reserve, nothing charged until it ships.

---

Prev: [← Chapter 3](03-the-ai-multiplier.md) · Next: [Chapter 5 — Proof Beats Credentials →](05-proof-beats-credentials.md)
