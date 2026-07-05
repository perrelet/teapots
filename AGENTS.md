# AGENTS.md — the Mythos project

**Mythos** is a faceted taxonomy of the teapot as a central object of human
meaning-making: the working corpus behind the Fractal Teapot, feeding toward Jamie
Perrelet's thesis on the "golden braid" of teapot-lore. Everything lives in
`mythos/`.

## Layout
- `mythos/README.md` — the index (entries grouped by ontology; hypothesis tallies)
- `mythos/SCHEMA.md` — facet axes, vocabularies, governing rules, changelog
- `mythos/entries/` — one markdown file per teapot, faceted in YAML frontmatter
- `mythos/views/` — **generated** cross-sections; do not hand-edit
- `mythos/build-views.py` — regenerates the views from entry frontmatter

## How the corpus works (see SCHEMA.md for the full detail)
- **Faceted, no single spine.** Every entry carries tags on independent axes;
  `ontology` (the register of existence) is the central/thesis axis.
- **Three governing rules.** The *centrality gate* (the teapot must be the tenant,
  or the entry is `peripheral`); *split-vs-shift* (distinct phenomena sharing a
  name split into separate entries; one thread crossing registers stays one entry
  with an `ontology-shift` tag); the *primary-register tie-break* (ontology = where
  the teapot does its famous cultural work).
- **Typed links are referential/genealogical only** (`responds-to`, `alludes-to`,
  `parodies`, `mashes-up`, `namesake`, `see-also`). *Thematic* kinship lives in
  `tags` and is found by querying, never hard-wired as an edge.
- **Let vocabulary emerge from data.** Add a mode/facet/register only when a real
  entry needs it, and log the addition in the SCHEMA.md changelog.
- **Views are derived.** After any facet change, run `python build-views.py`;
  never hand-edit files under `views/`.

## Entry body scaffold (tiered)

Each entry body (below the frontmatter + hero image) follows a light scaffold:
1. **Lead** — one punchy sentence: what it is.
2. **Body** — provenance + the concrete detail + a **primary-source block quote**
   where one exists (public-domain quoted freely; in-copyright kept to a short
   fair-dealing snippet). Verify quotes and cite in `source:`.
3. **`## In the braid`** — its symbolic function and the typed threads to sibling
   entries (`[[links]]` + motifs).

Depth is **tiered by importance**:
- **Keystones** (~350–450w): thesis-bearing / most-quotable — russells, perrelets,
  http-418, utah, andersens, bunbuku, im-a-little-teapot, teapot-effect, chocolate,
  mad-tea-party. **(Done.)**
- **Mid** (~200–250w): most other entries, as the material warrants. *(pending)*
- **Minor** (~120–180w): landmarks / museums / design-objects — one good fact well
  told. *(pending)*

Production is a **research pipeline**: gather a dossier (primary source +
provenance + reception + link candidates), then author in the house voice
(warm-analytical, present tense, connects to the braid). Set `confidence` honestly.

## Open threads (backlog)

Durable capture of pending work and un-used research, so resuming needs no
session context.

**Entry bodies — remaining tiers** (scaffold + pipeline above; keystones done):
- **Mid (24)** ~200–250w: assassin-teapot, baillie-lines-to-a-teapot,
  blytons-talking-teapot, brass-teapot-film, brown-betty, cadogan-teapot,
  cezanne-still-life-with-teapot, gong-flying-teapot, james-hadley-teapot,
  marianne-brandt-teapot, moroccan-berrad, mrs-potts, orwell-nice-cup-of-tea,
  sagittarius-teapot, sky-kingdom, teapot-dome-station, teapot-emoji, teapot-rock,
  teapotting, tempest-in-a-teapot-idiom, tempest-in-a-teapot-play,
  turkish-caydanlik, wish-dragon, yixing-gongfu
- **Minor (6)** ~120–180w, one good fact: edenton-teapot, goddess-in-a-teapot,
  peter-shire-teapots, teapot-hill, teapot-house-lasqueti, trenton-teapot-museum
- **Peripheral (2)** keep brief: operation-cosmic-teapot, teapot-dome-scandal

**Optional keystone enrichments** (re-derivable via web; from dossiers not yet used):
- russells: the philosophical pushback (Garvey; van Inwagen; Plantinga's
  disanalogy) and the parody-deity lineage (Invisible Pink Unicorn → Flying
  Spaghetti Monster).
- utah: further Easter eggs (the "Pipes" screensaver pre-XP; `D3DXCreateTeapot`).
- chocolate-teapot: the idiom's 1967 first attestation (Word Histories) for a
  fuller etymology.
- im-a-little-teapot: the 1941 "inane novelty" line is **unverified** — confirm the
  Newsweek citation or drop it.

**Other**
- Gallery (`views/gallery.html`): add **mode** filtering (has ontology + title search).
- Turn `views/hypotheses.md` into thesis prose (the self-naming quartet;
  service-vs-refusal).
- **12 entries have no featured image** (see README "Curatorial pass") — decide:
  free generic substitutes / licensed images / generated fallback cards.

## Commit convention — the teapot table

Format: `type(scope): summary` — imperative mood, ~70 chars, a teapot verb for the
type. Scope is an entry slug, or `schema` / `views` / a pass name.

| type | meaning |
|---|---|
| **steep** | add a new entry (steep a new teapot into the mythos) |
| **stir** | refine or polish an existing entry (no factual change) |
| **mend** | fix a factual or citation error in an entry |
| **strain** | cut an entry, or demote it to the peripheral contrast set |
| **kintsugi** | rework the schema — a breaking change to a facet, mode, rule, or vocabulary (the vessel broken and gilded back together) |
| **pour** | regenerate or emit the `views/` |
| **infuse** | docs, notes, meta (this file, README prose) |
| **rinse** | chore: renames, restructuring, tooling, cleanup |

Two rules that keep the pot honest:
1. A **kintsugi** commit must also update the SCHEMA.md changelog, in the same commit.
2. **pour** the views in the same commit as the facet change that affects them, so
   the generated evidence never goes stale.

One logical change per commit; a themed pass that touches many files is a single
commit with a body list. An optional 🫖 may prefix the summary.

Examples (drawn from real history):
- `steep(cadogan-teapot): lidless puzzle vessel`
- `mend(edenton-teapot): Boston timing was reversed; +Baldwin 1905`
- `strain(yoko-teapot): generic retail SKU, fails the distinctiveness bar`
- `kintsugi(mode): add mechanism; log in changelog`
- `pour: regenerate views after completeness pass`
- `rinse: rename teapot-lore → mythos`
- `mend(perrelets-teapot): cite dissertation (2014); add Gardner argument`

A themed pass:

    steep(completeness): +9 teapots from the multi-modal sweep

    - wish-dragon, cadogan, brown-betty, moroccan-berrad, turkish-caydanlik,
      teapot-emoji, teapotting, orwell, baillie
    - kintsugi: +mechanism mode, +meme form, +morocco/turkey/australia
    - pour: views regenerated

## Working style
Propose and apply clearly-correct changes; surface genuine forks as decisions;
let categories emerge from real data rather than pre-inventing them. When a claim
enters the corpus, verify it and set `confidence` honestly (`verified` /
`needs-check`).
