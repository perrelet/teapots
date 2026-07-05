# Mythos — Faceting Schema

Every entry is one file in `entries/`, carrying frontmatter tags on several
independent axes. Nothing is filed under a single spine; views are generated
by querying the facets (see `views/`). This keeps the collection re-sortable
as it grows instead of pre-sorted into a shape we'd later regret.

## Frontmatter template

```yaml
---
name: kebab-case-id            # matches the filename, used for [[links]]
title: Human Readable Title
domain: [ ]                    # field(s) of human activity — see vocab
mode: [ ]                     # symbolic FUNCTION — the interpretive axis
ontology:                     # REGISTER OF EXISTENCE — single value, see below
form: [ ]                     # how it physically manifests
geography: [ ]                # where it is rooted
year:                         # 4-digit ANCHOR year (most citation-relevant); may be empty
era:                          # fuzzy period label, always (carries spans & undatable cases)
centrality: central           # central | peripheral  (the quality gate)
stance:                       # what the EXAMPLE embodies — see vocab (may be n-a)
tags: [ ]                     # open motif vocabulary — cross-cutting threads
creator: ""                   # who made / coined it, if known
source: ""                    # citation / where it's attested
confidence: verified          # verified | needs-check
links:                        # TYPED edges — the canonical graph (see "link graph")
  - {to: other-entry, type: responds-to}
---
```

The canonical link graph is the typed `links:` block (see **The link graph**
below). Inline `[[wikilinks]]` in prose are a reading affordance and may be a
subset of it.

## The ontology axis (central)

Perrelet's whole inquiry — via Russell — is about the teapot's *existence
status*: proven, unprovable, real, imagined. So **ontology is where the thesis
lives.** It answers one question: *in what register does this teapot exist?*
Single primary value per entry; register-crossers get the `ontology-shift` tag.

