# The Glass Workshop: How to Build a Public Proof Site That Turns Forwarded Links Into Inbound Clients

> "[T]hose to whom we are weakly tied are more likely to move in circles different from our own and will thus have access to information different from that which we receive." — Mark Granovetter, *The Strength of Weak Ties* (1973)

The weekend after his second client's delivery week, Adrian built the least impressive thing in this book: one web page. It took him an evening. Down the left side, the proof he already owned — the live docs demo from chapter 5, still answering questions at its URL; the recall number his eval gate holds it to; the delivery date that held because the gate did its one job. Down the right, one offer — a fixed-scope docs assistant, one per month, twenty minutes to walk through it — and one contact route. At the bottom, three short entries under a heading he almost deleted twice: *what broke this week, and the fix.* He nearly did not deploy it; every instinct from the old game said the repo was the honest artifact and this was decoration. He shipped it anyway, mostly because it was one evening and the domain cost eleven dollars.

For three weeks the page did, as far as he could tell, nothing. Then, on a Tuesday, an email from a founder he had never spoken to, two sentences long: *Someone forwarded me the docs assistant you built — we have the same maze, worse. Is this something you take on?* He could trace every hop of the path, because it was short: the founder from chapter 7 had sent his demo link to her CTO; the CTO, months later, forwarded it to a friend drowning in her own documentation; the friend clicked the demo, asked it two questions, and then did the thing strangers do before they email a stranger about money — looked for the person behind it. The demo's footer gave her exactly one link, and at the end of it was the page: the demo running, the numbers defended, the log admitting what had broken the week before. She read it for four minutes and wrote the email. Client three did not come from an application. Client three went looking for him, and found the workshop with the lights on.

## The false belief: "A repo is enough — a website is vanity"

Say it out loud, because it is the engineer's version of modesty and it sounds unimpeachable: *the code is public, the demo is live — a website about myself is vanity.* The belief fails on one word: *find*. A repository is proof for people who have already found you. Founders do not browse GitHub looking for engineers, and the CTO on her third forwarded link of the day is not going to reconstruct your competence from a commit history. Your proof spends most of its life being looked at by people you never sent it to, in contexts you did not choose, with none of your explanations attached — and the thing that survives that trip is a single page that answers, in one screen, what you built, what it measures, and what to do next. The belief calls that page vanity. The forwarded stranger calls it the only thing she read.

## The concept: forwardability — proof that travels without you

**Forwardability** is the degree to which your proof survives being passed to a stranger without you in the room. Proof that is forwardable carries its own context: what this is, why it is credible, what to do about it, all inside the link. And forwarding is not a networking bromide — it is the measured channel opportunity actually uses. Granovetter's 1973 study found that among people who found jobs through a personal contact, only 16.7% saw that contact often; the break disproportionately came from acquaintances at the edge of the network. In 2022 that finding got the causal test almost no career advice ever gets: randomized experiments in LinkedIn's "People You May Know" system, spanning twenty million users and two billion new ties, showed that adding weak ties *causes* more job transmission than adding strong ones. A weak tie cannot carry your competence in their head — by definition they barely know you. What a weak tie can carry is a *link*, and forwardability is the load your proof must bear to travel that channel.

One honest boundary, because the evidence does not support more: I will not tell you a proof site brings clients to your door — nobody can schedule a forward, and Adrian's page sat silent for three weeks. What you control is whether the link that arrives is ready to be read by a stranger. You are not buying inbound; you are buying conversion on a channel that fires rarely, without warning, and only ever once per stranger.

## The framework: The Glass Workshop

Shops with glass fronts sell what people watch being made — not because the work is better, but because a stranger on the sidewalk can verify it without knocking. **The Glass Workshop** is that shop, built as one web page. Five parts, each earning its place on the single screen a forwarded stranger will actually read.

1. **The live demo.** Your chapter-5 system, embedded or one click away, on and answering. It goes first because no claim substitutes for it: a stranger who types a question and watches a grounded answer come back has verified you in fifteen seconds. A dead demo is worse than none — so the demo you show is the one your chapter-6 gate keeps honest.
2. **The receipts.** Two or three numbers you can defend, each pinned to its case: the retrieval accuracy your eval holds, the delivery date that held. Numbers, not adjectives — every receipt must survive the follow-up "measured how?" If it cannot, it does not go on the glass.
3. **The open ledger.** The repos, linked — the chapter-5 system with its honest README, the skill library, the eval harness. This converts the skeptical engineer in the forwarding chain, and it costs you nothing, because you already built all of it.
4. **The one offer.** A single, specific next step: the fixed-scope build you take on, the twenty-minute walkthrough. One, because a stranger given three options defers and a stranger given one either takes it or replies with what they actually need — both of which are conversations.
5. **The log.** A short, dated record of what broke and what the fix was. Three entries is enough to start. It is the strongest trust signal on the page precisely because it is the one no pretender writes — only someone operating a real system has this week's honest breakage to report. A current log says the machine is still on.

The disclosure, in full, because I use my own site as the worked example: aiescu.com is my site and my business — the demo on it is the one this book has been walking through, and yes, the paid programs live there too; that one sentence is the whole pitch you'll get. The framework owes nothing to any vendor: GitHub Pages or any static host serves a Glass Workshop free or for pocket change, and the pattern's best-known practitioner may be Simon Willison, whose public TIL site — hundreds of dated entries, every one backed by a public repo — has kept the machine demonstrably on for years. A domain you own is the only purchase this chapter endorses: proof that lives on someone else's subdomain is proof with a landlord.

## Go deeper

- [Mark Granovetter — *The Strength of Weak Ties* (the foundational study: opportunity arrives along acquaintances, not close friends)](https://doi.org/10.1086/225469)
- [Rajkumar et al. — *A Causal Test of the Strength of Weak Ties* (Science, 2022: twenty million users, randomized — weak ties cause job transmission)](https://doi.org/10.1126/science.abl4476)
- [Simon Willison — *TIL* (a long-running glass workshop in the wild: current work visible, notes honest, sources open)](https://til.simonwillison.net/)

---

> **This is the free edition.** The full chapter — the rigor pass, the complete stories, and the ship-this exercise — is in the book. [Reserve the $39.99 launch price](https://aiescu.com/book?utm_source=github&utm_medium=11-the-glass-workshop) — free to reserve, nothing charged until it ships.

---

Prev: [← Chapter 10](10-command-the-fleet-by-voice.md) · Next: [Chapter 12 — The Daily Driver →](12-the-daily-driver.md)
