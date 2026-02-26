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

## Project Structure

```
tsukano/
├── CLAUDE.md          # This file
├── index.html         # コーチング学習ツール（メインファイル）
└── .git/              # Git metadata
```

---

## このプロジェクトについて

**コーチング学習ツール** — ブラウザで開くだけで動く、シングルHTMLファイルのWebアプリ。

### 学習コンテンツ

| モード | 内容 |
|--------|------|
| フレームワーク辞典 | GROW・傾聴・承認・SMARTゴール等 7項目 |
| クイズ | コーチング理論・手法 全10問 |
| ケーススタディ | 実践シナリオ 3場面（選択式） |
| ロールプレイ | 会話練習シナリオ 2本（スコア付き） |

### 使い方
- `index.html` をブラウザで開くだけ。インストール不要。
- 進捗・バッジは `localStorage` に自動保存される。
- APIキー不要（ロールプレイはスクリプト式）。

---

## Development Workflow

| Step | Command | Description |
|------|---------|-------------|
| 起動 | `index.html` をダブルクリック | ブラウザで開く。サーバー不要 |
| 編集 | `index.html` を直接編集 | CSS・JS・データすべて1ファイル |

---

## Key Conventions

- **Language / Framework**: Vanilla HTML / CSS / JavaScript（ライブラリなし）
- **データ保存**: `localStorage`（サーバー不要）
- **コンテンツ追加方法**: `quizData` / `caseData` / `rpScenarios` / `dictData` 配列に追記する

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

*Last updated: 2026-02-26 — コーチング学習ツール (index.html) を初期作成*
