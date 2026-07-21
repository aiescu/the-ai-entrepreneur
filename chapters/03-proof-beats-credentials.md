# Proof Beats Credentials: How to Get AI Experience When Every Job Requires AI Experience You Can't Get Without a Job

> "[We explore] models which combine pre-trained parametric and non-parametric memory for language generation." — from Patrick Lewis et al., *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks*

The posting wants two years of production LLM experience. You have zero, because two years ago production LLM experience didn't exist, and the only way the posting will let you get it is to already have it. It's a locked door with the key on the inside. Adrian read forty of these in a week and felt the specific despair of a catch-22: he couldn't get the job without the experience, and he couldn't get the experience without the job.

Then he stopped trying the door. Over one weekend he built a small thing — a retrieval-augmented question-answering demo over a public documentation set — deployed it to a URL anyone could click, and pushed the code to a public repo with a plain README. It wasn't impressive to a researcher. It was *decisive* to a hiring manager, because it answered the only question that posting was really asking: can this person ship AI, or just talk about it? He had converted a credential he couldn't get into a proof he could show.

That is the move. In a market that cannot yet interview for the skill, the person who *demonstrates* it walks past the line.

## The false belief: "I can't get AI experience without a job"

The belief treats "experience" as something only an employer can grant, like a stamp. But experience is just evidence you can do the thing — and evidence, you can manufacture on your own, this weekend, with public data and a deploy button. The job was never the only source of the proof. It was just the source you were trained to wait for.

## The concept: proof, and RAG as the smallest honest proof

**Retrieval-augmented generation** is a system that looks up relevant documents and feeds them to a language model so its answers are grounded in real sources instead of invented ones. The name is literal: you *augment* generation with *retrieval*. It matters here for a second reason beyond usefulness: it's the smallest project that touches the whole production stack — ingestion, embeddings, a vector store, a model call, a deployed interface, and a repo. Build one and you've demonstrably done, in miniature, the thing the postings are afraid no one can do.

## The framework: The Proof Ledger

Credentials are claims; proof is entries in a ledger anyone can audit. **The Proof Ledger** is five steps that turn a weekend into a portable credential:

1. **Pick a real corpus.** Public docs, a dataset, your own notes — something a stranger would believe you'd want to query.
2. **Ship the smallest RAG that works.** Ingest, embed, retrieve, generate. Resist scope creep; a working small thing beats an unfinished ambitious one.
3. **Deploy it to a URL.** A clickable demo, not a screenshot. The click is the proof; a screenshot is a claim.
4. **Open the repo with an honest README.** What it does, how it's built, what you'd fix next. The "what I'd fix" line signals judgment, which is the scarce part.
5. **Log the entry.** Add the live link and repo to a running ledger you can paste into any conversation. Each entry is experience you granted yourself.

A ledger with one honest entry outranks a resume with ten certifications, because one of them you can click.

## Go deeper

- [Lewis et al. — *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks* (the original RAG paper, arXiv 2005.11401)](https://arxiv.org/abs/2005.11401)
- [Anthropic — *Introducing Contextual Retrieval* (a practical technique for making the retrieval half actually work in production)](https://www.anthropic.com/news/contextual-retrieval)

---

> **This is the free edition.** The full chapter — the rigor pass, the complete stories, and the ship-this exercise — is in the book. [Reserve the $39.99 launch price](https://aiescu.com/book?utm_source=github&utm_medium=03-proof-beats-credentials) — free to reserve, nothing charged until it ships.

---

Prev: [← Chapter 2](02-the-new-game.md) · Next: [Chapter 4 — Agents Without Evals Are Demos →](04-eval-ci-is-the-moat.md)
