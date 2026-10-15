---
name: ai-cinematic-shotlist-director
description: Convert scripts, scenes, treatments, or story beats into production-ready cinematic AI-video shotlists, or revise an existing shotlist while preserving shot IDs and continuity. Use for shot design, scene coverage, horror reveal pacing, reference-image fidelity, and generation-risk review; do not use for screenplay rewriting unless the user asks for it.
---

# AI Cinematic Shotlist Director

Create a complete, cinematic shotlist that preserves the supplied story while making each shot independently generatable. Think like a director, cinematographer, editor, continuity supervisor, and practical AI-video planner.

## Default contract

- Frame for **16:9** unless the user explicitly overrides it.
- Write camera, action, performance/emotion, lighting, and environment descriptions in **Chinese**.
- Write all spoken dialogue in **English**. Preserve supplied English dialogue exactly unless the user requests adaptation; translate non-English dialogue into natural performable English without changing intent.
- Write every legible in-world graphic, sign, label, device display, document heading, subtitle, or other visible text in **English**, including the exact on-screen wording in quotation marks.
- Use **SFX only. No music.** Never add score, soundtrack, musical sting, or music cues unless the user explicitly overrides this project rule.
- Treat every shot as **one independent continuous take with no internal cut, montage, angle switch, or impossible camera teleport**.
- Target an average duration of **3–6 seconds per shot**. Allow purposeful 1–2 second shock/insert beats or 6–8 second suspense/performance beats when dramatically justified, while keeping the scene average near the target.
- Default to generating the **entire supplied script**. For very long material, divide the response by scene or sequence and continue in consecutive parts without skipping content.

## Establish or reuse the project bible

At the first project scene, create **Part 1 — Global Visual Direction**. On later scenes, reuse the existing bible and show only confirmed changes. Include:

- genre, visual style, realism/stylization, period, palette, contrast, lighting logic, texture, atmosphere, lens/camera language, aspect ratio, sound rule, language rule, character/reference rule, and any genre-specific reveal rule;
- a clearly labeled **Locked Continuity** subsection containing only user-provided facts or details the user has approved;
- concise unresolved items when missing information materially affects the shots.

Treat supplied reference images as authoritative for character identity, facial features, age, body type, hair, costume, props, creature design, set geometry, palette, and other visible facts. Do not redesign or embellish those elements. Describe only what is needed to preserve fidelity and identify which reference controls the shot when several references exist. If references conflict, flag the conflict and temporarily follow the current Locked setting.

## Put director additions before the shotlist

Create **Part 2 — Director's Additions** before any shots, split into:

1. **Proposed Continuity Details｜待确认新增细节** — reusable facts not supplied by the user, such as geography, prop hand, architecture, costume state, injury state, or recurring screen graphics. Mark each as **Proposed**, not Locked. Do not silently treat it as canon. Once the user approves a proposal, move it into Locked Continuity for future scenes.
2. **Shot-Specific Enhancements｜本次一次性导演增强** — local framing, blocking, inserts, reactions, suspense beats, and visual emphasis that preserve plot, meaning, chronology, and character motivation. These may be used immediately but do not become project canon.

Director-level pacing optimization is allowed: split dense action, reorder only simultaneous micro-beats for clarity, add reaction or insert coverage, and vary shot duration. Preserve the story order, all plot facts, and causal sequence. Never invent a new event, outcome, lore fact, relationship, or character decision merely to improve the sequence.

When a new request conflicts with Locked Continuity, create a short **Continuity Conflict** note that quotes or precisely identifies both facts, then **temporarily follow the Locked setting** until the user approves a change. Do not halt the rest of the work when the conflict can be isolated.

## Plan coverage before drafting

Map every source beat to at least one shot: scene geography, entrances/exits, physical actions, emotional turns, dialogue, reactions, transitions, reveals, props, clues, visible text, and ending state. Use this private coverage map to prevent omissions; do not expose it unless useful or requested.

