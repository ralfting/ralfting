### Hi, I'm Ralph 👋

Senior Software Engineer with 11 years of building for the web, currently at [Birdie](https://birdie.ai) in Santa Catarina, Brazil. At Birdie I work on the frontend with React and TypeScript. On my own projects I go full stack in TypeScript: Next.js on the front, NestJS on the back, and [Effect](https://effect.website) holding the two together.

What I care about in a codebase:

- **Types that rule out wrong states**, so the compiler catches mistakes before a reviewer has to.
- **Clear boundaries**: layers with import rules enforced by lint rather than by convention, and an API contract the client and server both compile against.
- **Root causes over patches**: every non-obvious bug gets a write-up and a test that keeps it fixed.
- **Design systems** that make the consistent choice the easy one.

### At Birdie

- **Brought a testing culture to the frontend.** When I joined in July 2025 the app had 13 test files. I pushed for tests to be part of how we build and review, and in my first six months I wrote more of the new ones than anyone else (40 of 101). The team took it from there: today the frontend has 1,900+ test files and 10,700+ test cases.
- **Designed the foundation of the frontend architecture**: a domain-driven, layered React app with MVVM at the page level.
  - Code is organized by business domain, and dependencies flow one way: pages → features → use cases → domains → infrastructure. Flows that span several domains live in use cases, so domains never reach sideways.
  - Each domain keeps its entities apart from API DTOs, bridged by mappers, and owns its server state through React Query hooks.
  - Each page is a component that only renders plus a colocated ViewModel hook that returns `{ state, operations }`.
  - Lint enforces the main import bans.
- **Made bugs teach.** I started the bug dossier, a searchable knowledge base with one write-up per resolved bug and its root cause. AI agents and engineers search it before investigating a new bug. The team has written 68 so far. Before that I built our first AI bug-fix pipeline, which took a Jira ticket to a pull request with Claude Code.

### What I'm building

**[WisePath](https://github.com/ralfting/wisepath)** is a notebook for learning a subject on your own. You write pages in markdown, link them with `[[Title]]`, and the subject is drawn as a map. I've been building it solo since March 2026 with Next.js 15, NestJS and Effect 4, on Vercel and Neon.

- **One contract, two apps.** The API is described once as an Effect `HttpApi` in a shared package. The web client is generated from it and the server serves it as OpenAPI, so changing an endpoint breaks the web build, not production.
- **Tested without mocks.** Every service has an in-memory `Layer` beside its HTTP one, which keeps 100 test files and 8 Playwright end-to-end suites fast and honest.
- **18 bugs, 18 write-ups.** Each non-obvious bug has a root-cause document and the test or lint rule that prevents it from coming back.
- **Shipped continuously.** Every push to `main` that passes CI migrates Neon and deploys the apps it touched to Vercel. 730 commits so far.

<a href="https://github.com/ralfting/wisepath">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/ralfting/wisepath/main/assets/map-dark.png">
    <img alt="WisePath: a TypeScript learning path drawn as a map" src="https://raw.githubusercontent.com/ralfting/wisepath/main/assets/map-light.png">
  </picture>
</a>

### Stack

TypeScript · React · Next.js · NestJS · Effect · Mantine · PostgreSQL · Drizzle · Vitest · Playwright · Vercel

### Elsewhere

[LinkedIn](https://www.linkedin.com/in/ralph-effting/)
