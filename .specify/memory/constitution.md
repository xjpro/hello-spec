# Hello Spec Constitution

## Core Principles

### I. Mobile-First

- Layouts MUST be designed and styled for small screens (≤ 400px wide) first; larger screens
  are handled with `min-width` media queries that add to, never replace, the mobile styles.
- Every page MUST be fully usable at 320px wide with no horizontal scrolling.
- Tap targets MUST be at least 44×44 CSS pixels.

**Rationale**: Most visitors arrive on phones. Starting small keeps layouts simple and forces
the most important content to the top.

### II. Accessible to Everyone (NON-NEGOTIABLE)

- Every page MUST meet WCAG 2.2 Level AA.
- Every interactive element MUST be reachable and operable with the keyboard alone, in a
  logical tab order, with a clearly visible focus indicator.
- Images MUST have meaningful `alt` text (or `alt=""` when purely decorative).
- Text and interactive elements MUST meet AA color-contrast ratios.
- Content MUST NOT rely on color, hover, or motion alone to convey meaning; animations MUST
  respect `prefers-reduced-motion`.

**Rationale**: Accessibility is a baseline requirement, not a feature. A site that some people
cannot use is not finished.

### III. Semantic HTML

- Markup MUST use the element that matches its meaning: `<header>`, `<nav>`, `<main>`,
  `<article>`, `<section>`, `<footer>`, `<button>` for actions, `<a>` for navigation, and
  real `<label>`s for form fields.
- Each page MUST have exactly one `<h1>`, and headings MUST NOT skip levels.
- ARIA MUST be used only when no native HTML element provides the needed behavior.

**Rationale**: Semantic HTML gives keyboard, screen-reader, and search-engine support for free,
and is the easiest markup for a beginner to understand.

### IV. Fast and Findable

- Every page MUST score at least 90 for Performance and 100 for Accessibility, and at least
  90 for SEO and Best Practices in a mobile Lighthouse audit.
- Core content MUST be present in the HTML sent by the server (pre-rendered at build time or on
  the server); it MUST NOT depend on client-side JavaScript to appear.
- Each page MUST have a unique, descriptive `<title>` and `<meta name="description">`, and a
  `<meta name="viewport">` tag.
- Images MUST be appropriately sized, use modern formats where practical, declare `width` and
  `height`, and be lazy-loaded when below the fold.
- Client-side JavaScript SHOULD be kept small: send only what a page needs to be interactive.

**Rationale**: Fast pages keep visitors, and content in plain HTML is what search engines index
most reliably. React pages are pre-rendered so they meet this bar.

### V. Beginner-Readable Code

- Code MUST be readable by someone who knows basic HTML, CSS, JavaScript, and React.
- UI MUST be written as React function components using hooks; class components MUST NOT be
  used. Components SHOULD be small and focused on one job.
- Any dependency beyond React and the framework chosen to pre-render it MUST be justified in
  the plan's Complexity Tracking table, naming the simpler option that was rejected and why.
- Names MUST be descriptive; functions SHOULD do one thing; clever one-liners MUST NOT be used
  where a few clear lines work.
- Comments SHOULD explain *why* something is done when it is not obvious.

**Rationale**: This is a learning project. Code that cannot be read cannot be learned from or
safely changed.

## Technology & Deployment Constraints

- The frontend MUST be built with React.
- Pages MUST be pre-rendered to HTML (static generation preferred, server rendering when a page
  needs fresh data); a client-only single-page app does not satisfy Principle IV. The plan
  chooses the framework (e.g., Next.js) and records why.
- The site MUST be deployed to Vercel.
- Every page MUST include a `lang` attribute on `<html>`.
- The project MUST include a `robots.txt` and a `sitemap.xml` once more than one page exists.

## Development Workflow & Quality Gates

A change is complete only when all of the following are true:

1. It follows the Spec Kit flow: specify → plan → tasks → implement.
2. It has been checked in a mobile-sized viewport (≤ 400px) and a desktop viewport.
3. Every interactive element has been operated using the keyboard alone.
4. A mobile Lighthouse audit meets the scores in Principle IV.
5. The HTML has no errors in the W3C validator.

## Governance

- This constitution overrides any conflicting guidance in specs, plans, or tasks. The plan's
  Constitution Check MUST pass before implementation starts, and any exception MUST be recorded
  in Complexity Tracking with its justification.
- Amendments are made by editing this file (or re-running `/speckit-constitution`), recording
  the change in a Sync Impact Report, and committing it.
- Versioning follows semantic versioning: MAJOR for removing or redefining a principle, MINOR
  for adding a principle or section or materially expanding guidance, PATCH for clarifications
  and wording.
- Every plan and every review MUST verify compliance with these principles.

**Version**: 1.0.0 | **Ratified**: 2026-09-25 | **Last Amended**: 2026-09-25
