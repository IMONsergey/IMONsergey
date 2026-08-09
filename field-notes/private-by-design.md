# Private by Design

> Privacy is strongest when sensitive material is structurally unnecessary to the public workflow.

Automation projects naturally accumulate context: credentials, customer records, browser sessions, infrastructure details, generated profiles, internal decisions, and diagnostic logs. Security degrades when all of that context is treated as ordinary project content.

A private-by-design system creates different homes for different classes of information.

## Separate durable knowledge from runtime secrets

The repository should contain what a new operator needs to understand and reproduce the system:

- architecture and data-flow documentation;
- safe configuration examples;
- schemas and validation rules;
- deployment and rollback procedures;
- non-secret identifiers where appropriate;
- tests and verification commands;
- incident learnings without exposed credentials.

Runtime secrets belong in dedicated secret stores, protected environment variables, or local ignored files. Personal records and client datasets need their own access and retention rules.

A private repository is not a substitute for secret hygiene.

## Minimize sensitive inputs

Before automating a workflow, ask whether the system needs the sensitive field at all.

Good patterns include:

- using stable internal IDs instead of copying full personal records;
- storing secret names rather than secret values;
- reporting aggregated state instead of raw logs;
- passing temporary credentials only to the process that needs them;
- keeping generated client configurations outside version control;
- designing test fixtures that contain no real customer data.

The safest secret is the one the workflow never receives.

## Make boundaries testable

Privacy rules should produce observable checks:

- ignored paths are verified before commits;
- public builds are scanned for accidental secrets;
- logs are reviewed for tokens and personal data;
- external listeners and permissions match the intended architecture;
- example configuration uses placeholders;
- exported artifacts are checked independently of source files.

This turns security from a promise into a release condition.

## Avoid context leakage through convenience

Common failure modes are ordinary conveniences:

- pasting an entire environment file into a debugging thread;
- committing a real dataset because the mock is incomplete;
- exposing infrastructure addresses in public documentation without need;
- retaining temporary browser or export artifacts indefinitely;
- treating a generated access link as harmless text;
- sending verbose diagnostics to a third-party service by default.

The solution is a smaller diagnostic surface and deliberate redaction, not silence.

## Build trust through restraint

A professional system does not demonstrate capability by exposing everything it knows. It demonstrates judgment by revealing only what the audience needs.

Private-by-design architecture improves security, but it also improves maintainability. Clean boundaries make automation easier to test, repositories easier to share, and operational ownership easier to transfer.

---

[All field notes](./README.md) · [Back to profile](../README.md)
