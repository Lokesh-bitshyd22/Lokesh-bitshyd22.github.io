---
layout: post
title: "Building an AI-Assisted Research Vault for a Mathematics Thesis"
date: 2026-06-03
tags: [research, obsidian, ai-tools, phd, workflow]
---

Over the past few weeks I have been building a structured knowledge system to manage a year-long thesis. This post describes the full setup: vault structure, templates, and how different AI tools are assigned distinct roles.

---

## The Core Problem

Mathematical research generates heterogeneous material simultaneously — concept notes, paper summaries, meeting action items, daily logs, thesis drafts, open questions. Left unstructured, this becomes unsearchable. The goal was a system where every piece of knowledge has a defined home, a consistent format, and machine-readable metadata, so that both I and AI tools can navigate it reliably.

---

## The Stack

- **Obsidian** — local Markdown vault with `[[wikilinks]]` and YAML frontmatter
- **Graphify** — generates a graph report (`GRAPH_REPORT.md`) and interactive HTML from vault links and tags
- **Claude Code / Claude Cowork** — handles all file operations: creating notes, maintaining backlinks, drafting content, interpreting the graph report
- **ChatGPT** — handles mathematical discussion, proof exploration, and conceptual questions

The key design principle is **strict role separation**. Claude never does mathematics; ChatGPT never touches files. Each tool receives context through dedicated files in `00_AI/`.

---

## Vault Structure

```
Thesis-Vault/
├── CLAUDE.md               ← instructions for Claude Code
├── 00_AI/                  ← AI coordination files
├── 01_Concepts/            ← one note per mathematical concept
├── 02_Papers/              ← one note per paper
├── 03_Meetings/            ← advisor meeting notes
├── 04_Research_Log/        ← daily diary
├── 05_Weekly_Summaries/
├── 06_Monthly_Summaries/
├── 07_Thesis_Snippets/     ← thesis-ready prose by topic
├── 08_Bibliography/        ← refs.bib + PDFs/
├── 09_Assets/              ← figures, diagrams, screenshots
├── 10_Thesis/              ← thesis.md and thesis.tex
├── graphify-out/           ← auto-generated, do not edit
├── Templates/              ← 8 templates (see below)
└── _AI_WORKSPACE/          ← all AI drafts land here first
    ├── drafts/
    ├── scratch/
    └── pending_review/
```

The `_AI_WORKSPACE/` folder is the most important safety mechanism — nothing Claude generates touches the main vault until explicitly approved.

---

## Templates

Every note type has a template with consistent YAML frontmatter:

```yaml
---
title: "..."
aliases: ["..."]
tags: [concept, pit, in-progress]
status: in-progress
related: ["[[Arithmetic Circuits]]", "[[Lower Bounds]]"]
---
```

The `aliases` field prevents graph fragmentation when a concept has multiple names. The `related` field gives Graphify edges before the note body has any prose — critical early in the research when notes are sparse. The `status` field (`in-progress / needs-review / done`) lets Claude filter notes without reading their full content.

The eight templates are: `Concept`, `Paper`, `Meeting`, `ResearchLog`, `WeeklySummary`, `MonthlySummary`, `ThesisSnippet`, and `OpenQuestion`. The last one is worth highlighting — open questions are treated as first-class research objects with their own notes, tracking the origin (which paper or meeting raised them), attempted approaches, and eventually a resolution.

---

## AI Workflow

At the start of every Claude session, it reads five files in order: `AI_CONTEXT.md`, `CURRENT_FOCUS.md`, `OPEN_QUESTIONS.md`, `INBOX.md`, and `graphify-out/GRAPH_REPORT.md`. This gives it a complete picture of the research state before touching anything.

ChatGPT receives context through two files: a static one (background, references, notation conventions) that never changes, and a dynamic one updated periodically to reflect current focus and recent results.

All mathematics is written in LaTeX throughout — inline as `$...$` and display as `$$...$$` — enforced by both `CLAUDE.md` and `AI_CONTEXT.md` so neither tool produces plain-text math.

---

## What This Solves

The system enforces a clean separation between *knowledge capture* (daily logs, paper notes), *knowledge synthesis* (weekly and monthly summaries, concept notes), and *knowledge output* (thesis snippets, `10_Thesis/`). Each layer feeds the next. AI tools operate on the layer appropriate to their strengths, with the graph report as the navigation layer tying everything together.

The full `CLAUDE.md`, `AI_CONTEXT.md`, and all eight templates are available on request.
