# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

A personal **digital garden** — a learning diary of notes distilled from books, papers, and courses. It is *not* a single application: it has no top-level build, package manifest, lint config, or CI. The bulk is Markdown; code only appears as small, self-contained practice experiments. Treat most changes as writing/editing prose, not shipping software.

## Top-level structure

Each top-level folder is a distinct *kind* of note, with its own note shape:

- `rabbit_holes/` — single-topic explorations (Kafka, Mnesia, Broadway, Hammer, Mox, monitoring…). Shape: concept list → code/shell snippet → references. The largest and most active area.
- `books/` — distilled book notes (cover image → chapter headings → takeaways).
- `beam/` — long-form study of one source (Armstrong's thesis), split chapter-by-chapter with a parent `readme.md` linking children.
- `dojo/` — hands-on coding practice. `dojo/SICP/` is numbered Python exercises; `dojo/lang_chain/` is LangChain experiments. Each has a `readme.md` acting as a curriculum tracker.
- `learning/` — language explorations: `go/`, `lisp/`, `prolog/`, `smalltalk/` (notes), and `rd2/` (d2 diagram source + rendered SVG/PNG).
- `elixir-coding-notes/` — a personal Elixir PR/style guide (conventions, not code).
- `researching/` — newest, mostly empty inbox-style area.

`readme.md` is the front door; `summary.md` is a structural self-review of the garden (its punch list is a good source of intended improvements).

## Running the code experiments

There is no shared toolchain — each experiment runs standalone with its own language tooling:

- **Go** (`learning/go/`): per-folder modules. Run `go run main.go <args>` and test with `go test ./...` from inside the module dir (e.g. `learning/go/hello-cli/`). The only real test suite in the repo lives here (`main_test.go`).
- **Python** (`dojo/SICP/`, `dojo/lang_chain/`): no requirements file. SICP files run directly (`python dojo/SICP/1_square.py`). `dojo/lang_chain/` needs `langchain_openai` installed and `OPENAI_API_KEY` in the environment.
- **d2 diagrams** (`learning/rd2/`): edit the `.d2` source, then render with `d2 s1.d2 s1.svg`. Commit both source and rendered output (existing files do).
- **Lisp / Prolog** (`learning/lisp/`, `learning/prolog/`): loaded into a REPL (sbcl / swipl), not built.

## Conventions for notes

- **Use relative links between notes** (`./drawing_hypothesis.md`, not absolute GitHub URLs). The repo was renamed from `the-rabbit-notes`; absolute links to the old name are stale — don't add more.
- The aspirational note template (see `summary.md` §4) is: optional frontmatter (`title`, `type`, `status: seedling|budding|evergreen|archived`, `related: [[...]]`) → `# Title` → `> one-line essence` → `## Concepts` → `## Code / Commands` → `## My take` (personal synthesis) → `## References`. Most existing notes are partial; prefer adding a "My take" synthesis layer and cross-links (`[[other-note]]`) when editing.
- Keep the parent-`readme.md`-links-children pattern when adding files to `beam/`, `dojo/`, or `books/`.

## Elixir style guide (when touching Elixir, or notes about it)

From `elixir-coding-notes/README.md`: order functions alphabetically; `get_`-prefixed functions return `nil | t()`; use `ensure` not `maybe`; trailing `!` for raising functions; pattern-match instead of `case`; `with` for Repo operations; private functions skip `@spec`; tests use present tense and Arrange/Act/Assert (never assert before act).
