# Building a One-Shot DM Wiki (Generic Guide)

This describes how "The Hollow Chorus" (Tabaxi) and "The Masks of Millbrook" (doppelganger) were built, so
you can produce another one-shot in the same format without starting from scratch on structure or design
philosophy. It's aimed at 3.5–4 hour, level 3–4, newb-friendly one-shots, but the shape generalizes to other
lengths and levels with minor scaling.

## 1. Answer These Before Writing Anything

A one-shot wiki falls into place quickly once these are settled. Spend most of your prep time here, not on
prose.

- **The threat.** What's actually wrong, and why is it not obviously evil? The strongest one-shots give the
  antagonist a sympathetic, comprehensible motive (Us'gath thought it was answering a prayer; the doppelganger
  cell just wanted somewhere to stop running). Pure malice is a weaker climax than "understandable, still
  wrong."
- **The Core Truth.** One paragraph the players should not know until deep into the session. Write it down
  explicitly and never contradict it in NPC dialogue before the reveal.
- **The trusted guide.** Who leads the party through the investigation, and is that person secretly the
  threat (or connected to it)? This is your emotional through-line — decide it early so every scene with them
  can be written to hold up on a second read.
- **The one NPC who's genuinely, unambiguously safe.** New tables spiral into paranoia fast if literally
  everyone might be lying. Plant at least one NPC (a priest, an elder, a child) who is never a suspect, so
  players have somewhere to rest.
- **The mercy option.** Which minor antagonist(s) can be spared instead of killed, and what does sparing them
  change? Doesn't have to be complex — "they surrender and it matters" is enough.
