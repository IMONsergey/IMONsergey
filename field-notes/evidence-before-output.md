# Evidence Before Output

> The quality of an AI system is limited less by how fluently it generates and more by how honestly it represents state.

AI-assisted products often fail in a subtle way: the interface looks complete before the underlying work is complete. A model can describe a file it has only discovered, summarize data it has not fully parsed, or present a deployment as successful because a button was clicked.

The remedy is not a longer prompt. It is an explicit evidence model.

## Name the state

A useful workflow distinguishes at least these states:

```text
discovered → accessible → captured → parsed → analyzed → verified → published
```

Each transition requires evidence. A URL in a search result proves discovery, not access. A downloaded document proves capture, not understanding. A successful build proves compilation, not correct behavior. A deployment request proves intent, not a live release.

This vocabulary prevents confident language from outrunning reality.

## Keep provenance attached

Every important output should retain enough context to answer:

- Where did this information originate?
- What transformation was applied?
- Which assumptions were introduced?
- What was checked automatically?
- What was reviewed by a person?
- What remains unknown?

Provenance does not need to become bureaucracy. It can be a source identifier, an input hash, a test report, a screenshot, a commit, or a short decision record. The point is to keep the claim connected to its evidence.

## Separate proposal from mutation

An agent should be able to inspect and propose broadly, while consequential changes stay bounded by explicit scopes.

A dependable pattern is:

1. inspect the current state;
2. produce a typed plan or diff;
3. validate permissions and constraints;
4. apply the smallest coherent change;
5. verify the resulting state independently;
6. record what changed and what did not.

This makes AI work reviewable. It also makes recovery possible when an external service, browser session, or dependency behaves differently than expected.

## Design acceptance evidence early

Verification should not be improvised after implementation. Before building, define what would count as proof:

- a rendered route at specific viewports;
- an API response that satisfies a schema;
- a database invariant;
- a real external status rather than a submitted request;
- a visual comparison against an approved reference;
- a private-data boundary that remains intact.

The evidence can be lightweight, but it must match the claim.

## Why this matters commercially

Clients do not need more confidence theater. They need delivery they can trust.

Evidence-first systems reduce ambiguity in handoff, expose risks before they become incidents, and make collaboration easier across design, engineering, operations, and leadership. They also create a healthier role for AI: not an oracle, but a capable operator working inside a visible system of truth.

---

[All field notes](./README.md) · [Back to profile](../README.md)
