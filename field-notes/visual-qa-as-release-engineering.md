# Visual QA as Release Engineering

> If the interface is the product surface, visual verification is part of release engineering.

Unit tests can confirm logic while a broken layout ships to users. A route can return 200 while its navigation is unusable, images never decode, a drawer escapes the viewport, or a critical interaction is hidden below an internal scroll container.

Visual QA closes the gap between code correctness and experienced correctness.

## Test the rendered system

A dependable browser pass covers more than a homepage screenshot:

- real routes rather than isolated components;
- agreed desktop and mobile viewports;
- initial, active, error, loading, and empty states;
- keyboard and pointer interaction;
- internal scrolling as well as body scrolling;
- lazy content after it enters the viewport;
- console errors and failed resources;
- horizontal overflow;
- navigation, forms, and external links.

The test should follow the actual interaction model. A full-page capture can be misleading when the product scrolls inside a fixed application shell.

## Separate structural and visual evidence

Structural checks answer questions such as:

- Is the expected element present?
- Is it visible and interactive?
- Does the route avoid horizontal overflow?
- Did the image decode successfully?
- Did the form reach the correct state?
- Did the correct panel remain visible?

Visual evidence answers different questions:

- Is hierarchy clear?
- Does the composition match the approved direction?
- Are spacing and typography credible?
- Do crops and responsive transformations preserve intent?
- Is motion helping the interaction?

Both are necessary. Neither should impersonate the other.

## Verify after the real release

Local and preview checks are not evidence of the public state.

After deployment, repeat the critical route and interaction sweep against the actual URL. Confirm that the intended commit is live, assets resolve from production paths, caching is not serving stale bundles, and external integrations operate in the released environment.

A release request, CI success, and a working public product are three different states.

## Keep the evidence compact

Visual QA is most useful when the output helps a decision. A good release record can be small:

- routes and viewports checked;
- automated assertions passed;
- screenshots for high-risk states;
- known deviations with acceptance rationale;
- the deployed commit or version;
- unresolved risk and owner.

This creates a repeatable handoff rather than a folder of unstructured screenshots.

## Quality is operational

Visual quality is not decorative. It affects comprehension, accessibility, trust, and conversion. Treating it as release engineering gives design decisions the same operational seriousness as data and infrastructure changes.

---

[All field notes](./README.md) · [Back to profile](../README.md)