- **material** — exists in physical reality: a teapot, a teapot-shaped object, or
  a physical teapot-*phenomenon* (a behaviour of real teapots, not an object). The
  register is "physically real," not "is an object" — the object/process split is a
  `form` distinction, not an existence-register one. *(Sky Kingdom's giant teapot,
  Teapot Dome Station, the assassin's teapot, Yixing pots, the Nestlé chocolate
  teapot, Brandt's teapot; the teapot effect — a phenomenon, `form: phenomenon`.)*
- **natural** — a teapot-*form* found or projected in nature; nobody built it a
  teapot, it is *perceived* as one. *(Teapot Rock; the Sagittarius asterism.)*
- **fictional** — exists inside a narrative world: character, story-object, or
  mythology. *(Mrs. Potts, Andersen's & Blyton's teapots, Bunbuku Chagama, the
  Brass Teapot, Gong's Flying Teapot.)*
- **conceptual** — a philosophical/theoretical posit whose very existence is the
  point of contention. The ontologically self-aware category. *(Russell's
  teapot, Perrelet's teapot.)*
- **virtual** — a computational artifact: exists, but only in machines/code.
  *(Utah teapot 3D model — tag `digital-model`; HTTP 418 — tag `technical-spec`.)*
- **linguistic** — exists as a figure of speech, idiom, or a name. *(“tempest in
  a teapot”, “chocolate teapot”, the Teapot Dome *name*.)*
- **performative** — exists only while enacted or embodied. *(“I'm a Little
  Teapot”, where a child's body becomes the vessel.)*
- **representational** — a teapot depicted *as an image* inside a representational
  artwork: painting, photograph, figurative sculpture. It exists as a picture of a
  teapot, not a teapot you could pour from. *(Cézanne's *Still Life with Teapot*.)*
  Distinguished from `virtual` by medium: representational is depiction in an
  artwork, `virtual` is existence in code.
- **discursive** — the teapot as a sustained body of thought, writing, or living
  practice, rather than a single object or argument. *(“Goddess in a Teapot”, a
  decades-long devotional writing practice; “Tao in a Teapot”.)* Distinguished
  from `conceptual` (a *single* posit) by being an ongoing corpus/practice.

**`ontology-shift`** (a tag, not a value): flags a teapot that crosses registers
— the chocolate teapot (linguistic → material, once Nestlé built one), the Utah
teapot (material → virtual), Bunbuku Chagama (fictional ↔ the real temple relic).
The *crossing itself* is a thesis-level finding, so we mark it.

**Split vs. shift.** When a teapot spans registers, decide whether it is *one
teapot/thread crossing registers* or *distinct phenomena sharing a name*:
- **One thread → one entry** with `ontology-shift` — the chocolate idiom and the
  Nestlé pot built *to test that idiom*; the Bunbuku tale and the temple relic it
  *claims to be*.
- **Distinct phenomena → separate entries** joined by `namesake`/typed edges —
  Teapot Rock, the 1922 Dome Station, and the political Scandal: different
  creators, dates and places; three things that merely share a word.
- **Test:** could they have different creators, dates and locations *and still be
  themselves*? If yes, split.

**Primary-register tie-break.** When a teapot lives in two registers, the primary
`ontology` is the register in which it does its *famous cultural work* — the
reason it is in this collection — and the register(s) it crosses into are
recorded with `ontology-shift`. The chocolate teapot is famous *as an idiom* →
`linguistic` (shift → material). The Utah teapot is famous *as the model* →
`virtual` (shift → material). Teapot Rock is famous *as a rock* → `natural`; the
later life of its *name* is a `namesake` tag, not a shift.

## The link graph (typed edges)

`links:` in an entry's frontmatter is the **canonical graph**: a list of typed,
directional edges to other entries. Inline `[[wikilinks]]` in prose are a reading
affordance and may be a subset.

**Edges are for referential / genealogical relationships only** — one work that
knows about, replies to, or derives from another. *Thematic* kinship (two entries
sharing the `self-naming` or `celestial` motif) is **not** an edge: it lives in `tags`
and is found by querying, so the golden-braid motifs stay emergent rather than
hand-wired. Consequence: a root like Russell's teapot has **no outgoing edges** —
everyone points *at* it — and HTTP 418's kinship to "I'm a Little Teapot" is the
shared `self-naming` tag, not a link.

Author each edge on the entry where the relationship *originates* (the responder,
alluder, parodist). Reverse edges are derived by views, not hand-maintained;
`namesake` is symmetric and may be authored on each member of a cluster.

### `type` vocabulary
- **responds-to** — a deliberate reply or inversion (Perrelet → Russell)
- **alludes-to** — references without engaging directly (Gong's *Flying Teapot* → Russell)
- **parodies** — satirizes its target (*Operation Cosmic Teapot* → Russell)
- **mashes-up** — fuses two sources (*Tempest in a Teapot* play → Alice + The Tempest)
- **namesake** — shares or derives a name only; symmetric (Rock ↔ Dome Station ↔ Scandal)
- **see-also** — a genuine but untyped connection (fallback; use sparingly)

## Facet vocabularies

Seed vocabularies — **descriptive, not fixed.** Add a term when the data demands
it and log it in the changelog below. Lock the vocab only once all backlog
entries are classified.

### `domain` — field of activity
philosophy · literature · physics · astronomy · music · spirituality ·
visual-art · design · architecture · film · theatre · computing · politics ·
folklore · language · landmark · museum · business · food

### `mode` — symbolic function *(the interpretive spine; expect multiples)*
- **epistemological** — teapot as a claim about proof / belief (Russell's teapot)
- **refusal** — teapot that asserts itself and won't perform its function (HTTP 418)
- **embodiment** — a human/creature *becomes* the teapot ("I'm a Little Teapot")
- **duality** — concealment, two truths in one vessel (assassin's teapot)
- **cosmic-projection** — teapot mapped onto sky, universe, heaven (Sagittarius)
- **transformation** — meaning through service, breakage, rebirth (Andersen)
- **hospitality** — teapot as gathering / communion (tea ceremony)
- **scandal-power** — teapot entangled with politics & corruption (Teapot Dome)
- **trickster** — mischievous, shape-shifting, alive (Bunbuku Chagama)
- **uselessness-defied** — declared pointless, works anyway (chocolate teapot)
- **self-reference** — the teapot names itself / strange loop (418, Little Teapot)
- **veneration** — the teapot is an object of worship *within the work* (Sky Kingdom)
- **found-form** — the teapot *perceived* in a natural/unplanned configuration;
  pareidolia (Teapot Rock, the Sagittarius asterism)
- **effigy** — the teapot rendered as a large physical replica or structure
  (Teapot Dome Station, Teapot House, Sky Kingdom's teapot)
- **reference-object** — the teapot as canonical model / default primitive (Utah teapot)
- **formal-study** — the teapot as an exercise in pure form or composition (Cézanne, Brandt)
- **proverbial** — the teapot as figure of speech / idiom (tempest / chocolate teapot)
- **scientific-object** — the teapot as an object of scientific study (the teapot effect)
- **collection** — the teapot as object of accumulation / curation (teapot museums)
- **satire** — the teapot as vehicle of satire or social comment (Hadley 1882, Operation Cosmic Teapot)
- **mechanism** — the teapot defined by a trick or engineered mechanism: puzzle-fill, hidden chambers, self-pour (Cadogan teapot; also the assassin's teapot)

> `veneration` is the teapot-as-worshipped *inside* an example. Do not confuse it
> with `stance: devotional`, which is the *entry's own* embodied attitude.
> (Renamed from `devotion` to remove that collision — see changelog.)

> **Vocabulary now adopted:** the stress-test "known gaps" were all promoted as
> their first entries were written in Phase 2 — `reference-object`, `formal-study`,
> `proverbial`, `scientific-object`, `collection`, `satire` (and earlier
> `found-form`, `effigy`). Continue to add a term only when a real entry needs it.

### `ontology` — register of existence
material · natural · fictional · conceptual · virtual · linguistic ·
performative · representational · discursive
*(single value; see the dedicated section above)*

### `form` — how it manifests
thought-experiment · text · character · song · artwork · physical-object ·
building · monument · natural-formation · code · phrase · ceremony · model ·
event · meme · phenomenon
> `phenomenon` — the teapot manifests as a physical *process/behaviour* rather than
> an object (the teapot effect). Pairs with `ontology: material`.

### `geography`
uk · usa · canada-bc · malaysia · japan · china · germany · france ·
denmark · morocco · turkey · australia · cosmos · internet · generic

> Deliberately mixes physical and non-physical locales (`cosmos`, `internet`) —
> the cosmic-projection and computing threads require it. Not an inconsistency.

### `centrality` — Perrelet's gate
- **central** — the teapot is the subject; the work is *about* the teapot.
- **peripheral** — teapot present but not the tenant. Retained only as a
  deliberate **contrast set**, never counted in the main corpus.
  *(First contrast-set entry: `teapot-dome-scandal`.)*

### `stance` — the attitude the *example itself* embodies toward the teapot
skeptical · devotional · playful · earnest · n-a

> Not our cataloguing attitude — the attitude the work embodies. Russell's teapot
> embodies skepticism; Sky Kingdom, devotion; HTTP 418, play; Cézanne and Brandt,
> earnest formal seriousness. Use **n-a** for entries that embody no attitude —
> natural formations and found forms (Teapot Rock, the Sagittarius asterism) have
> no stance. (Retired `neutral`, which had become a dumping ground.)

### `tags` — open motif vocabulary (cross-cutting threads)
Seeds: `water` · `fire` · `earth-air-fire-water` · `unfalsifiability` ·
`burden-of-proof` · `brokenness-repair` · `self-naming` · `celestial` ·
`hidden-truth` · `insulation` · `first-performance` · `conscientious-objector` ·
`teapot-shaped-universe` · `ontology-shift` · `digital-model` · `technical-spec` ·
`namesake` · `pareidolia` · `roadside-novelty`.
Add freely; motifs are how the "golden braid" surfaces.

## The hypothesis this schema is built to test

**The self-reference hypothesis** — the "golden braid" is the strange loop: the
teapot that *names itself*. Query the `self-reference` mode and `self-naming` tag
(currently HTTP 418, "I'm a Little Teapot", the teapot emoji 🫖, teapotting).

**Narrow by definition.** Self-naming means a *reflexive declaration of
teapot-ness* — a teapot that says, in effect, "I am a teapot." First-person
object-narration does **not** qualify: a teapot merely *voiced* in the first person
(Andersen's "The Teapot", 1863 — it speaks *as* a proud teapot but never declares
its teapot-ness) is theatre, not the strange loop. Tested against this boundary and
deliberately excluded, so the criterion stays falsifiable rather than quietly
widening to admit every talking teapot.

> A former **spout hypothesis** and its `spout` axis were retired on 2026-07-05 as
> a false category (see changelog). The giving-out *motif* survives only in the
> prose of entries that genuinely turn on it; it is no longer a tracked facet.

## Sub-schemas & candidate extensions

### Character sub-schema — ADOPTED (minimal), 2026-07-04

Applies to entries with `form: character`. The 4-entry cluster (Mrs. Potts,
Andersen, Blyton, Bunbuku) was drafted with four provisional `char:*` tags, then
the data decided the schema:

- `char:agency` and `char:anthropomorphic` were **universal** across all four —
  no query power beyond `form: character`, so they are **implied by** it and need
  not be tagged (left on existing entries as harmless redundancy).
- `char:role` (**protagonist | supporting**) and `char:arc` (**service | refusal
  | curse-restoration | none**) **varied** — these are the discriminating facets,
  and the only two adopted. Encoded as flat tags: `char:role-<value>`,
  `char:arc-<value>`.

The payoff is `char:arc`: the **service-vs-refusal** axis holds (Andersen's humble
service vs Bunbuku's trickster escape) and ties into the corpus-wide refusal
thread (HTTP 418, the chocolate teapot). Mrs. Potts contributes a third arc
(curse-restoration); Blyton confirms `none` is real (agency without an arc).

_No candidate extensions currently open._

## Vocabulary changelog

- **2026-07-04** — Initial schema.
- **2026-07-04** — mode `devotion` → `veneration` (disambiguate from `stance`).
- **2026-07-04** — added the `ontology` axis (7 registers) + `ontology-shift`
  tag; established it as the central/thesis axis.
- **2026-07-04** — elevated `spout` from tag to its own field (`yes|no|n-a`).
- **2026-07-04** — split provenance from reliability: added `creator`; narrowed
  `confidence` to `verified | needs-check` (dropped `jamie-sourced`).
- **2026-07-04** — added numeric `year`; `era` is now a fuzzy label only.
- **2026-07-04** — inline `[[ ]]` declared canonical link graph; `related:`
  demoted to non-binding "see also".
- **2026-07-04** — added ontology **primary-register tie-break** rule.
- **2026-07-04** — `form`: added `model`, `event`. `domain`: added `food`.
- **2026-07-04** — `stance`: retired `neutral`; added `earnest` and `n-a`;
  redefined as the attitude the example embodies.
- **2026-07-04** — `mode`: added `found-form` and `effigy` (surfaced while
  splitting Teapot Dome).
- **2026-07-04** — corpus: split "Teapot Dome" into `teapot-rock` (natural,
  central), `teapot-dome-station` (material, central), `teapot-dome-scandal`
  (linguistic, **peripheral** — first contrast-set entry).
- **2026-07-04** — added ontology register `representational` (depicted teapots).
- **2026-07-04** — replaced `related:` with a **typed `links:`** graph
  (`responds-to | alludes-to | parodies | mashes-up | namesake | see-also`).
  `links:` is now canonical; inline `[[ ]]` is a reading affordance; thematic
  kinship moved to `tags` (edges are referential/genealogical only).
- **2026-07-04** — added the **split-vs-shift rule** governing multi-register
  teapots (distinct phenomena split; one thread crossing registers shifts).
- **2026-07-04** — added ontology register `discursive` (a sustained body of
  writing/practice, e.g. "Goddess in a Teapot"); distinct from `conceptual`.
- **2026-07-04** — logged **character sub-schema** as a candidate extension
  (watch list), to be decided after the character cluster is drafted.
- **2026-07-04** — Phase 2 begins: adopted modes `reference-object`,
  `formal-study`, `proverbial`, `scientific-object`, `collection`, `satire`;
  added geography `denmark`.
- **2026-07-04** — **adopted** minimal Character sub-schema (`char:role`,
  `char:arc`) after drafting the 4-entry cluster; dropped `char:agency` /
  `char:anthropomorphic` as facets (implied by `form: character`).
- **2026-07-04** — citation pass: all `needs-check` entries verified; cut 3 as
  too generic (yoko, tao, js-museum); moved Operation Cosmic Teapot to peripheral.
- **2026-07-04** — completeness pass: added mode `mechanism`, form `meme`,
  geographies `morocco` / `turkey` / `australia`; +9 entries.
- **2026-07-05** — **kintsugi**: re-registered `teapot-effect` from `conceptual`
  → `material`, and its form from `thought-experiment` → `phenomenon`; widened the
  `material` gloss to admit physical teapot-*phenomena* (behaviours, not objects);
  added `phenomenon` to the `form` vocabulary. *Rationale:* `conceptual` means "a
  posit whose very existence is contested." The teapot effect's *existence* was
  never contested — only its explanation was (for 65 years) — so `conceptual` was
  encoding its **epistemic** status (it's studied in physics) instead of its
  **ontic** register (a physical process). "It's studied" is already
  `mode: scientific-object` + `domain: physics`; carrying it in `ontology` too was
  an **ontology↔mode orthogonality leak**, now closed. *Falsification test:* if any
  future entry's `ontology` is chosen by *how the teapot is studied or treated*
  rather than *where it exists*, the same leak has recurred — re-file it. *Side
  effect, not the motive:* this removes the sole `spout: yes` + `conceptual` cell;
  `conceptual` now = {Russell, Perrelet}, matching its definition exactly. The move
  is justified on the ontic/epistemic argument alone — flagged here so it is not
  read as tuning the corpus toward the spout hypothesis.
- **2026-07-05** — **kintsugi**: **retired the `spout` axis entirely** — the field
  (from all 42 entries), the `### spout` vocabulary, the `by-spout` view, the
  gallery filter, and the "spout hypothesis." Also dropped the now-redundant `spout`
  seed tag and its six uses (each entry's specific tags — `fluid-dynamics`,
  `high-pour`, `two-chambers`, `pareidolia` … — already carried the content).
  *Rationale:* a **false category**. Under the centrality gate (a real teapot is the
  tenant), "has a spout" is ~universal and discriminates nothing; the axis's `n-a`
  values were really "not one discrete pourable teapot" (a museum, a hill, an idiom).
  The only non-tautological reading — "this entry is *about* the spout" — is a
  *motif*, which by this schema's own law belongs in `tags`, not a closed field; and
  the field failed the closed-axis test (careful readers disagreed on the soft cases
  — emoji, Utah, Dome Station). The "spout hypothesis" was agent-originated, not from
  the operator's inquiry (unlike `ontology` and the self-reference thread), and its
  field-hood was a self-reinforcing artifact (posit thesis → build a field to measure
  it → the field makes the thesis look load-bearing). *Falsification test:* a closed
  field is unjustified if its value is ~constant across the corpus (implied by an
  existing gate) or if careful readers disagree on it — that is a tag or a false
  category, not an axis. The self-reference hypothesis remains (it is the operator's).
