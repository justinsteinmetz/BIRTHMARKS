https://justinsteinmetz.github.io/BIRTHMARKS/



# BIRTHMARKS

**An archival identity instrument for Grades 11–12.**

> What was written before you spoke.

Before you formed your own understanding of the world, certain stories were already attached to you. Some were inherited through family and culture. Others were projected onto you by institutions and other people.

Students are not asked to defend themselves. They are asked to assemble a record — of names, places, languages, stories, silences, and marks. At the end, the archive is read.

---

## Concept

BIRTHMARKS examines inherited identity through the metaphor of the archive. A birthmark is present from the beginning, not consciously chosen, visible to others before you understand it yourself, and subject to misreading. The instrument asks students to assemble a record of the marks attached to them — and then submits that record to an archivist's reading.

The governing action is **excavation**, not confrontation. This distinguishes BIRTHMARKS from the rest of the suite:

| Instrument | Mechanic |
|---|---|
| The Danger Room | Pressure |
| Default Settings | Behavioural diagnosis |
| Who Are You, Really | Pattern recognition |
| BIRTHMARKS | Archival excavation |

---

## Structure

Six sections, two prompts each. Twelve prompts total. Completable in 20–30 minutes.

| Section | What it examines |
|---|---|
| I — Family & Name | The name as first entry; transmitted values, fears, roles, and generational inheritance |
| II — Place & Language | Geographic identity and its assumptions; languages carried, partial, or lost |
| III — Stories | The founding family story and what it protects; the national story and which parts are carried or resisted |
| IV — Silences | What is present but rarely explained; what the silence protects; what the student has written around |
| V — How Others Read You | Assumptions made before speech; misreadings; the performed self |
| VI — What Continues | Which marks are still running; what is being revised and what resists revision |

### The principle of absence

Incomplete archives are real archives. Students are told from the intro screen that *"I don't know" is a legitimate entry* — stated as instruction, not caveat. On the record screen, blank answers appear as `[no entry]` rather than a dash. What is absent from an archive is as meaningful as what is present. The archivist's reading is instructed accordingly.

---

## The reading

After all six sections, the archive is submitted to the model. The model reads as a historian and archivist — not as a therapist, teacher, or judge.

The reading produces:

**A headline** — 4–8 words drawn from or responding to the archive. Not a type, not a verdict — an observation that feels like a title for this specific archive.

**A reading** — 220–300 words. Specific. Grounded. Reads across sections for patterns: a name that carries shame, a silence about family history, and a repeated story are connected evidence. Does not resolve. Does not end hopefully.

**A signature** — one sentence naming the specific marks that continue, drawn from the student's actual answers. Not the generic project line.

**Three discussion questions** — derived from this archive specifically. Each points to a cross-section pattern, a silence, or a gap between what was inherited and what continues.

### The archivist's constraints

The model operates under strict rules:
- Every observation traceable to a specific answer, silence, or word the student used
- `[no entry]` and `[minimal]` answers are primary evidence — named directly, not worked around
- No therapeutic language: not 'authentic', not 'healing', not 'journey', not 'growth', not 'trauma'
- No reassurance, no praise, no moralising
- Does not begin with 'You' — enters through a specific detail from the archive
- Final sentence locates the student in the archive, does not direct them somewhere

---

## Design

**Aesthetic** — aged paper (`#f5f0e8`), paper grain texture, vignette. Warm sepia accent. The feel of a document that has been kept.

**Typography** — Cormorant Garamond throughout. The serif of old documents, annotation, archival material. IBM Plex Mono for labels and metadata.

**Record screen** — structured as a genuine dossier. Session ID (`BM-XXX-XXX`), date/time stamp, labelled entries. Save / Print button allows students to keep the archive.

**Progress** — a single sepia line that fills as sections complete.

---

## Pedagogical notes

**This instrument requires trust.** The Silences section asks for material that may be sensitive — family gaps, inherited shame, unexplained absences. If classroom trust is not established, students will retreat into vague language. The archivist's reading is designed to name that retreat, but the instrument works better when students don't need to retreat.

**BIRTHMARKS is more emotionally demanding than intellectually demanding.** The prompts are accessible. The emotional territory — inheritance, projection, silence, family — is not always safe. Introduce the instrument with care.

**The result is private by default.** Students choose what, if anything, leaves the room. The Save / Print function allows them to keep the record without sharing it.

**Discussion entry points** (generic — the instrument also generates three specific ones per student):
- "Which section was hardest to write? Why that one?"
- "What did you mark as [no entry]? What does that absence mean to you?"
- "The reading named something. Is it accurate? Where is it wrong — and why might it be wrong in that specific way?"
- "Which mark in your archive do you still not fully understand?"

---

## Abitur Themenfeld relevance

| Themenfeld | Angle |
|---|---|
| The Individual & Society | Inherited identity, race, ethnicity, class, religion; the construction of the self before conscious choice |
| Politics, Culture & Society — UK | Postcolonial Britain; national myths and omissions; migration and belonging; the British Empire as inherited story |
| Politics, Culture & Society — USA | American national narrative; race and representation; migration; the gap between national story and personal inheritance |

BIRTHMARKS is the instrument in this suite most directly relevant to the postcolonial and antiracist dimensions of the UK and USA Themenfelder.

---

## Technical architecture

Uses the same Cloudflare Worker proxy as the rest of the suite. The API key is stored as a Cloudflare environment secret and never exposed in the browser.

```javascript
const PROXY = "https://anthropic-proxy.justin-steinmetz.workers.dev";
```

See the *Who Are You, Really* README for full Worker deployment instructions.

### Deployment

Single HTML file. No dependencies, no build step. Rename `birthmarks.html` to `index.html` and push to a GitHub Pages repository.

The instrument makes one API call per session — the archivist's reading at the end.