- **What gets found, not fought.** At least one handout/journal/mural that reveals backstory through an
  object rather than a monologue (Maren's ledger, the ritual mural).

## 2. The Session Shape (5 Acts)

| Act | Length (of ~210–225 min) | Function |
|---|---|---|
| 1 — The Hook | ~10 min | Get hired. Make the job sound easy to dismiss, so it's believable nobody's solved it yet. |
| 2 — Meet the Cast | ~35 min | Establish tone as *good* before anything's wrong. Plant 2–4 small "cracks" the players can notice or miss. Introduce the trusted guide here, warmly. |
| 3 — Pulling Threads | ~70–75 min | The investigation proper, plus **one mundane, non-plot-related fight** (see §4) as a red herring / combat palate cleanser. End with a real lead to the antagonist's lair. |
| 4 — The Lair | ~40 min | Traps, captives/victims, and the unmasking of the trusted guide. This is where dread should peak. |
| 5 — Climax & Resolution | ~55–65 min | Boss fight with a monologue, a mercy option if applicable, and an epilogue that resolves victims' fates and seeds a sequel. |

Adjust proportions for a shorter or longer slot, but keep the *ratio* — Acts 3 and 5 are the two that can
flex, Acts 1 and 2 should stay tight so you don't burn your runway before anything happens.

## 3. Wiki Sections (Nav Structure)

Mirror this section order — it's what makes the wiki fast to navigate mid-session:

1. **Orientation** — Overview & Core Truth, Session Timeline
2. **The Story** — one entry per Act, in order
3. **People** — one profile per named NPC, each tagged `Real` / `[Threat type]` in a DM-only badge, cross-linked
   from wherever they're first mentioned in the Acts
4. **Bestiary** — one stat block per unique monster/NPC combatant, grouped by which Act they appear in, with a
   `.scaling` note under each for adjusting difficulty live
5. **Locale Extras** — a locations table + a short list of "ordinary" background NPCs who exist purely for
   texture and to prove not everyone is a suspect
6. **Reference** — Clues & Handouts, Skill Checks by Locale, Loot & Rewards, DM Tips

Every NPC, monster, and clue should be a named anchor (`id="npc-x"`, `id="monster-x"`, `id="act3-detour"`, etc.)
and cross-linked with `<a href="#...">` wherever it's mentioned elsewhere in the document. This is what makes
the wiki actually usable at the table instead of just a linear document — you should be able to click from
"Act 4 mentions Fenwick" straight to his People entry without scrolling.

## 4. Design Principles That Made These Work

- **Deliver tells through roleplay, not dice.** Reserve skill checks for players who actively push further; the
  base "something's off" beats should land through narration so no one gets locked out by a bad roll.
- **Spend your biggest reveal exactly once.** If your antagonist type has a signature "gotcha" (a doppelganger
  reverting to true form, a construct's disguise cracking, a possession snapping), make sure it happens on-screen
  only at the climax. If lesser versions of the same threat show up earlier, have them flee or get captured
  rather than die where players can see the reveal repeated — repetition kills the impact.
- **Include one fight that has nothing to do with the plot.** A short, mundane combat (bandits, wild animals,
  a bar brawl) gives newer players low-stakes practice with the rules and breaks up roleplay-heavy stretches,
  without asking them to parse Plot Significance while also learning to use their sheet. Good place for it: a
  red herring lead that the trusted guide deliberately points the party toward, which then turns out to be a
  genuine dead end.
- **Write the villain a monologue that's aggrieved, not gloating.** The most effective version believes it did
  nothing wrong, or did the least-bad thing available to it. Deliver it in pieces across the fight (on reveal,
  at half HP, near death) rather than all at once.
- **Give the villain one thing it can't explain away.** A single innocent casualty it didn't choose or
  couldn't prevent (Willa, in Millbrook) keeps the sympathetic take from tipping into "actually just right" —
  it should regret this one specifically, not perform generic villain guilt.
- **Handouts carry backstory better than exposition.** A journal, mural, or ledger the party finds and reads
  themselves lands harder than an NPC explaining the same facts out loud. Write 3–5 short entries/passages, not
  a wall of lore.
- **Protect the one safe NPC.** Never let them be a suspect, even briefly, or the "somewhere to rest" function
  breaks.
- **Add a mercy option for at least one minor antagonist.** Gives players a real choice besides "fight until
  everything's dead," and reinforces that this threat is made of individuals, not a monolith.
- **Cap the encounter math.** Use the DMG's medium/hard/deadly XP thresholds per party size and level as a
  sanity check for the final fight, then explicitly write a `.scaling` note telling yourself how to knock it
  down live if the table is struggling. Newb tables should walk away from the climax feeling powerful, not
  ground down.

## 5. Skill Checks by Locale (Reference Table Pattern)

Build this table last, after the Acts are written — walk through the document top to bottom and log every
check that could plausibly come up, in the order the party would encounter them. Columns: **Where / Check /
DC / What It Reveals or Does**. Note explicitly, in the table's intro line, that most narrative beats shouldn't
require a roll at all — this table is a reference for the checks players *choose* to make, not a checklist you
force on them.

## 6. HTML Template Notes

Both wikis share one CSS skeleton — reuse it directly rather than rebuilding:

- Sticky left-hand nav, grouped by the six sections in §3, each link an in-page anchor.
- A light parchment palette (`:root { color-scheme: light }`, warm background, dark ink text) — keep it
  print-friendly (`@media print { nav { display:none } }`).
- Reusable boxed callout classes: `.readaloud` (read-aloud text, tan/gold border), `.tell` (green-tinted,
  for discoverable clues), `.secret` (red-tinted, DM-only info), `.riff` (dashed border, DM riffing notes),
  `.monologue` (villain speech), `.statblock` (bordered stat block card with a `.chiprow` for AC/HP/Speed and
  a `.cr` pill badge for challenge rating).
- `.badge.real` / `.badge.fake` (or reskin the second class name per threat type) for the DM-only status tag
  in the People table and profiles.

Copy `masks_of_millbrook.html` as a starting scaffold for the next one: strip the Millbrook-specific content
section by section, keep the CSS and nav skeleton, and rebuild from §1 of this guide.

## 7. Build Order (Recommended)

1. Answer §1 (premise, Core Truth, trusted guide, safe NPC, mercy option, key handout).
2. Draft the Act-by-act beat outline as plain bullet points — no prose yet.
3. Write Acts 1–5 in full, including read-aloud boxes and DM riffing notes, cross-linking to People/Bestiary
   anchors as you introduce each NPC/monster (even before those sections exist — you'll fill the links in
   next).
4. Write full People profiles and Bestiary stat blocks for everything you referenced.
5. Write Locale Extras (locations table + ordinary NPCs).
6. Write Reference last: Clues & Handouts, then the Skill Checks by Locale table (walk the document top to
   bottom), then Loot & Rewards, then a DM Tips list summarizing anything you had to explain twice while
   writing.
7. Sanity-check every `id=` has a matching `href="#..."` and vice versa before calling it done.

## 8. Pregenerated Character Sheets

The `pregenned-characters/` directory contains a full set of level 3 one-shot characters, one per PHB class. Use them when players arrive without a character or want to jump straight into play.

### File Structure

```
pregenned-characters/
  index.html          ← landing page with card grid (link here from your one-shot wiki)
  barbarian.html      ← Grimtusk Ironskin (Half-Orc, Berserker, Outlander)
  bard.html           ← Lyria Ashveil (Half-Elf, Lore, Entertainer)
  cleric.html         ← Brother Aldric (Human Variant, Life, Acolyte)
  druid.html          ← Sylvara Thornwood (Wood Elf, Circle of Moon, Hermit)
  fighter.html        ← Cade Stormwall (Human Variant, Champion, Soldier)
  monk.html           ← Wei Sunstep (Human Variant, Open Hand, Outlander)
  paladin.html        ← Ser Iona Brightshield (Human Variant, Devotion, Noble)
  ranger.html         ← Ash Coldwind (Wood Elf, Hunter/Colossus Slayer, Outlander)
  rogue.html          ← Pip Tumblewhistle (Lightfoot Halfling, Thief, Criminal)
  sorcerer.html       ← Zara Emberveil (Tiefling, Wild Magic, Sage)
  warlock.html        ← Dorian Ashcroft (Human Variant, Fiend/Chain, Sailor)
  wizard.html         ← Mira Starcroft (High Elf, Evocation, Sage)
  portraits/          ← 600×900 px PNGs, one per class (CC-BY 4.0, Joseph Hewitt)
```

### Stat Generation Rules

All characters were built on the **standard array** (15, 14, 13, 12, 10, 8), assigned to maximize the class's primary ability. Racial bonuses applied on top. Proficiency bonus +2. All stats are at level 3 with no magic items.

| Thing | Choices made |
|---|---|
| Standard array | 15/14/13/12/10/8 — gives a fair, balanced character without requiring a backstory justify |
| Variant Human feat | Taken for Fighter (Tough), Monk (Mobile), Cleric (War Caster), Paladin (War Caster), Warlock (War Caster) — feats that complement the class without requiring system knowledge to use |
| HP | Max at level 1, average-rounded-up for levels 2–3, plus CON modifier per level |
| AC | Best armor the class can wear without penalty, plus shield where it fits the fantasy |
| Subclasses | Chosen for playability over optimization: Champion (Fighter), Open Hand (Monk), Life (Cleric), Circle of Moon (Druid), Lore (Bard), Fiend/Chain (Warlock), Hunter/Colossus Slayer (Ranger), Thief (Rogue), Wild Magic (Sorcerer), Devotion (Paladin), Berserker (Barbarian), Evocation (Wizard) |

### Sheet Template (CSS Classes)

Each sheet shares the same CSS skeleton as the one-shot wikis (warm parchment palette, sticky left nav with `.active` on current sheet, `@media print` hides nav). Additional classes unique to character sheets:

- `.quickstats` — row of chips (HP, AC, Speed, Initiative, etc.)
- `.ability-box` — 6-column grid for STR/DEX/CON/INT/WIS/CHA with score, modifier, and label
- `.sheet-grid` — two-column layout (saves/skills left, attacks/equipment right)
- `.prof-list` — save and skill list; `.prof` subclass adds filled bullet ●; expertise uses ◆ prefix in `fdesc` text
- `table.atk` — attacks table (weapon, to-hit, damage, notes)
- `.sslot` — spell slot chip (level + count)
- `.spell-list` — spell list with `.slvl` pill per entry
- `.statblock` — embedded NPC/beast stat block (e.g., Wild Shape forms, familiars)
- `.quirk` — purple dashed-border box for the once-per-long-rest character quirk
- `.portrait` — float-right character portrait (155px wide in browser, 110px in print)
- `.personality` — 2-column grid for trait/ideal/bond/flaw

### The Character Quirk

Each character has a once-per-long-rest ability in a `.quirk` box — silly, useful, and not game-breaking. These exist to give new players a personal moment that's entirely theirs, distinct from class mechanics. Design guidelines:

- **Thematically tied** to the character's background or personality, not just the class
- **One sentence activation** — players should be able to trigger it without reading rules
- **Doesn't require a slot or resource other than the per-long-rest limit**
- **Should prompt a table moment** — laughter, a groan, or at minimum someone leaning over to read it

Current quirks: Primal Nose (Barbarian), Earworm (Bard), Mild Prophecy (Cleric), Local Gossip (Druid), Not Today (Fighter), Flying Entrance (Monk), Inspiring Speech (Paladin), I Know a Shortcut (Ranger), Oh This Old Thing (Rogue), Controlled Misfire (Sorcerer), The Imp Knows Things (Warlock), Excessive Footnote (Wizard).

### Portraits

Portraits are sourced from **Joseph Hewitt's Fantasy RPG Portrait Set 1** (opengameart.org, CC-BY 4.0). Each sheet links to `portraits/CLASSNAME.png` (relative path) and includes a footer attribution line. To replace a portrait: drop a new PNG at `portraits/CLASSNAME.png` — no other change needed.

**Portrait source:** https://opengameart.org/content/joseph-hewitts-fantasy-rpg-portrait-set-1  
**License:** CC-BY 4.0 — attribution required: *"Fantasy portraits by Joseph Hewitt (pyrrho12@yahoo.ca)"*

### Adding a New Pregen

1. Copy any existing sheet as a starting point.
2. Update the `<title>`, `<h1>`, `.char-sub`, and `.char-flavor` for the new character.
3. Update the `.active` class in `<nav>` to point at the new file (or add a new nav entry if it's a new class).
4. Fill in stats using the standard array and the class's primary ability priority.
5. Add a `portraits/CLASSNAME.png` — 600×900 px looks best, portrait orientation.
6. Add a `.quirk` box — one sentence to trigger, personal to the character, mildly absurd.
7. Link the new sheet from `index.html` as a card in the appropriate section.
