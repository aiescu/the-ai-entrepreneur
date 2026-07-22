# The AI Entrepreneur Glossary: 154 AI, Agent, and RAG Terms Explained With Real-Life Analogies

Every term here gets a plain definition and a comparison from ordinary life, drawn from *The AI Entrepreneur* — because a definition that cannot survive outside the documentation is not much use at the workbench. The big official glossaries document the model well and the system around the model badly; this one lives in that gap: evals, guardrails, prompt caching, agent lanes, prompt injection — the vocabulary between "here is an LLM" and "here is a shipped, monitored, cost-controlled product." No major glossary pairs every term with a real-life analogy; this one does, in the book's register of kitchens, workshops, warehouses, and dispatch towers. Terms the book coined are marked "(as *The AI Entrepreneur* uses it)," so you can tell industry vocabulary from a name this book uses to make a recurring practice visible.

## Contents

- [The Machine — models, tokens, context](#the-machine--models-tokens-context) (39 terms)
- [Finding the Right Page — retrieval and RAG](#finding-the-right-page--retrieval-and-rag) (14 terms)
- [Making It Reliable — evals, gates, drift](#making-it-reliable--evals-gates-drift) (19 terms)
- [The Work Style — commanding the fleet](#the-work-style--commanding-the-fleet) (42 terms)
- [Proof and Shipping — repos, CI, deploys, cost](#proof-and-shipping--repos-ci-deploys-cost) (20 terms)
- [Finding and Serving Clients](#finding-and-serving-clients) (9 terms)
- [Safety and Failure Modes](#safety-and-failure-modes) (11 terms)

---

## The Machine — models, tokens, context

### AGI (artificial general intelligence)

Hypothetical AI with broad, human-level competence across domains, as opposed to today's task-shaped systems. The definition is contested; treat every confident timeline with suspicion.

*Real-life:* The "someday fully-autonomous car" of AI: permanently a few years away in keynotes, and not the vehicle you are driving today.

### AI (artificial intelligence)

Software that does tasks we normally associate with human judgment: understanding language, recognizing patterns, deciding.

*Real-life:* An umbrella word like "transportation": it covers everything from a scooter to a freight train, so the word alone tells you almost nothing about what is underneath it.

### Chain of thought

Prompting (or training) a model to write out its reasoning steps before the answer, which measurably improves accuracy on hard problems.

*Real-life:* Showing your work in math class: the requirement to write the steps catches the error before the wrong answer gets circled.

### Compaction

The harness summarizing older conversation history to free context space, keeping a long session going at the cost of detail.

*Real-life:* Rewriting a long meeting's minutes into a summary mid-meeting so the table stays usable: the meeting continues; the detail is gone.

### Context engineering

Deliberately choosing the smallest set of high-signal tokens the model sees — facts, examples, constraints — instead of stuffing the window. The discipline replacing "prompt engineering."

*Real-life:* A chef's mise en place: only what the dish needs, prepped and within reach; everything else stays in the pantry.

In the book: [chapter 12](chapters/12-the-daily-driver.md)

### Context rot / attention budget

The measured finding that as the context window fills, the model gets worse at recalling what is in it; every token spends down an attention budget.

*Real-life:* A whiteboard so full that the one number you need is technically on it and practically lost.

In the book: [chapter 12](chapters/12-the-daily-driver.md)

### Context window

The fixed amount of text (in tokens) a model can see in one request — instructions, documents, history, and its own answer all share it. Outside the window, nothing exists to the model. A cache, not a memory.

*Real-life:* A desk of fixed size: the model works only from what is on the desk right now, and putting one more thing on means something else hangs off the edge.

In the book: [chapter 2](chapters/02-the-new-game.md)

### Deep learning / neural network

Machine learning built from many layers of simple connected units whose connection strengths are tuned during training; the substrate of modern AI.

*Real-life:* Layers of filters in a bucket brigade: each layer hands along a slightly more distilled version of the input.

### Dictation / speech-to-text (STT)

Software that turns spoken words into text; the book's use is briefing agents by voice at roughly three times typing speed.

*Real-life:* The dispatcher's radio: the same orders, transmitted at the speed of talk instead of the speed of a pen.

In the book: [chapter 2](chapters/02-the-new-game.md)

### Distillation

Training a small, cheap model to imitate a large one's outputs, keeping much of the quality at a fraction of the cost.

*Real-life:* The ML literature's own image: a teacher-student apprenticeship — the small model learns by imitating the big one's answers, keeping most of the skill at a fraction of the payroll.

### Few-shot / zero-shot

Getting a task done by showing the model a few worked examples in the prompt (few-shot) or none (zero-shot).

*Real-life:* Showing the new cleaner two rooms done to your standard versus just saying "clean like a hotel": the worked examples beat the adjective.

### Fine-tuning

Further training a model on your own examples so a behavior or format is baked into its weights instead of supplied in the prompt each time. The practitioner rule of thumb: RAG for facts and freshness, fine-tuning for form and behavior.

*Real-life:* Sending an experienced hire through your company bootcamp: afterward the habits are theirs, no briefing needed — but retraining is the only way to change the habits.

### Foundation model

A big general-purpose model trained once on broad data, then adapted to many downstream tasks instead of building one model per task.

*Real-life:* A sourdough mother: cultured once at great effort, then split and adapted into every loaf the bakery sells.

### Frontier model

The current most-capable class of models from the big labs — and the most expensive per call. The book's routing law exists because most calls do not need one.

*Real-life:* The flagship trim at the dealership: genuinely better, priced accordingly, and the wrong choice for the school run.

In the book: [chapter 3](chapters/03-the-ai-multiplier.md)

### Generative AI

AI that creates new content — text, images, code, audio — rather than only classifying or ranking what already exists.

*Real-life:* The difference between a wine critic and a winemaker: one scores what exists; the other produces something new every run.

### Inference

Running a trained model to get answers, as opposed to training it. "Inference cost" is how the industry names the metered, per-call side of AI.

*Real-life:* Driving the car versus building it at the factory: inference is every trip you take after the car exists.

### Jagged frontier / jagged intelligence

Models are superhuman at some tasks and fail at trivially easy neighbors, with no smooth boundary — you cannot infer competence from adjacent competence.

*Real-life:* Ethan Mollick's image: an invisible, jagged wall between what the model does brilliantly and what it flubs. The practical rule: test the task, not the neighbor.

### Knowledge cutoff

The date a model's training data ends; it knows nothing after that unless you put it in the context.

*Real-life:* A returning astronaut: encyclopedic up to launch day, blank after it, and too fluent for you to notice the gap unless you ask about last week.

### Latency

How long the user waits between asking and getting the answer; caching and routing are the book's two levers on it.

*Real-life:* The pause at the drive-through speaker: nobody praises a short one; everybody leaves over a long one.

In the book: [chapter 12](chapters/12-the-daily-driver.md)

### LLM (large language model)

A program trained on enormous amounts of text to predict what comes next, which turns out to be enough to draft code, answer questions, and follow instructions. It produces fluent language; it does not know your business until you show it.

*Real-life:* A new hire who has read everything ever published but nothing about your company: articulate from minute one, useful only once you brief them.

In the book: [chapter 5](chapters/05-proof-beats-credentials.md)

### Machine learning

The branch of AI where systems get good at a task by learning patterns from examples instead of following hand-written rules.

*Real-life:* Training a sniffer dog: nobody writes rules for what contraband smells like; you reward correct finds until the nose generalizes.

### Model

The trained artifact itself: the specific, named, versioned thing you call — and, in this book's framing, a supplied part, not the product.

*Real-life:* The engine under the hood: you did not forge it, you can swap it, and the manufacturer can discontinue your exact engine on their schedule.

In the book: [chapter 0](chapters/00-introduction.md)

### Multimodal model

A model that works across more than one medium — reads images and text, answers in text, sometimes hears audio.

*Real-life:* A colleague who can read the report, look at the chart, and listen to the voicemail — instead of three specialists who each handle one.

### On-device vs cloud

Whether the AI processing happens on your own machine or on a provider's servers. On-device means the data never leaves; cloud means it does, under someone else's policy.

*Real-life:* Doing the shredding in your own office versus mailing the documents to a shredding service: same result, very different custody.

In the book: [chapter 10](chapters/10-command-the-fleet-by-voice.md)

### Open-weights model

A model whose trained weights you can download and run or fine-tune yourself (Llama, Mistral, Qwen), versus closed models reachable only through an API. Say "open weights," not "open source" — the training data and licenses are usually not open.

*Real-life:* Buying the espresso machine versus buying coffee at the counter: it sits in your kitchen and nobody can discontinue your cup — but maintenance is now your job.

### Parameters (and weights)

The millions-to-trillions of internal numbers a model learns during training; "the weights" colloquially means the model itself.

*Real-life:* The tension settings on a piano's strings: millions of tiny adjustments nobody set by hand, and together they are the instrument's sound.

### Prompt

The full text you send a model in one request: instructions, context, the question. The book's position: curating what goes in beats polishing how it is phrased.

*Real-life:* A work order handed to a contractor: everything they will act on is on that one page, so what you put on the page is the whole game.

In the book: [chapter 1](chapters/01-the-ladder-collapsed.md)

### Prompt engineering

The craft of phrasing and structuring prompts — roles, formats, worked examples — to get reliably better output. The book folds this craft into context engineering.

*Real-life:* Learning to write good work orders: same contractor, better outcome, because the page got clearer.

In the book: [chapter 1](chapters/01-the-ladder-collapsed.md)

### Quantization

Shrinking a model by storing its weights in lower-precision numbers, cutting memory and latency with modest quality loss.

*Real-life:* Shipping the statue in dense foam instead of marble: far lighter to move, nearly the same shape, slightly softer edges.

### Reasoning model

A model trained to spend extra "thinking" tokens before answering, trading latency and cost for accuracy on hard problems; you pay for the thinking.

*Real-life:* The chess player who takes the full clock: slower and pricier per move, and worth it only on positions that punish the quick move.

### RLHF (reinforcement learning from human feedback)

Training a model against human preference rankings so its outputs match what people actually find helpful and safe; the step that turned raw predictors into assistants.

*Real-life:* Training by applause: show the crowd two performances, keep whichever gets the louder clap, repeat until the act is shaped by the audience.

### Sampling controls (top-p, max tokens, stop sequences)

The API dials besides temperature: how much of the probability long tail is on the table (top-p) and how long the answer may run before it is cut (max tokens, stop sequences).

*Real-life:* House rules on the dice: how much of the long tail is even in play, and how many rolls the answer is allowed to take.

### Small language model (SLM)

A compact model (millions to a few billion parameters) that trades peak capability for speed, cost, and on-device deployment.

*Real-life:* A hatchback next to the flagship sedan: cheaper, quicker to park, and entirely sufficient for most errands.

### System prompt

Standing instructions set by the builder that shape the model's behavior across a whole conversation, separate from what the user types.

*Real-life:* The employee handbook versus the day's task list: read before the shift starts, in force all shift, and the customer never sees it.

### Temperature

The randomness dial on generation: low is predictable and near-repeatable, high gives unlikely words a real chance. It is a probability-sampling dial, not a talent dial — and temperature 0 is still not fully deterministic.

*Real-life:* How far down the ballot the model will pick: at low temperature it almost always takes the front-runner next word; at high temperature the long shots get a real chance.

### Test-time compute (extended thinking)

Buying accuracy at answer time — longer thinking, multiple attempts, search — instead of only via bigger models; vendors expose it as a thinking-budget dial.

*Real-life:* Paying the surveyor for extra hours on the tricky lot: same person, better answer, billed by the hour of thinking.

### Token

The unit models read and bill in: word fragments, roughly three-quarters of an English word each. Every price and limit in the field is quoted per token.

*Real-life:* The taximeter tick: you do not pay per trip or per sentence; you pay per tick, so long rides on the meter are what make bills surprising.

In the book: [chapter 3](chapters/03-the-ai-multiplier.md)

### Training (and training data)

The compute-heavy process of adjusting a model's parameters against examples until it performs; the examples' coverage and quality set a ceiling nothing later fully lifts. Pre-training is the massive first phase that yields capability but not helpfulness.

*Real-life:* An athlete's training log: capability is downstream of what the practice hours contained.

### Transformer

The neural-network architecture behind modern LLMs; its attention mechanism lets it weigh every part of the input against every other part at once.

*Real-life:* A reader who keeps every word of the page in peripheral vision at once, instead of moving a fingertip left to right.

---

## Finding the Right Page — retrieval and RAG

### Agentic RAG

Letting an agent decide when, what, and how to retrieve — and re-retrieve — instead of a fixed retrieve-then-answer pipeline.

*Real-life:* A researcher allowed to go back to the archive mid-draft: retrieval becomes a decision the agent makes, not a fixed first step.

### Chunking

Splitting documents into smaller passages before embedding, so retrieval can return a focused piece instead of a whole file. Chunk badly and the answer gets split across two pieces.

*Real-life:* Slicing the loaf so a slice fits the toaster: cut in the wrong place and the filling ends up half in one slice, half in the other.

In the book: [chapter 1](chapters/01-the-ladder-collapsed.md)

### Embedding

Turning text into a list of numbers — a coordinate — placed so passages with similar meaning land near each other, which is what makes search-by-meaning possible.

*Real-life:* A good librarian shelving books by subject rather than by the color of the spine, so "reset my password" and "recover a locked account" end up neighbors.

In the book: [chapter 4](chapters/04-parallel-engineering.md)

### Grounding / citations

An answer is grounded when it is supported by the retrieved sources rather than produced from the model's memory; citations make the support checkable, source by source.

*Real-life:* A journalist who cites the document instead of writing from recollection: the claim can be checked against the page it came from.

In the book: [chapter 5](chapters/05-proof-beats-credentials.md)

### Hallucination

Confident, fluent output that is factually wrong or unsupported by the sources — the failure mode grounding and evals exist to catch. It bites hardest in citations, package names, and API calls.

*Real-life:* A witness who never says "I don't remember" and instead fills the gap with plausible detail, under oath, in a steady voice.

In the book: [chapter 5](chapters/05-proof-beats-credentials.md)

### Hybrid search

Combining meaning-based retrieval with exact-keyword retrieval, because each misses things the other catches.

*Real-life:* Two guards at the door — one checks the guest list letter by letter, one recognizes faces; together they miss fewer.

### Ingestion

Loading and preparing documents before any question arrives: reading them in, chunking, embedding, storing.

*Real-life:* Receiving day at a warehouse: unbox, label, shelve. Nobody sees this work, and every later delivery depends on it being done right.

In the book: [chapter 5](chapters/05-proof-beats-credentials.md)

### Knowledge base

The curated document collection an assistant retrieves from: what it can look up, as opposed to what it memorized.

*Real-life:* The office reference shelf: the answerer is only as current as what got shelved.

### RAG (retrieval-augmented generation)

A system that looks up relevant passages from your documents first and hands them to the model, so the answer comes from your sources instead of the model's memory.

*Real-life:* An open-book exam: a student handed the book and told to find the page before answering, instead of sitting a closed-book exam on whatever stuck.

In the book: [chapter 0](chapters/00-introduction.md)

### Recall / retrieval accuracy

The share of questions for which the right passage actually came back from the retrieval step. The book's headline metric (0.93 held in CI), because nothing downstream can fix a wrong fetch.

*Real-life:* A warehouse's pick accuracy: of a hundred orders, how many times did the right item leave the shelf? The prettiest packaging cannot fix the wrong item in the box.

In the book: [chapter 1](chapters/01-the-ladder-collapsed.md)

### Reranking

A second, more careful pass that reorders the shortlist of retrieved passages by true relevance before the model reads them — a cheap accuracy win.

*Real-life:* The hiring manager personally re-reading the top twenty resumes the screener pulled: the screener is fast; the second reader is right.

In the book: [chapter 5](chapters/05-proof-beats-credentials.md)

### Retrieval

The lookup step: finding the handful of stored passages most relevant to the question. The book's repeated claim: this is where RAG systems actually fail, before the model ever runs.

*Real-life:* The librarian's fetch: if the wrong book comes back from the stacks, the smartest reader in the building writes a confident essay from the wrong book.

In the book: [chapter 0](chapters/00-introduction.md)

### Semantic search

Search by meaning rather than by exact words, implemented by comparing embeddings; the reason "locked account" finds the password-reset page.

*Real-life:* Asking the record-store clerk for "something like this" instead of an exact title: the match is by the feel of the music, not the spelling of the name.

### Vector database

A store built for embedding coordinates, optimized for "find the items nearest this one in meaning" at speed and scale (Pinecone, Qdrant, pgvector).

*Real-life:* A card catalog organized by topic-coordinates instead of the alphabet: you do not look up a title; you ask "what lives near this idea?"

In the book: [chapter 12](chapters/12-the-daily-driver.md)

---

## Making It Reliable — evals, gates, drift

### Benchmark

A standardized public test set (MMLU, SWE-bench) used to compare models: useful, gameable, and usually unlike your real workload.

*Real-life:* Standardized test scores on a resume: comparable across candidates, gameable, and not your job.

### Binary pass/fail eval

Grading each output pass or fail rather than on a 1-10 scale: scores feel rigorous but are noise; booleans force a clear definition of failure.

*Real-life:* A driving test is pass or fail; nobody parallel-parks 7.3 out of 10 — and that is what makes the test mean something.

### Cassette

A saved recording of the judge's verdicts, committed to the repo and replayed in CI — so the gate runs offline, free, and deterministic, and re-recording is a deliberate, reviewed act.

*Real-life:* A VCR tape: record the verdicts once, replay the tape forever; you only re-record when you mean to change the show.

In the book: [chapter 6](chapters/06-eval-ci-is-the-moat.md)

### Code-based eval / assertion

A deterministic check on output — regex, schema validation, "does the code run" — cheap and fast; use it before reaching for a judge.

*Real-life:* The go/no-go gauge on the bench: dumb, instant, and used before anyone calls in an inspector.

### Drift

Behavior changing under you while your own code sits still — typically because the provider updated the model. Direction is unpredictable; the only defense is measuring. The book also uses the word for an agent drifting off its brief.

*Real-life:* Your flour supplier quietly changed the grind: same recipe, same oven, different bread — and no memo.

In the book: [chapter 6](chapters/06-eval-ci-is-the-moat.md)

### Error analysis

Reading your system's real outputs one by one, labeling failures, and finding the patterns before building any automated metric. Hamel Husain's rule: 60-80 percent of eval time belongs here.

*Real-life:* The mechanic road-testing the car before reaching for the diagnostic computer: you ride with the actual failures until the pattern names itself.

### Eval

A test for a system whose output varies: instead of asserting one exact answer, you score many outputs against criteria and track the rate. A unit test with the determinism removed.

*Real-life:* A spelling test marks right or wrong; an eval grades an essay against a rubric. You cannot spelling-test an essay.

In the book: [chapter 0](chapters/00-introduction.md)

### Eval gate / gate (red-green) (as *The AI Entrepreneur* uses it)

A required check standing between a change and the main branch, empowered to say no. Green means the change may land; red means it may not, regardless of how confident the author sounds. Gating merges on checks is established platform practice; as this book uses it, an eval gate is that check with a passing threshold written down before tuning starts.

*Real-life:* The quality-control check that blocks the shipment: the pallet does not leave the dock because the inspector's light is red, and the inspector does not care how sure the foreman is.

In the book: [chapter 2](chapters/02-the-new-game.md)

### Eval-CI

Running the eval automatically on every proposed change, with the merge blocked if the score drops below a named threshold. Converts "I hope it still works" into a number a robot checks.

*Real-life:* A smoke detector wired to the door lock: while the air is clean the door opens; the instant it is not, the change cannot leave the building.

In the book: [chapter 0](chapters/00-introduction.md)

### Faithfulness

An eval score for whether the generated answer sticks to what the retrieved sources actually say.

*Real-life:* A translator graded on fidelity to the original text, not on how nice the translation sounds.

In the book: [chapter 6](chapters/06-eval-ci-is-the-moat.md)

### Fixture

A known-good reference output checked into the project, which new output is compared against in a test.

*Real-life:* The reference part bolted to the inspection bench: every new part off the line is held up against it.

In the book: [chapter 6](chapters/06-eval-ci-is-the-moat.md)

### Golden questions (industry: golden dataset / golden set)

A small, fixed, hand-checked set of representative questions with known-good answers, written before tuning, that the system is graded against on every change. Vendors call it a golden dataset or golden set; 20-50 cases is enough to catch regressions in CI.

*Real-life:* The answer key, written before the exam is handed out — so nobody can move the goalposts to wherever the class happened to land.

In the book: [chapter 5](chapters/05-proof-beats-credentials.md)

### Guardrails

Industry sense: validation and policy checks around a model's inputs, outputs, and actions, enforcing rules the model cannot be trusted to follow on its own. In this book the word also appears in its everyday sense: the cautions in each Ship This section.

*Real-life:* Bumpers on the bowling lane: the ball still does the rolling, but the gutter is no longer an option.

In the book: [chapter 5](chapters/05-proof-beats-credentials.md)

### LLM-as-judge

Using a second model to grade the first model's answers against a rubric, for cases where "correct" is too fuzzy for a string match. You spot-check the judge against human judgment before trusting it.

*Real-life:* A second teacher hired to grade essays to your rubric — and you re-mark a sample of their grading before you let their marks stand.

In the book: [chapter 6](chapters/06-eval-ci-is-the-moat.md)

### Model deprecation / retirement

A provider withdrawing the exact model version you depend on, on their schedule, sometimes with errors as the only notice.

*Real-life:* The manufacturer discontinuing your engine while the car is on the road: the recall notice arrives after the breakdown.

In the book: [chapter 0](chapters/00-introduction.md)

### Observability / trace

Instrumenting a running system so you can see what it is actually doing — especially the failures that report success. A trace is the full recorded path of one request (every prompt, tool call, and output): the raw material of error analysis.

*Real-life:* Gauges on the dashboard plus a smoke alarm: the engine light for the failure you can feel, the alarm for the one you cannot — the failure returning a cheerful HTTP 200.

In the book: [chapter 0](chapters/00-introduction.md)

### Open coding

Borrowed from qualitative research: annotating raw traces with free-form notes about what went wrong, then clustering the notes into failure categories.

*Real-life:* A field notebook before a filing system: write down what you see in plain words first; the categories come from the notes, not before them.

### Regression (eval) suite

The accumulated set of past-failure test cases you re-run on every change, so fixed bugs stay fixed.

*Real-life:* The scar-tissue checklist: every bug that ever bit you becomes a permanent question on the pre-flight list.

### Vibe check / vibes-based evaluation

Judging a model or change by poking at it informally instead of measuring — what evals exist to replace, though everyone still does it first.

*Real-life:* Kicking the tires: everyone does it first; nobody should buy the car on it.

---

## The Work Style — commanding the fleet

### Adversarial verification

Reviewing an agent's claims, never its confidence: read the diff, run the check yourself, and for hard calls set a second agent to refute the first.

*Real-life:* Trust the inspection, not the smile: the contractor's "all done" is checked by walking the site, and for the big jobs you hire a second inspector to argue with the first.

In the book: [chapter 4](chapters/04-parallel-engineering.md)

### Agent

A model run in a loop with access to tools: it takes an action, reads the result, decides the next action, and continues until done or stopped. It does tasks; it does not own the judgment.

*Real-life:* A capable temp worker with keys to the tool shed and one written task: they will work unsupervised and report back fluently — whether or not the work deserves the fluency.

In the book: [chapter 0](chapters/00-introduction.md)

### Agent lane / lane (as *The AI Entrepreneur* uses it)

One agent, one independent task, one disjoint set of files it owns. Lanes exist so parallel work cannot collide; the mechanism they ride on is worktree isolation.

*Real-life:* Airport landing lanes: the marked lanes are the entire reason the planes do not hit each other.

In the book: [chapter 0](chapters/00-introduction.md)

### Agent memory

Mechanisms for an agent to retain information across sessions or beyond the context window: notes, files, databases, summaries.

*Real-life:* A field agent's notebook: sessions end and the head empties, so anything worth keeping must be written where the next shift will look.

### Agentic

Built around agents: systems or tools where a model takes multi-step actions — reads files, runs commands, calls APIs — rather than answering one question. Vague in marketing, precise in engineering docs.

*Real-life:* The difference between a phrasebook and a fixer: one answers when asked; the other goes and gets it done.

In the book: [chapter 7](chapters/07-finding-clients.md)

### Agentic engineering

Professional, reviewed, tested development with coding agents — the discipline this book teaches, and the emerging neutral name for it.

*Real-life:* The difference between joyriding and holding a commercial license: same vehicle, plus rules, logs, and inspections.

### Agentic loop

The cycle an agent runs: gather context, act, verify, repeat. The unit of agent behavior.

*Real-life:* A cook tasting as they go — act, taste, adjust until the dish passes. The tasting is what makes it a loop rather than a recipe.

### AI engineer

The role between ML researcher and full-stack developer: builds products on top of foundation models through APIs, not by training models.

*Real-life:* A master builder who buys steel rather than smelting it: the craft moved from making the material to making the building.

### Autonomy slider

The design idea that products should let users dial an agent's independence up gradually rather than shipping full autonomy.

*Real-life:* Andrej Karpathy's image: "Iron Man suits, not Iron Man robots" — augmentation with a dial, not a replacement with a will of its own.

### Background agent / asynchronous coding agent

An agent you fire off to work unattended — it runs remotely or in the background and comes back with a diff or PR instead of chatting with you.

*Real-life:* Dropping the suit at the tailor: you leave, it works, you come back to a finished alteration — not a conversation.

### Capsule brief (as *The AI Entrepreneur* uses it)

The complete, self-contained instruction an agent gets: goal, files it owns, constraints, and the verifiable done condition. The agent knows nothing you did not put in the capsule.

*Real-life:* The note you leave a housesitter: everything they need on one page, because they cannot walk down the hall to ask — and if you cannot write the note, the errand was not ready to hand off.

In the book: [chapter 4](chapters/04-parallel-engineering.md)

### Clone Protocol (as *The AI Entrepreneur* uses it)

The book's five-step discipline for parallel work: isolate the lane, write the capsule brief, dispatch and detach, verify adversarially, then merge deliberately. It gives each lane an identical isolated environment, disjoint file ownership, and no shared mutable state while it runs.

*Real-life:* Photocopying the workshop, not the worker: many identical rooms, one set of blueprints on file, and never two hands on the same part.

In the book: [chapter 4](chapters/04-parallel-engineering.md)

### Computer use / browser use

Letting an agent drive a real screen — looking, clicking, typing — to automate software that has no API.

*Real-life:* Teaching the assistant to use the same mouse and screen as you instead of giving it a service entrance: slower, but it can go anywhere you can.

### Daily Driver Stack (as *The AI Entrepreneur* uses it)

The book's settled stack: five layers with one default each — build, ship, old game, presentation, and fleet. The small set of tools the operator actually uses every day, chosen for reliability under load over novelty.

*Real-life:* The daily driver in the garage: not the fastest car you own — the one that starts every morning.

In the book: [chapter 12](chapters/12-the-daily-driver.md)

### Dispatch / dispatches-per-hour (as *The AI Entrepreneur* uses it)

Dispatch is sending a briefed lane off to run without you. Dispatches-per-hour is the operator's unit of output: briefs, redirects, and verdicts issued per hour, not lines typed. Separate from the unrelated Claude Code "Dispatch" product feature, which routes phone-initiated tasks.

*Real-life:* The railway dispatcher, measured in transmissions, not miles driven: he does not drive one train.

In the book: [chapter 4](chapters/04-parallel-engineering.md)

### Dispatch Loop (as *The AI Entrepreneur* uses it)

The operator's recurring circuit: brief, dispatch, verify, merge or redirect — run across all lanes, all session.

*Real-life:* The control tower's sweep: the same circuit of the board, every few minutes, all shift.

In the book: [chapter 10](chapters/10-command-the-fleet-by-voice.md)

### Fleet (as *The AI Entrepreneur* uses it)

In the broader industry sense, simply several agents working together in parallel. As this book uses it, a fleet is a managed operating unit: agents working in parallel under one operator whose job is briefing, redirecting, and deciding what merges — not typing.

*Real-life:* The team you brief: several independent craft moving at once under one commander who does not row, and decides which boats reach port.

In the book: [chapter 0](chapters/00-introduction.md)

### Harness

In the book's test-rig sense: the scaffolding that holds a system still so you can run and measure it. In the industry agent sense: the software wrapped around a model that gives it tools, context management, permissions, and the loop — Claude Code is the harness; Claude is the model inside it.

*Real-life:* The engine test rig: the frame that holds the engine on the bench so you can run it hard before it ever goes in a car.

In the book: [chapter 3](chapters/03-the-ai-multiplier.md)

### Hook

A user-defined handler that fires deterministically at fixed points in the agent's lifecycle — before a tool runs, after an edit — automation the model cannot forget or skip.

*Real-life:* A tripwire on the workshop door: it fires every time, because it is wired to the door, not to anyone's memory.

### Human-in-the-loop

Designing the system so a person reviews or approves key steps at defined checkpoints instead of granting full autonomy.

*Real-life:* The pharmacist's counter-check on the prescription: the system drafts; a person signs.

### Manager mode / player-coach

The book's name for the operator's two stances: running lanes hands-off (manager mode) versus writing the tricky core yourself — and the rare skill of reading which day it is.

*Real-life:* A playing coach on a small team: some days you set the lineup from the bench; some days the fastest way to explain the play is to run it once yourself.

In the book: [chapter 2](chapters/02-the-new-game.md)

### Memory file (CLAUDE.md / AGENTS.md)

A markdown file of standing instructions the harness loads at every session start: the project's persistent briefing to the agent. AGENTS.md is the cross-tool open standard; CLAUDE.md is Anthropic's.

*Real-life:* The laminated card taped over the shift-worker's bench, read at every clock-in — because yesterday's briefing did not survive the night.

### Multiplier Stack (as *The AI Entrepreneur* uses it)

The book's five reusable assets in order: spec once, skill-ify what repeats, cache what is stable, route by cost, and measure the compounding. Each layer turns a cost paid once into a discount collected across later builds.

*Real-life:* Compound interest in machinery: each layer multiplies the last instead of adding to it.

In the book: [chapter 3](chapters/03-the-ai-multiplier.md)

### Operator's Ladder (as *The AI Entrepreneur* uses it)

The book's five-stage progression from hands-on coder to fleet operator: Decide, Leverage, Prove, Sell, and Compound. At each rung you touch the keys less and the decisions more; every rung is something you run and can verify, never a title someone else grants you.

*Real-life:* Deckhand to harbor pilot: same water, and at every rung less rope in your hands and more of the harbor in your head.

In the book: [chapter 0](chapters/00-introduction.md)

### Orchestration

Running multiple agents from one seat: sequencing, redirecting, and merging their work, hands off the keyboard.

*Real-life:* Conducting, not playing: the conductor produces no sound, and the concert is still theirs.

In the book: [chapter 2](chapters/02-the-new-game.md)

### Permission modes / plan mode

The baseline autonomy setting of a coding agent — plan-only, ask-per-edit, auto-approve, full bypass — the practical autonomy slider. Plan mode is the read-only rung: research and propose, no edits until approved.

*Real-life:* The learner-driver ladder: observer, supervised, licensed. Same driver, graduated trust.

### Ralph Wiggum loop

Running the same prompt at an agent in a plain bash loop, fresh context each iteration, progress accumulating in files and git — crude, surprisingly effective on long tasks.

*Real-life:* Named by Geoffrey Huntley for Ralph Wiggum cheerfully ramming ahead ("I'm helping!"): dumb persistence with a fresh head each attempt, beating clever one-shots.

### Rehearsal Loop (as *The AI Entrepreneur* uses it)

The book's four steps of deliberate practice applied to the interview: pick the question you fumble, rep it aloud against an AI counterpart, read the transcript and tag one weakness, then re-rep until the tag disappears.

*Real-life:* Band practice before the paid gig: the set list is only real after it survives rehearsal.

In the book: [chapter 8](chapters/08-win-the-old-game.md)

### Sandboxing

OS-level filesystem and network isolation around an agent's commands, so it can act freely inside a boundary without per-command approval — and without reaching anything load-bearing.

*Real-life:* Letting the apprentice use every tool — inside a room where nothing load-bearing can be reached.

### Scope creep

Doing more than the brief asked — named in the book as the signature agent failure, and the first thing the two-pass review hunts.

*Real-life:* You asked for the faucet fixed; you came home to a retiled bathroom, beautifully done, and a bill.

In the book: [chapter 2](chapters/02-the-new-game.md)

### Shared-nothing

An architecture where workers hold nothing in common, so they never contend for the same resource and adding more workers does not slow the others down.

*Real-life:* Cooks with separate stations, separate knives, separate pans: nothing to fight over, so the tenth cook is as fast as the second.

In the book: [chapter 4](chapters/04-parallel-engineering.md)

### Skill

Industry sense: Anthropic's Agent Skills — a versioned, on-demand, reusable capability file, with SKILL.md as the standard file format. As this book uses it: any versioned reusable spec an agent loads before working — a correction paid for once that never has to be paid again. "A skill without a version is a rumor."

*Real-life:* The factory jig: throwing it away after one part is the choice between a shop that compounds and one that restarts.

In the book: [chapter 3](chapters/03-the-ai-multiplier.md)

### Spec

The durable written statement of the problem, constraints, and the shape of done — the artifact that survives when the code under it is regenerated.

*Real-life:* The blueprint that outlives the building: knock the walls down and rebuild tomorrow; the expensive thinking is still on paper.

In the book: [chapter 0](chapters/00-introduction.md)

### Spec-driven development (SDD)

Treating the written spec as the primary artifact and code as build output; the agent regenerates code from the spec. "The spec is the prompt."

*Real-life:* The blueprint outranks the building: when they disagree, you fix the blueprint and rebuild — never the other way around.

### Subagent / multi-agent

A child agent with its own separate context window and restricted tools, spawned to do a sub-task and report back a summary; a multi-agent system is several coordinating on one job — including the book's adversarial pair, where one agent finds problems and a second tries to refute the first.

*Real-life:* A foreman's crew of specialists — plus the book's own device: two inspectors forced to disagree, because one inspector alone gets confidently wrong.

In the book: [chapter 2](chapters/02-the-new-game.md)

### Tool use / function calling

Letting the model emit a structured request — "call this function with these arguments" — that your code executes, feeding the result back. How models act on the world.

*Real-life:* The model writes the purchase order; your code is the only one with keys to the stockroom.

In the book: [chapter 12](chapters/12-the-daily-driver.md)

### Verification loop

Giving the agent a check it can run — tests, build, screenshot diff — so "done" is decided by the check, not by the agent's own opinion.

*Real-life:* The torque wrench that clicks: the bolt is tight when the tool says so, not when the mechanic feels done.

### Vibe coding

Prompting an AI to build software while barely reading the code, judging only by results — fine for throwaway projects, dangerous for production. Coined by Andrej Karpathy; not all AI-assisted programming is vibe coding, though the word is drifting that way.

*Real-life:* Ordering omakase: hand control to the chef and judge only the plate that arrives — a fine dinner, a bad way to run a restaurant.

### Vibe engineering

Simon Willison's half-serious counter-term to vibe coding: professional, reviewed, tested AI-assisted development of production code.

*Real-life:* The same kitchen with a health inspector on staff.

### Workflow (vs agent)

An LLM pipeline where your code, not the model, decides the order of steps. The key contrast from Anthropic's "Building Effective Agents": most production "agents" are really workflows — and that is often the right call.

*Real-life:* An assembly line versus a locksmith on call: the line executes a fixed sequence; the locksmith sizes up each door and chooses the next move.

### Workflow patterns (prompt chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer)

Anthropic's named building blocks for LLM systems: sequential calls with checks between (chaining), classify-then-specialize (routing), simultaneous calls you merge or vote over (parallelization), a lead model delegating to workers, and a generate-critique loop.

*Real-life:* Kitchen brigade layouts: the same cooks arranged as a line, a relay, or a head chef delegating — pick a layout; do not reinvent it.

### Worktree (git worktree)

Git's way of checking out more than one branch at once, each in its own directory with its own files — so two agents can work the same repository without seeing each other's half-done changes.

*Real-life:* Parallel universes of the same workshop: same blueprints on file, separate benches, and an edit in one universe does not exist in the other until it is committed.

In the book: [chapter 2](chapters/02-the-new-game.md)

---

## Proof and Shipping — repos, CI, deploys, cost

### API (and endpoint)

A service you call over the network with a structured request and get a structured answer — how your code uses a provider's model without owning it. An endpoint is one specific address that does one specific job.

*Real-life:* Ordering at the counter without entering the kitchen: you say the order in the menu's exact words, the kitchen does the work, the plate comes back over the counter. One window takes orders; that one takes returns.

In the book: [chapter 2](chapters/02-the-new-game.md)

### API key / environment variable / .env

The secret credential that authorizes your calls (and gets billed), kept in an environment variable — a setting outside the code — so it never lands in a public repo. A leaked key is a burned key.

*Real-life:* The safe combination: written nowhere on the blueprints, because git remembers — and a combination posted even once is a combination you change.

In the book: [chapter 4](chapters/04-parallel-engineering.md)

### Batch API

Submitting non-urgent model calls together for asynchronous processing at roughly half price; combined with caching, the savings compound.

*Real-life:* The overnight freight rate: half price if the job can ride the slow train.

### CI (continuous integration)

An automatic system that runs your checks on every proposed change and blocks the ones that fail — the robot that already runs your tests, which the eval gate piggybacks on.

*Real-life:* The assembly line's automatic inspection station: every unit passes through it, nobody has to remember to send one, and the belt stops when a check fails.

In the book: [chapter 0](chapters/00-introduction.md)

### Deploy

Putting the system live at a URL where strangers can use it — the step that turns code on your machine into proof anyone can click.

*Real-life:* Moving the piece from the workshop to the storefront window: it is not for sale until it is in the window.

In the book: [chapter 0](chapters/00-introduction.md)

### MCP (Model Context Protocol)

An open standard for how AI tools plug into agents and apps: build a tool once and any MCP-compatible agent can use it. Server = the program exposing tools; client/host = the AI app that connects.

*Real-life:* Anthropic's own analogy: "like a USB-C port for AI applications" — one plug shape, any tool, any agent.

In the book: [chapter 12](chapters/12-the-daily-driver.md)

### MLOps / LLMOps

The engineering discipline of deploying, monitoring, versioning, and governing models in production.

*Real-life:* Fleet maintenance for software: the discipline that keeps deployed vehicles inspected, versioned, and recalled on schedule.

### Model gateway

One layer all model calls pass through, so you can swap providers, set fallbacks, and survive a migration by changing config instead of code.

*Real-life:* One reception desk in front of many specialists: the callers keep one phone number while you change who is on duty behind it.

In the book: [chapter 7](chapters/07-finding-clients.md)

### Pipeline

A series of processing stages where each stage's output feeds the next; the book uses it for both the hiring funnel and the ingest-embed-retrieve-generate chain.

*Real-life:* An assembly line: each station does one job and hands the work to the next, and the line is only as good as its worst station.

In the book: [chapter 0](chapters/00-introduction.md)

### Prompt caching (context caching)

Providers re-serve the unchanged front of your prompt at a steep discount (up to ~90 percent) instead of recomputing it — so the more of your context you hold still, the cheaper every call gets.

*Real-life:* The stockpot kept on the stove: you paid full price to bring it to a boil once; every serving after that costs a ladle, not a fire.

In the book: [chapter 3](chapters/03-the-ai-multiplier.md)

### Pull request (PR)

A proposed change, packaged for review before it enters the main project. The book's unit of shipped work — and the last cheap place to catch a regression.

*Real-life:* Work laid on the reviewer's desk before it goes to print: the editor reads the pages, not the author's summary of them.

In the book: [chapter 0](chapters/00-introduction.md)

### Rate limit

The per-minute cap on requests or tokens a provider allows; production apps queue, back off, and retry around it — and your fleet size is a rate-limit question before it is an ambition question.

*Real-life:* The on-ramp meter: the provider admits so many cars a minute, and the size of your fleet is set by the meter, not by your garage.

### README

The plain-language front page of a repo: what this is, how it is built, and — the book's addition — what you would fix next.

*Real-life:* The note taped to the front of the machine: what it does, how to start it, and the one thing the builder knows is still wrong with it.

In the book: [chapter 5](chapters/05-proof-beats-credentials.md)

### Repo (repository)

The project's home: all its files plus the full history of every change, hosted publicly or privately (GitHub being the default public square).

*Real-life:* A filing cabinet that keeps every draft ever made and who changed what when — and a public repo is that cabinet with the drawers unlocked.

In the book: [chapter 0](chapters/00-introduction.md)

### Routing by cost (model routing)

Sending each call to the cheapest model that can handle it — the easy majority to a small model, the hard minority to the frontier one — encoded as configuration. Practitioner range: 40-70 percent cost reduction.

*Real-life:* The triage nurse: routine cases go to the junior clinician, the specialist sees only what genuinely needs the specialist, and the hospital's bill is the difference.

In the book: [chapter 3](chapters/03-the-ai-multiplier.md)

### Serverless

Hosting where short-lived functions spin up per request and vanish: cheap and zero-config, and the wrong shape for an app that must stay running with state.

*Real-life:* Renting a burner per pancake: perfect for one pancake at a time, useless for a stockpot that must simmer all day.

In the book: [chapter 5](chapters/05-proof-beats-credentials.md)

### Static host

A service that serves fixed files — pages the same for every visitor — which makes hosting a one-page proof site free or nearly free.

*Real-life:* A printed sign in the shop window versus a staffed desk: nothing to run, nothing to crash, pennies to keep up.

In the book: [chapter 11](chapters/11-the-glass-workshop.md)

### Streaming

Sending the response token by token as it is generated instead of waiting for the full answer — the difference between "feels instant" and "feels broken."

*Real-life:* A waiter bringing courses as they are ready instead of holding everything for one big tray: the meal starts sooner.

### Structured output / JSON mode

Forcing the model to reply in a machine-readable format — JSON matching a schema — so software can consume the answer directly instead of parsing prose hopefully.

*Real-life:* Making the model fill in the form instead of writing a letter: the mailroom machine can read forms.

### Tokens-per-dollar / cost-per-task

Judging models and agent designs by what a completed task costs, not by per-token price alone.

*Real-life:* Judging the trip by the total fare, not the per-mile rate: a cheap meter on a wandering route still costs more.

---

## Finding and Serving Clients

### Asymmetric information

A deal where one side can see quality and the other cannot — so buyers price for the worst, and good sellers cannot earn what the work is worth until the asymmetry is deleted.

*Real-life:* The used-car market: the buyer cannot tell a sound car from a lemon, so every car sells at lemon-adjusted prices — until you let them drive it.

In the book: [chapter 7](chapters/07-finding-clients.md)

### Data flywheel

Product usage generates data that improves the product — often through evals or fine-tuning — which attracts more usage: the classic AI network-effect claim.

*Real-life:* A gym whose members' workouts design better equipment, which attracts more members: the usage manufactures the advantage.

### Evals-as-moat

The argument that a domain-tuned private eval suite — plus the labeled failure data behind it — is durable IP: it survives model swaps, and competitors cannot copy it by prompting the same model. An emerging phrase, not yet standardized.

*Real-life:* The house recipe book with the tasting notes: rivals can buy the same oven; they cannot buy your record of what your diners sent back.

In the book: [chapter 6](chapters/06-eval-ci-is-the-moat.md)

### Forwardability

How well your proof survives being passed to a stranger without you in the room — carrying its own context: what it is, why it is credible, what to do next.

*Real-life:* A flyer that still makes sense taped to a lamppost, versus a note that needs its author standing next to it.

In the book: [chapter 11](chapters/11-the-glass-workshop.md)

### Glass Workshop (as *The AI Entrepreneur* uses it)

The book's five-part public proof headquarters on one web page: the live demo, the receipts, the open ledger, the one offer, and the log. It is doing the work where prospects can watch — public repos, a one-page proof site, honest READMEs. Lineage: building in public, and Andy Matuschak's "work with the garage door up."

*Real-life:* A jeweler's bench in the shop window: passersby watch the actual work, and the watching is the marketing.

In the book: [chapter 11](chapters/11-the-glass-workshop.md)

### Moat (in AI)

Whatever a competitor cannot copy by prompting the same model: proprietary data, workflow lock-in, distribution, or a private eval suite tuned to your domain.

*Real-life:* Location, regulars, and the recipe book: everything about the restaurant a rival cannot copy by leasing the identical kitchen.

### Parser / ATS (applicant tracking system)

The software that reads, scores, and files job applications before any human sees them — matching keywords and year counts, not meaning. The book's "machine that was never pointed at your worth."

*Real-life:* A mail sorter that reads envelopes, not letters: three hundred arrive, it files them by postmark and keyword, and a human opens three.

In the book: [chapter 0](chapters/00-introduction.md)

### Proof-first outbound

Building a small, real solution to a problem the prospect has stated publicly, showing it working, and discussing terms only after they have seen the result.

*Real-life:* Showing up with the dish cooked instead of the menu: the buyer is no longer imagining whether you can cook.

In the book: [chapter 7](chapters/07-finding-clients.md)

### Wrapper (GPT wrapper)

The dismissive name for a product that is a thin UI over a model API, with no proprietary data, workflow depth, or switching costs. "Just a wrapper" is the default skeptic critique; the counter is that distribution and workflow are moats.

*Real-life:* A restaurant that only reheats a supplier's food: the sneer writes itself — until the room is full every night because of the service and the address.

---

## Safety and Failure Modes

### Alignment (and HHH)

The broader goal of making AI systems reliably pursue what their operators and society intend, not just what was literally optimized. Anthropic's HHH — helpful, honest, harmless — is the most concrete operationalization.

*Real-life:* Training the dog to want what the shepherd wants, not merely to fear the leash.

### Bias

Systematic unfairness a model absorbs from its training data and reproduces in its outputs.

*Real-life:* A scale zeroed wrong at the factory: every later weighing inherits the tilt, no matter how careful the clerk.

### Constitutional AI

Anthropic's technique of training a model to critique and revise its own outputs against a written set of principles, instead of relying only on human raters.

*Real-life:* An editor with a written style guide instead of a panel of judges: the rules are on paper, and the drafts are checked against the page.

### Data exfiltration (via agents)

An injected agent leaking private data out through any channel it can write to — a URL, an email, a commit. The endgame of the lethal trifecta.

*Real-life:* The compromised assistant mails the safe's contents out through any slot that opens outward.

### Jailbreak

Tricking a model into ignoring its own safety rules through the user's direct prompt. Distinct from prompt injection, which attacks the user through third-party content.

*Real-life:* Talking the bouncer into breaking his own house rules — versus prompt injection, where someone slips the bouncer a fake note from the manager.

### Lethal trifecta

The three conditions that make prompt injection catastrophic when combined: access to private data, exposure to untrusted content, and the ability to communicate externally. Remove any one and the attack defuses. Coined by Simon Willison.

*Real-life:* The fire triangle — fuel, oxygen, spark: safety work is removing one leg, not begging the fire to behave.

### Model card

A standardized disclosure sheet for a model: capabilities, training-data notes, evals, limits, intended use.

*Real-life:* The original Model Cards paper's image: a nutrition label for a model — what is inside, what it is for, what to watch.

### Prompt injection

Hostile instructions hidden in content the model reads — a web page, an email, a tool result — that hijack it into doing something its operator never asked. Named (by Simon Willison) by analogy to SQL injection. Still unsolved.

*Real-life:* A forged memo slipped into the inbox the assistant processes: the handwriting looks like the boss's, and the assistant cannot reliably tell orders from mail.

### Red-teaming

Deliberately attacking your own AI system — adversarial prompts, jailbreaks, edge cases — to find the failures before your users do. The name comes from military exercises.

*Real-life:* Hiring a burglar to break into your own house and hand you the list of ways in.

### Slop

Low-quality AI-generated content produced in volume — and the reputational risk hanging over every AI product. The book's proof-first stance is the antidote.

*Real-life:* The styrofoam packing peanuts of the internet: cheap to produce, bulky, everywhere, and nobody ordered them.

### Slopsquatting

Registering package names that LLMs hallucinate, so agents that install the hallucinated package get malware.

*Real-life:* Squatters building a fake storefront at an address the model keeps inventing: eventually somebody's agent walks in with the company card.

---

> **This is the free edition.** The full book — the rigor passes, the complete stories, and the ship-this exercises that end every chapter — is at aiescu.com. [Reserve the $39.99 launch price](https://aiescu.com/book?utm_source=github&utm_medium=glossary) — free to reserve, nothing charged until it ships.

---

Back to the [README](README.md) · Start reading: [Introduction — You're Early, Not Obsolete](chapters/00-introduction.md)
