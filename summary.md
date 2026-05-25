# Digital Garden — Structural Review & Feedback

> A reading of how you currently model, structure, and communicate information across this repo — what works, what is leaking value, and concrete moves to strengthen the system.

---

## 1. How you currently model information

Your garden has a clear *implicit* taxonomy, even if it isn't documented anywhere:

| Folder | Role (inferred) | Note shape |
|---|---|---|
| `beam/` | Long-form study of a single source (Armstrong's thesis) | Chapter-by-chapter, parent `readme.md` links children |
| `books/` | Distilled book notes | Cover image → title → headings per chapter → numbered/bulleted takeaways |
| `dojo/` | Hands-on practice (SICP, LangChain) | Source code files + a `readme.md` that acts as a curriculum tracker |
| `learning/` | Language explorations (Go, Lisp, Prolog, Smalltalk, d2) | Phased learning plans + small experiments |
| `rabbit_holes/` | Single-topic exploration (Kafka, Mnesia, Broadway, Hammer…) | Concept list → code snippets → references |
| `elixir-coding-notes/` | A personal style guide for Elixir PRs | Bulleted conventions |

The recurring "atomic note" template you reach for, when you're at your best, is roughly:

```
![cover image]
# Title (+ subtitle / source attribution)
> One-line quote or definition
## Concept group 1
- crisp bullet
- crisp bullet
## Concept group 2
```code example```
## References / Further reading
```

This template is in use most clearly in `rabbit_holes/kafka.md`, `rabbit_holes/monitoring.md`, `rabbit_holes/mnesia_basics.md`, `rabbit_holes/broadway.md`, and the Smalltalk notes. **It works — when you follow it, the notes are excellent.**

---

## 2. Strengths

### 🌟 A real voice, not a paraphrase machine
The best parts of the garden are where *you* show up — not just the source. `learning/smalltalk/readme.md` is a standout: "Causal loops", "XRay analysis", "Open-heart surgery", "Tinkering Toolkit", "Lost in the forest", "Black Holes", "Turtle Steps", "White Belt", "Retrospective Maps". These are **your** mental models, named in *your* language. They are exactly what a digital garden should produce: distilled, reusable, recognizable thinking. `dojo/SICP/bloom.md` does the same with the "Code Learning" loop and the "Equilibrium Protocol."

### 🌟 Cross-disciplinary stitching
Drawing → systems thinking → music (Sonic Pi) → BEAM operations → management — you're already wiring distant ideas together. `books/drawing_hypothesis.md` quietly powers your visual-thinking instinct, and that bleeds into how you reason about architecture and code.

### 🌟 Concept + code + command, side by side
`rabbit_holes/kafka.md`, `mnesia_basics.md`, `hammer.md`, `mox.md` follow the same instinct: explain the idea, then drop the shell command or the Elixir snippet that makes it concrete. This is *learning-by-doing* baked into the note shape — strong pedagogy.

### 🌟 Capturing the "why," not only the "what"
`programming-as-theory-building.md`, `the-programmers-brain.md`, `engineering_management.md`, the XP and TDD notes — these go beyond mechanics into *philosophy of practice*. That's where notes survive longest because they age more slowly than syntax.

### 🌟 A reading-list culture
`readme.md` ends with curated references by theme (visual thinking, Erlang, ML, knowledge management, code reviews). It's a public-facing "currents I'm reading in" — valuable as a thinking-out-loud artifact.

---

## 3. Opportunities to improve

### ⚠️ The root index doesn't match the garden
`readme.md` only links the `rabbit_holes/` folder. `books/`, `beam/`, `dojo/`, `learning/`, `elixir-coding-notes/` are invisible from the front door. A reader (including future-you) has no map.

### ⚠️ Broken / stale internal links
`books/readme.md` links to `github.com/carlogilmar/the-rabbit-notes/...` — the **old repo name**. Every one of those is dead. Use relative paths (`./drawing_hypothesis.md`) so the garden survives renames.

### ⚠️ Inconsistent note density
The template works *when followed*. But:
- `dojo/lang_chain/readme.md` — one line, with a typo ("Lang Chaing").
- `rabbit_holes/readme.md` — just an image.
- `rabbit_holes/doc.md` — 7 bullet fragments, no real shape.
- `rabbit_holes/erlang.md` — duplicates the same links already in `readme.md`.
- `rabbit_holes/git-learning.md` — strong content, but tabs/spaces are inconsistent, headings collapse mid-file, list nesting is broken.

These stubs leak credibility from the strong notes around them.

### ⚠️ No cross-linking between notes
`rabbit_holes/wombat.md` and `rabbit_holes/monitoring.md` are the same conversation — neither links to the other. `rabbit_holes/mox.md` should reference `elixir-coding-notes/README.md`. The Smalltalk notes on "Programming as Thinking" and `books/programming-as-theory-building.md` are siblings in spirit but isolated on disk. **Your ideas are already a graph; the filesystem is hiding it.**

### ⚠️ No personal synthesis layer in most notes
Most `rabbit_holes/` notes are *faithful summaries of external sources*. The Smalltalk note is the exception — it ends in a "My Own Mental Models" section. That move (source → synthesis → mental model) is what turns a notebook into a **garden**. Without it, the notes are a wiki of someone else's ideas.

### ⚠️ No status / freshness signal
Nothing tells you (or a reader) whether a note is:
- 🌱 a seedling (just started, half-formed)
- 🌿 budding (actively expanding)
- 🌳 evergreen (you trust it; it's distilled)
- 🪦 archived (kept for history, no longer maintained)

Without this, a stub like `rabbit_holes/redis.md` looks like the same kind of artifact as a polished note like `rabbit_holes/monitoring.md`.

### ⚠️ You reference Diataxis — but don't use it
Your own `readme.md` links to [Diataxis](https://diataxis.fr/). Diataxis says: separate *tutorials*, *how-tos*, *reference*, and *explanation*. Right now, many notes mix all four — e.g. `kafka.md` is part explanation, part installation how-to, part reference list. Pulling these apart (even just within a single file, with clear headings) would sharpen each.

### ⚠️ Spelling / language polish
There's a steady drip of typos that erodes the work: "Lang Chaing", "amstrong", "Absthinte", "writter", "implementors", "succes", "Knowdlegde", "responsabilities". A single proofreading pass over the top 10 notes would visibly raise the floor.

### ⚠️ Misplaced / ambiguous naming
- `elixir-coding-notes/` is a *style guide*, not coding notes. Either rename or move under `rabbit_holes/elixir_style.md`.
- `dojo/SICP/bloom.md` contains three unrelated frameworks (Code Learning, LLM Context Structure, Equilibrium Protocol). These deserve to be **three separate evergreen notes** — they're some of your best original thinking and they're buried.

---

## 4. A note template worth standardizing

Below is a refinement of the template you're already using, so future notes drop into it without thinking:

```markdown
---
title: <Topic>
type: rabbit-hole | book | dojo | language
status: seedling | budding | evergreen | archived
sources:
  - <link or book title>
related:
  - [[other-note-name]]
last-touched: 2025-10-15
---

# <Title>

> <one-line essence / quote / why this matters>

## Concepts
- ...

## Code / Commands
```lang
...
```

## My take
<the synthesis layer — what you now believe about this, in your own words>

## Open questions
- ...

## References
- ...
```

Even adopting just **`status` + `My take` + `related`** would transform the garden.

---

## 5. A prioritized punch list

If you want quick, high-leverage moves, do these in order:

1. **Fix the front door.** Rewrite `readme.md` to index every top-level folder, not just `rabbit_holes/`.
2. **Repair stale links.** `books/readme.md` points at `the-rabbit-notes`; sweep the repo for that string.
3. **Promote your originals.** Split `dojo/SICP/bloom.md` into three evergreen notes (`learning-loop.md`, `llm-context.md`, `equilibrium-protocol.md`) and link them from the root.
4. **Add a `My take` section** to your five most-visited notes. Even three bullets is enough.
5. **Add status labels** (🌱🌿🌳🪦) at the top of each note — start with the ones you know are mature.
6. **Spelling pass** on the top-level `readme.md` and the 5 most-linked notes.
7. **Cross-link siblings**: wombat ↔ monitoring, mox ↔ elixir-coding-notes, smalltalk ↔ programming-as-theory-building, drawing-hypothesis ↔ visual thinking refs.
8. **Decide what to do with stubs.** Either grow them or move them to an `inbox/` folder so the rest of the garden looks intentional.

---

## 6. Feedback on how you *learn* (not just how you write)

A few patterns I notice across the garden, which may help your learning loop itself:

- **You're a collector with a synthesizer underneath.** The collector side dominates most folders; the synthesizer side shows up in Smalltalk, bloom.md, and the management notes. Push the synthesizer earlier — make a "My take" *the first* thing you write after reading a source, not the last (or never).
- **You think in metaphors better than in lists.** "Black Holes", "Turtle Steps", "Tinkering Toolkit", "Equilibrium Protocol", "Career Termometer" — these stick because they're images. When a note feels lifeless, the missing ingredient is usually a metaphor. Ask: *what is this idea like?*
- **You return to BEAM, distributed systems, and visual thinking again and again.** Those are your *home territories*. Consider building a single "Carlo's BEAM playbook" evergreen note that pulls together monitoring, mnesia, broadway, wombat, kafka into one personal architecture stance — that's a stronger artifact than the same content scattered across 8 files.
- **The visual sense is underused.** You love drawing as a thinking tool (per `drawing_hypothesis.md`, your Smalltalk cover sketches, the d2 experiments in `learning/rd2/`). Many `rabbit_holes/` notes have no diagram. A small ASCII or d2 diagram per note would massively raise their reusability.
- **You're writing for two audiences at once: you-now and you-in-6-months.** You-in-6-months won't remember why you wrote a note. A `> Why I wrote this:` line at the top of each note costs nothing and pays back forever.

---

## 7. Closing

The garden's bones are good. The instincts are right — distill, name, connect, sketch, layer mechanics with philosophy. The biggest gap isn't *how* you take notes; it's that **you don't yet treat the garden as a system**. There's no front door, no status, no cross-links, no synthesis layer enforced by habit.

Fix those scaffolds and the same notes — without changing their content — will start *compounding* on each other. That's when a notebook becomes a garden.