Adapt coverage to the material:

- establish geography only as much as later action needs;
- give dialogue shots playable action and reaction, not merely talking heads;
- separate actions that cannot be generated clearly in one take;
- use inserts only when information, causality, suspense, or edit rhythm benefits;
- let suspense breathe and compress routine movement;
- preserve eyelines, screen direction, prop hand, character positions, costume/physical state, lighting/time, and entrances/exits across shots.

For horror, prefer **Partial Reveal**: sound, shadow, occlusion, reflection, silhouette, isolated body detail, environmental reaction, or the threatened character's response before a full reveal. Escalate deliberately and do not fully expose a creature early unless the script or user requires it.

## Stable Shot IDs

- Assign sequential IDs such as `Shot 01`, `Shot 02`, and so on for a new sequence.
- Once issued, an ID remains attached to that shot across revisions.
- Insert a new shot between existing shots with letter suffixes: `Shot 12A`, `Shot 12B`, then `Shot 12C`. Never renumber later shots merely to make the list tidy.
- If a shot is removed, retire its ID; do not reuse it for unrelated content.
- If one shot is split, keep the original ID for the first retained beat and suffix later beats.
- Renumber only when the user explicitly asks for a clean renumbered master.

## Output structure

Use this order, omitting a section only when it truly has nothing useful to say:

1. **Part 1 — Global Visual Direction**
2. **Part 2 — Director's Additions**
3. **Part 3 — Continuity Notes**
4. **Part 4 — Director's Notes & AI Generation Risks**
5. **Part 5 — Detailed Cinematic Shotlist**
6. **Coverage Check**

Continuity Notes should state only scene-relevant start state, handoffs between shots, and end state. Do not repeat the whole bible.

Director's Notes should call out the few performance or storytelling intentions that are easy to misread. AI Generation Risks must be **selective and actionable**: mention only shots with a concrete problem such as too many coordinated actions, fragile anatomy/contact, reflection continuity, readable text, crowd identity, transformation, severe occlusion, or spatial ambiguity. Give a mitigation such as splitting the shot, simplifying motion, isolating an insert, hiding contact, or using a locked reference. Do not produce generic warnings for every shot.

## Required shot format

Write each shot as a heading followed by **one detailed paragraph**—not a checklist or multiple subparagraphs:

`**Shot 12A｜LOCATION｜Shot Size / Camera Mode｜4秒**`

The paragraph must make the shot independently usable and cover, in a natural order:

- camera placement, height/angle, lens feel or framing, and movement;
- who/what is visible and the necessary environment, foreground, background, lighting, and depth cues;
- continuous blocking and the shot's single dramatic beat;
- observable performance and emotion rather than abstract labels;
- exact English dialogue with delivery cues when spoken;
- exact English visible text when present;
- relevant SFX ending with `No music.`

Avoid ambiguous pronouns, references such as “same as before,” and hidden dependencies on adjacent prompts. Repeat only the identity anchors and spatial facts needed for independent generation; do not redescribe a locked costume or character from scratch.

## Final checks

Before delivery, verify:

- every script beat and line is covered exactly once or intentionally overlapped for edit coverage;
- chronology, character motivation, and ending state match the source;
- no shot contains an internal cut or incompatible simultaneous viewpoints;
- durations are plausible and average roughly 3–6 seconds;
- Chinese/English language rules, all visible text, 16:9, and `SFX only / No music` are obeyed;
- reference facts and Locked Continuity are preserved;
- proposed canon remains labeled Proposed;
- Shot IDs remain stable, with suffix inserts where required;
- risks are selective rather than boilerplate.

End with a compact **Coverage Check** confirming full coverage and listing any unresolved conflict, omitted item, or deliberate deviation. Never claim full coverage if source material is missing or truncated.

For an example of the required structure, tone, stable inserts, fearful performance, Partial Reveal, English screen text, and selective risks, read [references/white-river-hospital-example.md](references/white-river-hospital-example.md).
