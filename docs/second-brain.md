# Second Brain: the Knowledge & Memory Layer

The Second Brain is the knowledge and memory layer inside Umnograf AI. It is not the whole system — it's the substrate that AI agents read from and write to, sitting between orchestration/agents and the business tools they act on.

```
AI Operating System → Orchestration → AI Agents → Second Brain / Knowledge & Memory → Business Tools & Data → Human Approval
```

## Why AI agents need a memory layer, not just a prompt

An AI agent without persistent memory starts every task from whatever fits in its context window: the current message, maybe a few recent ones. That's enough for a single reply, but it breaks down the moment work spans more than one interaction — which is most real business work.

A lead conversation happens over weeks. A content idea gets revisited after a competitor does something relevant. A decision made in March should still shape a draft written in September. None of that survives in a stateless prompt. The Second Brain exists so agents can retrieve *why* something is the way it is, not just *what* it currently is — decisions, context, and outcomes, not just current values.

## What makes it a knowledge layer for agents, rather than a notes app

A personal note-taking vault is written by one person, for that person's own later recall. The Second Brain in Umnograf AI is written and read by multiple agents as well as a human, which changes what it needs to do:

- **Structured enough to retrieve reliably.** Agents query it programmatically (via a retrieval/reasoning engine), not just by a human scrolling and searching.
- **Consistent across writers.** An outreach agent, a content agent, and a human all write into the same knowledge base — entries need consistent structure and linking so nothing becomes an island.
- **Continuously maintained.** Knowledge that isn't kept current is worse than no knowledge, because agents will act on it as if it were true. Consistency checks — deduplication, drift detection, staleness — run against the Second Brain rather than being a one-time cleanup.
- **The record of outcomes, not just facts.** Every action an agent takes writes its outcome back in, so "what happened last time" is retrievable context for "what should happen this time."

## Relationship to Obsidian

The underlying note graph is built on Obsidian-style Markdown: plain-text notes, wiki-style links between them, and folder structure that reflects the business's own domains rather than a generic schema. This keeps the knowledge human-readable and human-editable directly, not locked behind a proprietary format — the human operator can open, read, and edit the same notes the agents retrieve from.

Obsidian itself is the human-facing view. The retrieval and reasoning layer that agents use to query this note graph is a separate, purpose-built engine — the Second Brain is the knowledge graph itself; Obsidian is one way of looking at it.

## From notes to context to action

The path from a note in the Second Brain to an agent's action looks like this:

1. A signal or task needs context (who is this lead, what did we decide about X, what's the current state of Y).
2. The retrieval layer searches the Second Brain and returns the relevant notes and links, not just keyword matches.
3. An agent grounds its draft in that retrieved context, rather than generating from the prompt alone.
4. The outcome of the resulting action — sent, approved, rejected, replied to — is written back into the Second Brain as a new fact.

This closes the loop: the Second Brain isn't just where knowledge is stored, it's where the system's judgment compounds.

## What this repository does not cover

The actual contents of the Second Brain — client information, internal decisions, personal notes — are private and are not part of this public repository. What's documented here is the architecture and role of the memory layer, not its content.
