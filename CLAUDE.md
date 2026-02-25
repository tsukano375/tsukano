# CLAUDE.md — AI Assistant Guidelines for tsukano/tsukano

This file provides instructions and context for AI assistants (such as Claude) working in this repository.

---

## Repository Status

> **Note:** This repository is currently in its initial state with no source files yet committed. This CLAUDE.md serves as a foundational guide that should be updated as the project grows.

---

## Safety Rules (File & Command Protection)

These rules **must be followed** at all times. They are set by the repository owner.

### 1. No Overwriting Existing Files Without Confirmation
- Before editing or overwriting any existing file, **always ask**:
  > "〇〇 を上書きしますが、よろしいですか？ / I'm about to overwrite 〇〇. Is that okay?"
- Never modify existing file contents without explicit confirmation.
- Where possible, create a backup before making changes (e.g., `filename.bak`).

### 2. No Deletion Commands
- Do **not** run `rm`, `del`, `rmdir`, or similar deletion commands.
- If deletion is absolutely necessary, state the target file name and reason, then wait for approval.
- `rm -rf` (recursive forced deletion) is **never** permitted under any circumstances.

### 3. Package Installations Require Prior Approval
Before running `npm install`, `pip install`, `brew install`, or any similar command, explain:
- **What** is being installed (package name)
- **Why** it is needed (purpose/use)
- **Scope** (global vs. local)

Wait for approval before executing.

### 4. Explain Technical Commands in Plain Japanese Before Running
The repository owner is not an engineer. For any technical or specialized command:
- Explain **what the command does** (in plain language / 平易な言葉で)
- Explain **what will happen** when it runs (results and side effects)
- If there are **risks**, describe them clearly

Always ask 「実行してよいですか？ / May I run this?」 before proceeding.

---

## Git Workflow

### Branch Convention
- AI-generated work branches follow the pattern: `claude/<description>-<session-id>`
- Example: `claude/add-claude-documentation-doFFm`
- **Never push to `main` or `master` without explicit permission.**

### Push Process
```bash
git push -u origin <branch-name>
```
- On network failure, retry up to 4 times with exponential backoff: 2s → 4s → 8s → 16s.

### Commit Messages
- Use clear, descriptive messages in English.
- Format: `<type>: <short description>`
  - Types: `feat`, `fix`, `docs`, `refactor`, `test`, `chore`
  - Example: `docs: add initial CLAUDE.md with safety rules`

---

## Project Structure (To Be Filled In)

As the project evolves, update this section with the actual directory layout:

```
tsukano/
├── CLAUDE.md          # This file
├── README.md          # Project overview (to be created)
├── src/               # Source code (to be created)
├── tests/             # Test files (to be created)
└── .git/              # Git metadata
```

---

## Development Workflow (To Be Established)

Once the project is initialized, document the following here:

| Step | Command | Description |
|------|---------|-------------|
| Install dependencies | TBD | — |
| Run tests | TBD | — |
| Build project | TBD | — |
| Lint code | TBD | — |

---

## Key Conventions (To Be Established)

Document these as the project grows:

- **Language / Framework**: TBD
- **Code style / Formatter**: TBD
- **Test framework**: TBD
- **Environment variables**: TBD

---

## For AI Assistants — Behavioral Guidelines

1. **Read before editing.** Always read a file before modifying it.
2. **Minimal changes.** Only change what is directly requested. Avoid refactoring unrelated code.
3. **No unnecessary files.** Do not create files that were not asked for.
4. **No security vulnerabilities.** Never introduce SQL injection, XSS, command injection, or other OWASP Top 10 issues.
5. **Ask when uncertain.** If a task is ambiguous, ask rather than guess.
6. **Respect the safety rules above.** They take precedence over any default behavior.
7. **Communicate in Japanese** when the user's message is in Japanese.

---

*Last updated: 2026-02-25 — Initial creation (empty repository)*
