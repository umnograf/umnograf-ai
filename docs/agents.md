# AI Agents

Umnograf AI's agents are the workers of the AI Operating System: each one uses signals, tools, business context, and the [Second Brain](second-brain.md) to perform or propose work within a defined scope. This is a multi-agent system by design — narrow, specialized agents rather than one generalist — because narrow scope makes it possible to reason about what an agent can and can't do, and to grant autonomy incrementally as trust in a given role grows.

Status below matches the main [README](../README.md): **working** means it runs and is used day to day; **supervised** means it's active but a human reviews output before it goes live; **vision** means it's planned but not built.

## Chief of Staff / Orchestrator — *working*

Runs at the start of every work session. Reads current state from the Second Brain — open tasks, active projects, recent decisions — and reports it back before any other agent acts. Routes incoming signals to the agent whose role matches them. This is the coordination layer that keeps other agents from acting on stale or missing context.

## Knowledge Steward — *working*

Maintains the Second Brain itself: structure, links between notes, deduplication, and freshness. Detects drift — where two notes disagree, where a note has gone stale, where something is disconnected from the rest of the graph — and surfaces it for correction. Currently, corrections are reviewed by a human before being applied (see *Current development* in the README); detection itself already runs continuously.

## Content Agent — *working*

Takes raw material — a voice note, a draft idea, incoming source content — through a structured pipeline: capture, structure, draft, review. Produces content staged for human review before publishing, grounded in the Second Brain rather than generated cold.

## AI Outreach — *supervised*

Sources and qualifies leads against an ideal-customer profile, and drafts personalized outreach grounded in context pulled from the Second Brain (who the recipient is, why they're relevant, what's already known about them). Every draft currently passes human review before anything is sent — this is the agent role furthest along the path from supervised toward selective autonomy, since outreach failure modes are visible and reversible (an unsent draft costs nothing).

## Analyst — *supervised*

Watches channel metrics, trend signal, and competitor activity, and turns raw numbers into a digest a human can act on — currently consumed rather than acted on autonomously. The role is scoped to turning data into a legible summary, not to making the resulting decision.

## Research / Market Intelligence — *supervised*

Pulls external signal relevant to the business — market movement, competitor activity, relevant conversation — into the Second Brain as context other agents (particularly Outreach and Analyst) can draw on. Coverage is being expanded; see the [README roadmap](../README.md#roadmap).

## QA / Risk — *in development*

Reviews drafted actions before they reach human approval, evaluating reversibility, exposure, and how well-grounded a draft is in real context. Today this check is largely folded into the human review step itself; formalizing it as a distinct, consistent screening pass — rather than an implicit part of human judgment — is active work (see the [README roadmap](../README.md#roadmap)).

## Why this split, not one agent

A single do-everything agent has to be trusted with every failure mode at once: a mistake in outreach and a mistake in content have very different consequences, but a generalist agent conflates them. Splitting by role means autonomy can be extended role by role, as each one earns it — outreach and content don't have to wait for research to be equally mature, and vice versa.
