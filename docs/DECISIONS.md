# Decisions

This file records why the project is shaped the way it is. Add a new entry when a decision changes the architecture, the stack, or how the site is hosted. Do not treat a chat message as the record if it is not written here.

## Philosophy

1. **Complete ownership of source code.** Pages, styles, scripts, assets, and docs live in this repository. The site should not depend on a hosted builder or on generated code that nobody can edit by hand.
2. **Maintainable without AI assistance.** File names, folder roles, and documents should be clear to a person using an ordinary editor and Git.
3. **Minimal dependencies.** Prefer the browser platform: HTML, CSS, and JavaScript. Add a dependency only when the project cannot meet a real requirement without it.
4. **Transparent architecture.** A page is an HTML file plus the CSS and JavaScript it links. There is no hidden build, server, or service in the default design.
5. **No unnecessary infrastructure.** Do not create accounts, servers, databases, or third-party products ahead of a demonstrated need.
6. **Clear documentation.** Stack, decisions, progress, deployment, and maintenance stay in `docs/`.

## Recorded decisions

### D1 — Static HTML, CSS, and JavaScript

- **Status:** Accepted
- **Decision:** The first version of the site is a static frontend. HTML holds content and structure. CSS holds presentation. JavaScript is added only for behavior that HTML and CSS cannot provide.
- **Reason:** The site is informational. A static frontend is enough for service descriptions, and it stays portable and reviewable.
- **Consequences:** No framework install, no package manifest, and no compile step unless a later decision adds one.

### D2 — No backend, database, CMS, or authentication by default

- **Status:** Accepted
- **Decision:** Do not introduce a backend, database, CMS, or authentication unless a requirement is demonstrated and the change is approved before implementation.
- **Reason:** Those systems add accounts, hosting, and maintenance that this site has not been shown to need.
- **Consequences:** Content updates are file edits in this repository. Forms, logins, and searchable databases are out of scope until a decision says otherwise.

### D3 — No external services by default

- **Status:** Accepted
- **Decision:** Do not call external services, create external accounts, or provision infrastructure without approval. Document anything that is approved in `TECH_STACK.md` and `DEPLOYMENT.md`.
- **Reason:** External services move behavior and data outside the repository and are harder to maintain or remove later.
- **Consequences:** Fonts, images, and scripts should be files in this repository if they are used. Analytics, embedded widgets, and form processors are not assumed.

### D4 — Repository and Git are already established

- **Status:** Accepted
- **Decision:** Use the existing Git repository. Do not change Git configuration as part of project setup.
- **Reason:** The repository already has `main`, an initial commit, and a configured identity. Setup work should not rewrite that.
- **Consequences:** Progress marks repository setup and Git configuration as completed. Later Git changes, if any, need a separate request.

## Open decisions

These are unresolved. Do not implement them until they are accepted and moved into Recorded decisions.

- Page list and navigation labels
- Brand colors, typography, and logo files
- Whether contact happens by a displayed email and phone number, or by a form (a form may require a processing service)
- Domain name, DNS host, site host, and HTTPS
- Whether any font files will be self-hosted
- Legal pages (privacy, terms) and the exact public business name and address to display
