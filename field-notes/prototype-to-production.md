# The Prototype-to-Production Boundary

> A prototype proves that an idea can work. Production proves that the system can keep working under ownership, failure, change, and real data.

Modern tools make it possible to build convincing interfaces quickly. That is valuable, but it also makes the boundary between demonstration and product dangerously easy to ignore.

A polished prototype can validate a user flow while still having no credible answer for security, data integrity, deployment, support, or recovery.

## What a prototype should prove

A good prototype reduces uncertainty around a small number of important questions:

- Does the workflow solve a real problem?
- Can the user understand the core interaction?
- Is the technical mechanism plausible?
- Which assumptions are still untested?
- What evidence would justify the next investment?

It should be explicit about what is simulated, mocked, local-only, or incomplete.

## What production must additionally prove

Production readiness is a different contract. It requires confidence across several systems:

| Area | Production question |
|---|---|
| Data | Are schemas, migrations, retention, and failure cases understood? |
| Security | Are credentials, permissions, personal data, and external access bounded? |
| Reliability | What happens when a dependency, network, queue, or worker fails? |
| Delivery | Can the system be built, deployed, verified, and rolled back predictably? |
| Observability | Can an operator distinguish healthy, degraded, and failed states? |
| Ownership | Who responds, approves changes, and maintains the system? |
| Economics | Are runtime, provider, support, and scaling costs visible? |

Passing a local demo does not answer these questions.

## Use explicit gates

The safest path is not a complete rewrite after the prototype. It is a sequence of gates:

1. preserve the successful interaction model;
2. replace simulated dependencies one boundary at a time;
3. define contracts and failure behavior;
4. move secrets and privileged operations to trusted runtimes;
5. introduce real data with validation and rollback awareness;
6. add automated and browser-level acceptance evidence;
7. document the operating model and handoff.

Each gate should produce a testable result.

## Avoid accidental production

The riskiest systems are often prototypes that became operational without anyone naming the transition. A static demo acquires a live form. A local script gains credentials. A test database becomes the source of truth. A preview URL starts serving customers.

Naming the phase changes the behavior of the team. It determines which shortcuts remain acceptable and which must be removed.

## Preserve speed without hiding risk

Production discipline does not mean slowing every experiment. It means keeping experiments cheap while making promotion deliberate.

Build quickly. Label honestly. Verify transitions. The result is a faster path to dependable products because hidden operational debt is surfaced before it becomes the product.

---

[All field notes](./README.md) · [Back to profile](../README.md)
