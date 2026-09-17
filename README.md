# hey-be-careful — Careful, Step-by-Step Agent Execution for Figma

Register this skill in Figma's custom skill feature and invoke it at the start of a chat. It doesn't touch the canvas — it's a set of six behavioral rules that make the agent slow down, verify, and communicate instead of rushing through a task on autopilot.

---

## What this is

Figma's design agent, like most LLM agents, tends to skip steps it judges "predictable," bundle multiple questions into one, or report "done" without describing what actually happened — especially inside a long multi-step skill. Well-written skill instructions get silently ignored under that pressure.

This skill is a standing set of guardrails against that drift. Once invoked, it applies for the rest of the chat session:

```
1. Ask when anything is unclear — never guess "it's probably this"
2. Follow skill steps in the exact order written — no skipping
3. Verify every result carefully before moving on
4. Ask questions one at a time — never bundle them
5. Share the plan before starting multi-step work
6. Report completions specifically — not just "Done"
```

It has no selection requirement and doesn't read or write anything on the canvas, so it's safe to invoke on any file, at any time, as a first step before other Figma skills or freeform requests.

---

## Scope

- **No canvas interaction.** This skill only sets behavioral rules for the chat session — it never reads or modifies the file.
- **No selection required.** Works regardless of what (if anything) is selected.
- **Session-scoped.** The rules apply for the current chat; invoke it again in a new chat to re-apply them.
- **Complements, not replaces, other skills' own instructions.** It reinforces a skill's existing step-by-step structure rather than adding new steps of its own.

---

## Requirements

- **Figma (Design Agent / custom skill feature).** No external MCP servers or API keys required — register `SKILL.md` as a custom skill and it runs.

---

## Repo structure

```
skills/
  hey-be-careful/
    SKILL.md          — skill definition to register in Figma's custom skill feature
    LICENSE
```

---

## Getting started

**Once published on Figma Community**, you'll be able to add this skill directly from the [AI Skills library](https://www.figma.com/community/ai-skills) — no download needed. Until then, register it from source:

**From source:** clone this repo and register the skill file yourself.

```bash
git clone https://github.com/gaspanik/hey-be-careful-skill
```

**1. Register `skills/hey-be-careful/SKILL.md`** in Figma's custom skill feature.

**2. Invoke it at the start of a chat, before other work.**

```
/hey-be-careful
```

```
Be careful and thorough for this session
```

```
慎重に、一つずつ確認しながら進めて
```

---

## Part of a larger set

This skill is one of 28 Figma-agent skills bundled in **KMRVID Figma Skills** — covering AI-slop-resistant page generation, multi-layout-pattern exploration, layer cleanup, contrast/accessibility checks, tokenization, component audits, ALT text suggestions, and more: [gaspanik.gumroad.com/l/kmrvid-figmaskills](https://gaspanik.gumroad.com/l/kmrvid-figmaskills)

---

Built by Masaaki Komori - [@cipher](https://x.com/cipher) · Skill for [Figma](https://www.figma.com/)
