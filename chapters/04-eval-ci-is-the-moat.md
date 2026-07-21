# Agents Without Evals Are Demos: Why Eval-CI Is the Moat Between a Cool Prototype and a Product People Pay For

> "Unsuccessful products almost always share a common root cause: a failure to create robust evaluation systems." — from Hamel Husain, *Your AI Product Needs Evals*

The demo goes perfectly. It always does — you tested it on the same five inputs a dozen times. The prospect nods, asks one question you didn't rehearse, and the model confidently returns something wrong. Not obviously wrong. Plausibly, expensively wrong. The room cools. What you're feeling in that moment is the exact distance between a demo and a product, and it's measured in one thing you didn't build: a way to know, automatically, whether the thing still works when the inputs change.

Adrian shipped the RAG demo from the last chapter and it got him a call. The call nearly ended it, because a demo that works on your five favorite inputs is a magic trick, and buyers have seen magic tricks. What survives contact with a real user is a system that *proves* it still works — on inputs you didn't cherry-pick — every time you change the code. That proof is the moat. It's also the thing almost nobody building AI demos has bothered to build, which is precisely why it's worth money.

The gap between "played with an LLM" and "ships production AI" is not model access. Everyone has model access. It's evals.

## The false belief: "My demo is enough"

The belief confuses *it worked once* with *it works*. A demo is an existence proof for a happy path. A product is a guarantee under variation — and variation is exactly what a live user brings. Without evals, every deploy is a coin flip you can't see the result of until a customer does. "Enough" is the word that keeps prototypes from ever becoming products.

## The concept: evals, and eval-CI as regression testing for probabilistic systems

An **eval** is a test for a system whose output isn't deterministic. Instead of asserting `output == expected`, you score a model's response against criteria — correctness, grounding, format — across a set of representative inputs, and track the aggregate. **Eval-CI** is the discipline of running that eval automatically in continuous integration, so a pull request that drops quality below a threshold *cannot merge*. It's regression testing adapted for probability: you can't assert one exact string, so you gate on a measured rate. The etymology is honest — you *evaluate* rather than *assert*, because the system evaluates rather than computes.

## The framework: The Eval Gate

A moat isn't a feeling; it's a gate that blocks bad changes automatically. **The Eval Gate** is four steps to put one in front of a real change:

1. **Write the eval set.** Fifteen to thirty representative inputs with a way to score each output — an assertion, a rubric, or an LLM-as-judge with a spot-checked prompt. Small and real beats large and aspirational.
2. **Set a threshold.** Decide the passing rate the system must hold — say, 90% grounded and correct. Name the number before you're tempted to move it.
3. **Wire it into CI.** The eval runs on every pull request. Below threshold, the check goes red and the merge is blocked. The gate, not your goodwill, enforces quality.
4. **Gate a real PR.** Make an actual change to your chapter-3 project, watch the eval catch a regression (or pass honestly), and merge only through the green gate. Now you have a demo that defends itself.

Ship the eval, and you've built the one thing buyers can't get from a prototype: a reason to trust it tomorrow.

## Go deeper

- [Hamel Husain — *Your AI Product Needs Evals* (the canonical practitioner guide to building domain-specific evals)](https://hamel.dev/blog/posts/evals/)
- [OpenAI Evals — the open-source framework and registry for evaluating LLM systems](https://github.com/openai/evals)
- [Martin Fowler — *Engineering Practices for LLM Application Development* (testing, CI, and responsible practice for production LLM apps)](https://martinfowler.com/articles/engineering-practices-llm.html)

---

> **This is the free edition.** The full chapter — the rigor pass, the complete stories, and the ship-this exercise — is in the book. [Reserve the $39.99 launch price](https://aiescu.com/book?utm_source=github&utm_medium=04-eval-ci-is-the-moat) — free to reserve, nothing charged until it ships.

---

Prev: [← Chapter 3](03-proof-beats-credentials.md) · Next: [Chapter 5 — Finding Clients When Nobody's Hiring →](05-finding-clients.md)
