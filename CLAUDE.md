# CLAUDE.md

This file provides guidance for AI assistants (Claude and others) working in this repository.

---

## Repository Status

This repository is currently **empty** — no source files, dependencies, or build configuration have been committed yet. This CLAUDE.md was created to establish conventions before development begins.

Update this file as the project grows, keeping it current with the actual codebase structure.

---

## Project Overview

<!-- Fill in once the project is underway -->
- **Purpose**: _TBD_
- **Language / Runtime**: _TBD_
- **Primary framework**: _TBD_

---

## Repository Structure

<!-- Update this section once files are added -->
```
make-something/
├── CLAUDE.md          # This file
└── (project files TBD)
```

---

## Development Workflow

### Branching

- Feature branches: `feature/<short-description>`
- Bug fixes: `fix/<short-description>`
- AI-generated branches follow the pattern: `claude/<task-id>`
- Never push directly to `main` / `master`

### Commits

- Write short, imperative commit messages (`Add login form`, not `Added login form`)
- Keep commits atomic — one logical change per commit
- Reference issue numbers when applicable: `Fix #42: handle null user`

### Pull Requests

- Fill in the PR template fully before requesting review
- PRs must pass all CI checks before merging
- Squash-merge feature branches; merge-commit hotfixes

---

## Commands

<!-- Populate once tooling is chosen; remove any that don't apply -->

### Install dependencies
```bash
# e.g. npm install | yarn | pnpm install | pip install -r requirements.txt
```

### Run development server / REPL
```bash
# e.g. npm run dev | python -m app
```

### Run tests
```bash
# e.g. npm test | pytest | go test ./...
```

### Lint / format
```bash
# e.g. npm run lint | ruff check . | golangci-lint run
```

### Build for production
```bash
# e.g. npm run build | go build ./... | cargo build --release
```

---

## Code Conventions

### General

- Prefer clarity over cleverness — code is read far more than it is written
- Delete dead code rather than commenting it out
- Keep functions small and focused on a single responsibility
- Avoid premature abstractions; three similar blocks of code is fine, four is a pattern worth abstracting

### Naming

- Use descriptive names; avoid abbreviations unless they are universally understood (`id`, `url`, `http`)
- Boolean variables / functions: prefix with `is`, `has`, `can`, or `should` (`isLoading`, `hasPermission`)
- Exported/public identifiers: describe what they _are_ or _do_, not how they work internally

### Error handling

- Never swallow errors silently
- Validate at system boundaries (user input, external API responses); trust internal code
- Return errors to callers rather than logging-and-continuing deep in the call stack

### Comments

- Write comments to explain *why*, not *what* — the code shows what; comments should add context
- Prefer self-documenting code over comments where possible
- Keep comments up-to-date; a wrong comment is worse than no comment

---

## Testing

<!-- Update once a test framework is chosen -->

- Aim for tests that verify observable behaviour, not implementation details
- Unit-test pure functions; integration-test side-effectful code at boundaries
- Tests live alongside source files **or** in a dedicated `tests/` / `__tests__/` directory (decide and document here once chosen)
- All new features need at least one test; all bug fixes need a regression test

---

## Environment & Configuration

- Store secrets in environment variables, never in source control
- Use a `.env.example` file (committed) to document required variables; keep `.env` in `.gitignore`
- Document all required env vars here once they are known

---

## AI Assistant Guidelines

When working in this repository, AI assistants should:

1. **Read before editing** — always read a file before modifying it
2. **Stay in scope** — only change what is directly requested; avoid drive-by refactors
3. **Match the existing style** — follow whatever conventions are already established in the file being edited
4. **Keep CLAUDE.md current** — update this file whenever the project structure or workflow changes materially
5. **Prefer small commits** — commit one logical change at a time so diffs are easy to review
6. **Never force-push** without explicit user permission
7. **Ask before destructive actions** — deleting files, dropping tables, resetting git history, etc.

---

*Last updated: 2026-03-01 (empty repository bootstrap)*
