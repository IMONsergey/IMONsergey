# Platform-Native First

> Automation should respect the operating model of the platform until there is a clear reason to replace it.

Website and design platforms compress a large amount of infrastructure into a working environment: editing, responsive behavior, forms, content models, permissions, publishing, analytics, and collaboration. Exporting the visible result does not automatically export those capabilities.

This is why the first architectural question should not be “How do we extract everything?” It should be “Which system should remain the source of truth?”

## Three legitimate modes

### 1. Work natively

Use the platform editor, components, layout system, CMS, and publishing flow. Automate repetitive inspection, content preparation, QA, or carefully bounded edits around that model.

This is usually the right choice when the team depends on non-technical editing, built-in forms, frequent visual iteration, or platform-specific interactions.

### 2. Export and operate

Move rendered assets and routes to infrastructure you control, while deliberately replacing every capability that used to be provided by the platform.

An export plan must account for:

- forms and email delivery;
- CMS or catalog content;
- authentication and member areas;
- routing and redirects;
- analytics and consent;
- asset optimization;
- deployment, rollback, and monitoring;
- future content updates.

The HTML is often the easiest part.

### 3. Rebuild outside the platform

Choose a new application architecture because product requirements, performance, data ownership, integrations, or long-term economics justify it.

A rebuild should preserve validated content and interaction intent without inheriting accidental implementation constraints.

## Decide by operational truth

The correct mode depends on who edits the product, how often it changes, which integrations are critical, and who will own failures.

A native workflow may be more professional than a custom stack when it gives the client reliable control. A custom stack may be necessary when the platform prevents a core capability. Export can be sensible when the operational replacements are explicit and tested.

The mistake is treating these modes as stages of technical prestige.

## Automate the seams

The highest-value automation often lives between systems:

- turning structured briefs into platform-ready content;
- checking responsive geometry and asset quality;
- validating forms and redirects after publishing;
- maintaining inventories of pages and components;
- preparing safe exports;
- comparing public output with approved references;
- recording deployment evidence.

This improves delivery without fighting the platform.

## Preserve reversibility

Platform work benefits from the same engineering discipline as application development: small changes, clear ownership, previews, explicit publication, and verification against the live result.

The objective is not maximum control. It is the right control, placed where the team can operate it reliably.

---

[All field notes](./README.md) · [Back to profile](../README.md)
