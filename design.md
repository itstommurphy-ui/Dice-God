# Dice God — Devlog
from pathlib import Path

content = """# Dice God — Design Document

> **Working title:** Dice God  
> **Core fantasy:** Sit at the table where fate is decided. Roll imperfect information, manipulate the result, and build increasingly impossible dice.  
> **Core identity:** The player's build lives primarily on the six faces of their dice.

---

## 1. High Concept

**Dice God** is a minimalist roguelike dice-builder built around the physical and visual appeal of dice.

The player sits at a simple table with a cup and a small pool of dice. Each round presents a rising Fate target that must be beaten over a limited number of casts.

The game is not purely luck-driven. A roll gives the player a puzzle rather than a verdict. The player can hold dice, reroll them, physically nudge them onto adjacent faces, arrange their resolution order, and build powerful synergies by modifying the dice themselves.

Over the course of a run, ordinary dice become strange, specialised artefacts. Individual faces can be replaced, engraved, duplicated, cursed, weighted, swapped, broken, empowered, or given conditional effects.

The game should feel immediately understandable but become increasingly complex through interaction and synergy.

---

## 2. Design Pillars

### 2.1 Dice Are the Star

The dice themselves are the primary game pieces, progression objects, collectibles, and visual focus.

The game should avoid surrounding the dice with too many secondary systems.

If a mechanic can live directly on a die or one of its faces, that is usually preferable to creating a separate passive item.

---

### 2.2 Chance Creates the Puzzle; Skill Solves It

The player must never feel that success or failure is determined entirely by the initial roll.

Randomness creates tension, but the player should have meaningful ways to manipulate and exploit the result.

A bad roll should frequently produce:

> “Hang on…”

rather than:

> “Well, that run is dead.”

Player skill should come from:

- knowing what to hold;
- deciding what to reroll;
- choosing when and where to Nudge;
- arranging dice in the best resolution order;
- building dice with complementary faces;
- understanding adjacency and opposite-face relationships;
- choosing upgrades that create strong synergies;
- knowing when to pursue consistency versus explosive scoring.

---

### 2.3 The Build Lives on the Dice

The game should resist becoming “Balatro with dice.”

There should not be six passive Joker-equivalent slots doing most of the interesting work.

The majority of a build should be physically visible on the dice.

A screenshot of a strong run should make another player think:

> “What have you done to that die?”

The dice should visually communicate the build.

---

### 2.4 Minimal Art, Maximum Polish

The game should be visually restrained.

Primary visual elements:

- a simple table;
- a dice cup;
- the player's dice;
- score / Fate target;
- small UI elements;
- occasional trays, tools, cards, seals, or objects placed onto the table.

The game should not require:

- character animation;
- world maps;
- enemy sprites;
- population simulation;
- environmental scenes;
- large numbers of bespoke backgrounds.

The art budget should be concentrated on making the dice, their movement, sound, faces, materials, and upgrades extremely satisfying.

---

### 2.5 Discovery Is a Major Reward

A major long-term appeal should be discovering:

- new dice types;
- new face types;
- new engravings;
- new materials and themes;
- unusual pip styles;
- rare combinations;
- new rules and modifiers.

The collection should feel tangible.

Outside runs, discovered dice and visual sets should be displayed in a **Dice Cabinet** or equivalent collection screen.

---

## 3. Tone and Theme

The player is effectively a god, fate-maker, or cosmic administrator.

However, the world should mostly exist through implication.

The player does not watch armies march or villages grow. Instead, they sit at the table where those outcomes are decided.

Examples of flavour text:

> **THE THIRD CASTING**  
> A kingdom waits for rain.

> **THE FIFTH JUDGEMENT**  
> Three houses have gone to war.

> **THE GREAT DECREE**  
> The dead ask to be remembered.

The table is the point where fate is determined.

The theme should make small dice feel disproportionately powerful.

The contrast is important:

**tiny, tactile objects controlling enormous unseen consequences.**

---

## 4. Core Game Loop

A basic round should look something like this:

1. A **Fate target** is presented.
2. The player has a limited number of casts to reach the target.
3. The player shakes the dice cup.
4. The player throws their dice.
5. The player evaluates the result.
6. They may hold certain dice.
7. They may reroll others.
8. They may use limited manipulation abilities such as **Nudge**.
9. Before scoring, the player may arrange the dice into a chosen order.
10. Dice resolve from left to right.
11. Numbers and face effects combine into the final score.
12. If the Fate target is met, the player receives a reward or upgrade opportunity.
13. The next Judgement increases in difficulty or introduces a rule modifier.

The core game should be extremely fast to understand.

The complexity should emerge from the player's dice rather than from complicated base rules.

---

## 5. The Dice Cup

The cup is an important sensory element.

The player should be able to shake the dice before throwing them.

This does **not** need to meaningfully affect randomness.

Its purpose is tactile pleasure.

Important sensory details:

- dice rattling inside the cup;
- subtle vibration / controller rumble / mobile haptics;
- individual material sounds;
- a satisfying throw;
- dice colliding with each other;
- dice bouncing against the table;
- the brief moment where the final die settles.

The anticipation between throw and result is already inherently satisfying and should be celebrated rather than rushed.

---

## 6. Player Agency

The player should have several ways to influence fate.

### 6.1 Hold

A die can be kept between casts.

Held dice do not reroll.

---

### 6.2 Reroll

Unheld dice return to the cup and are cast again.

Rerolls are limited by the number of casts available in the round.

---

### 6.3 Nudge

**Nudge is a core signature mechanic.**

The player can physically tip a die onto one of its four adjacent faces.

This means the geometry of the cube matters.

A rolled face cannot simply become any other face.

The player may only access a face that is physically adjacent unless another effect allows otherwise.

Nudges should be a limited resource so that choosing when to use one matters.

Potential upgrade interactions:

- additional Nudges;
- cheaper Nudges;
- free Nudges on certain faces;
- Nudging multiple dice;
- allowing a die to flip directly to its opposite face;
- triggering effects when a die is Nudged;
- making certain faces inaccessible through Nudge.

---

### 6.4 Arrange

After the final cast, the player chooses the left-to-right resolution order.

This allows dice to interact with their neighbours.

A die might:

- multiply the next die;
- copy the previous die;
- sacrifice a neighbouring die;
- increase adjacent dice;
- trigger again if beside a certain symbol;
- modify only dice appearing later in the chain.

The same rolled values can therefore produce very different results depending on arrangement.

---

## 7. Why Physical Dice Geometry Matters

A standard die is not simply six independent outcomes.

It has:

- six faces;
- four adjacent faces for each face;
- three opposite-face pairs.

For a conventional die:

- 1 is opposite 6;
- 2 is opposite 5;
- 3 is opposite 4.

The game should use these relationships mechanically.

This creates strategy that is uniquely suited to dice.

Examples:

- a face may empower its opposite;
- a face may copy one adjacent face;
- a Nudge can only access adjacent faces;
- an effect may flip directly to the opposite face;
- a cursed face can deliberately be placed opposite a powerful face;
- certain engravings may affect all four neighbouring faces;
- players may rearrange face positions during upgrades.

The physical structure of the cube should matter enough that the game could not simply be reskinned with cards.

---

## 8. Dice Anatomy

A die can potentially have several layers.

### 8.1 Base Die / Mould

Defines the fundamental face distribution and special properties.

Examples:

**Standard**  
1 / 2 / 3 / 4 / 5 / 6

**Loaded**  
1 / 2 / 3 / 6 / 6 / 6

**Balanced**  
3 / 3 / 3 / 4 / 4 / 4

**Wild**  
1 / 1 / 2 / 5 / 6 / ?

**Hollow**  
Includes a blank face that copies another die.

**Saint**  
Low raw values but unusually powerful face effects.

**Glutton**  
Can consume another die during a run and steal one of its faces.

---

### 8.2 Face Value

The numerical value of a face.

This may be conventional or unusual.

Possible values include:

- 0;
- repeated values;
- values above 6;
- blanks;
- wild values;
- symbols instead of numbers.

---

### 8.3 Engraving / Face Effect

An individual face can have a special behaviour.

Example notation:

- 1★
- 3☽
- 6🔥

The effect only matters when that specific face is active.

---

### 8.4 Material / Theme

The physical appearance of the die.

Potential materials:

- ivory;
- bone;
- brass;
- obsidian;
- marble;
- wood;
- cheap plastic;
- translucent acrylic;
- mother-of-pearl;
- neon plastic;
- old pub dice;
- children's board-game dice.

Materials can primarily be cosmetic, although rare dice moulds may combine appearance and mechanics.

---

### 8.5 Pip / Face Style

Individual dice or even individual faces can use distinctive markings.

Examples:

- traditional pips;
- Roman numerals;
- stars;
- eyes;
- moons;
- hand-painted numbers;
- scratched tally marks;
- symbols;
- carved runes.

Some themes could deliberately make every face look different.

---

## 9. Face Effects

Face effects should provide much of the game's combinatorial depth.

Example concepts:

### Echo
Copies the previous die.

### Crown
Sacrifice this die to double the next die.

### Anchor
Cannot be rerolled, but scores at increased strength.

### Mirror
Uses the value or property of the opposite face.

### Hunger
Destroy the next die and gain a multiple of its value.

### Halo
Both adjacent dice gain a bonus.

### Snake Eyes
If another 1 is present, both transform or score as 6s.

### Decay
Starts with a large bonus but weakens every time it is rolled.

### Memory
Scores whatever this die rolled on the previous cast.

### Martyr
Scores nothing but permanently improves another face.

### Sixth Sense
Triggers a large multiplier after a specified number of 6s have been rolled.

### Cracked
Very powerful, but the face eventually breaks after repeated activations.

### Magnet
Allows the die to flip directly to its opposite face.

### Chain
Gains strength for every matching symbol earlier in the resolution order.

### Parasite
Attaches to a neighbouring face and steals part of its value.

### Mercy
If the roll would otherwise fail, provides a limited rescue effect.

The exact effect pool can become extremely large over development.

---

## 10. Building Dice During a Run

The player should gradually mutate their dice.

Potential upgrade actions:

- replace a face;
- engrave a face;
- duplicate a face;
- increase a face value;
- decrease a face value in exchange for another benefit;
- swap two face positions;
- move an engraving;
- permanently weight a face;
- curse a face;
- bless a face;
- crack a face;
- repair a face;
- fuse two effects;
- copy a face from another die;
- destroy a die;
- add a die;
- remove a die from the cup;
- transform the base mould.

These choices create the player's build.

The aim is not simply to acquire higher numbers.

The aim is to create **synergistic dice**.

---

## 11. Example Build

A player's five dice might eventually contain something like:

### Die A — Loaded Brass
1 / 2 / 3 / 6 / 6 / 6🔥

The fire 6 doubles if another 6 resolved immediately before it.

### Die B — Hollow Marble
Blank / 2 / 3 / 4 / 5 / 6

The blank copies the previous die.

### Die C — Saint
1★ / 1 / 2 / 2 / 3 / 3

The star face doubles both adjacent dice.

### Die D — Glutton
1 / 2 / 3 / 4 / 5 / Hunger

Hunger destroys the next die in the chain and scores triple its value.

### Die E — Cracked Obsidian
1 / 2 / 3 / 4 / 5 / 12

The 12-face breaks permanently after its third activation.

A successful roll becomes an optimisation problem rather than a simple sum.

---

## 12. Scoring Philosophy

The exact scoring system needs prototyping.

However, it should satisfy several principles:

1. **Base scoring must be understandable immediately.**
2. **Face effects should create most of the complexity.**
3. **Order of resolution must matter.**
4. **Players should be able to predict outcomes before confirming.**
5. **Very strong builds should be capable of absurd score explosions.**
6. **Consistency builds and high-variance builds should both be viable.**

Possible basic structure:

**Final Fate = base face values + triggered additions × multipliers**

The player should see a clear preview of the expected resolution before locking it in.

The game should avoid becoming an opaque spreadsheet.

---

## 13. Judgements

Instead of enemies, the player faces escalating **Judgements**.

Each Judgement requires a specific amount of Fate.

Example:

### Age I

**Judgement I**  
80 Fate

**Judgement II**  
130 Fate

**Judgement III**  
190 Fate

**Great Decree**  
280 Fate + special rule

Targets rise over the course of a run.

This retains the clarity of an escalating score challenge without requiring combat.

---

## 14. Great Decrees

Major rounds introduce temporary rule changes.

These act as build checks and force adaptation.

Examples:

### The Law of Silence
Engraved 6-faces do not activate.

### The Law of Equality
No die may score more than twice the value of another die.

### The Law of Gravity
Nudging costs twice as much.

### No Miracles
Rerolled dice cannot produce 6.

### The Law of Sacrifice
The highest-scoring die is destroyed after resolution.

### The Law of Reversal
Dice resolve right to left.

### The Law of Three
Only the first three dice in the chain can score normally.

### The Law of Memory
Repeated face values weaken each time they appear.

Great Decrees should disrupt strategies without arbitrarily deleting entire builds.

The best ones make the player reconsider how to use their existing tools.

---

## 15. Run Structure

Target run length:

**20–60 minutes**

Likely median:

**30–40 minutes**

Potential structure:

### 3 Ages

Each Age contains:

- 3 normal Judgements;
- 1 Great Decree.

Total:

**12 scoring rounds**

Between rounds, the player receives rewards or upgrade opportunities.

After each Age, the player enters a larger **Workshop** phase.

A straightforward player can complete a run quickly.

Players who spend time inspecting their dice and optimising upgrades can take longer.

---

## 16. Rewards Between Judgements

Reward screens should not all feel identical.

Possible rewards:

- choose one of three new dice;
- choose one of three engravings;
- replace one face;
- duplicate one face;
- swap two faces;
- modify die geometry;
- improve a face value;
- remove a die;
- repair a damaged face;
- gain an unusual one-use intervention;
- unlock a rare material;
- transform an existing die mould.

Choices should regularly force trade-offs.

The most exciting reward is not always the objectively strongest item. It may be the item that completes a synergy.

---

## 17. Workshop

The Workshop is where more invasive changes occur.

Visually, the game should not move to a giant new environment.

Instead, a small tray or toolset is placed onto the table.

Possible Workshop actions:

- engrave;
- replace;
- polish;
- crack;
- fuse;
- swap;
- weight;
- rotate face positions;
- transfer a face;
- dismantle a die.

The Workshop should reinforce the physicality of modifying an object.

---

## 18. Global Upgrades

Global upgrades may exist, but they should be secondary.

The game should avoid having a separate passive system become more important than the dice.

A useful target:

**80–90% of meaningful build identity should live on the dice themselves.**

Global upgrades can change rules such as:

- +1 Nudge per Judgement;
- held dice gain a bonus;
- the first reroll each round is free;
- cracked faces last longer;
- doubles create a small bonus;
- the first die in the chain gains a property.

These should support the dice rather than overshadow them.

---

## 19. Collection and Discovery

Long-term discovery is a central retention mechanic.

The player should gradually fill a **Dice Cabinet**.

Potential collection categories:

### Dice Moulds
New mechanical die types.

### Engravings
New face effects.

### Materials
Visual themes.

### Pip Sets
Alternative markings.

### Rare Faces
Special numbers, symbols, or wild faces.

### Decrees
New challenge rules.

### Curiosities
Unusual one-off discoveries or secret interactions.

Unlocks should encourage experimentation rather than simply provide permanent power.

---

## 20. The Dice Cabinet

The collection screen should feel physical and satisfying.

Possible presentation:

- wooden cabinet;
- velvet-lined drawers;
- individual dice slots;
- undiscovered silhouettes;
- rotating dice previews;
- completion percentages by collection type.

Players should be able to inspect a discovered die and rotate it freely.

A collection entry could show:

- name;
- mould;
- material;
- face layout;
- description;
- date first discovered;
- best run using it;
- discovered variants.

The collection itself should become a reason to keep playing.

---

## 21. Visual Direction

The visual style should be minimalist, tactile, and highly readable.

Potential scene:

- dark green or near-black felt;
- subtle wood or dark table edge;
- one attractive dice cup;
- small brass or wooden UI elements;
- focused lighting;
- very little background clutter.

The dice should receive the majority of visual attention.

Visual upgrades need to be legible at a glance.

A die may accumulate:

- scratches;
- gold inlays;
- cracks;
- glowing symbols;
- engravings;
- stains;
- paint;
- metal edging;
- wax seals;
- embedded gems;
- chipped corners.

The final build should look visibly transformed from the original dice.

---

## 22. Animation and Sensory Design

Small interactions need to feel excellent.

Key moments:

### Shaking
Dice audibly rattle inside the cup.

### Throwing
Dice bounce, collide, and roll naturally.

### Settling
The final half-second before a die stops should preserve suspense.

### Holding
Held dice should visibly separate or lock into place.

### Nudging
The player physically tips the die onto another face.

### Engraving
A face is stamped, carved, burned, or etched.

### Replacing a Face
The old face is physically removed or transformed.

### Destroying a Die
The die cracks or shatters.

### Acquiring a Die
A new die is dropped into the cup.

### Huge Scoring Chains
Resolution should build in intensity through sound and animation without becoming visually unreadable.

---

## 23. Sound Direction

Sound is extremely important because the game is tactile and visually minimal.

Important sounds:

- dice rattling in the cup;
- different materials colliding;
- dice rolling across felt;
- subtle impacts;
- a die settling;
- engravings activating;
- multipliers escalating;
- cracks forming;
- dice shattering;
- workshop tools;
- distant thematic ambience.

Different materials could subtly produce different sounds.

For example:

- bone feels dry and hard;
- brass is metallic;
- wood is softer;
- acrylic is sharp and plastic;
- stone is heavy.

This could make cosmetic collections feel more meaningful without giving them mechanical power.

---

## 24. Worldbuilding Through Implication

The game should make the outside world feel enormous without showing it.

Possible techniques:

- short flavour text before Judgements;
- distant thunder after rain-related outcomes;
- a muffled crowd after a huge success;
- bells;
- wind;
- chanting;
- distant battle;
- candles reacting to events;
- changes in ambient sound.

The result of the dice matters enormously, but the player never leaves the table.

This helps the game feel larger than its art requirements.

---

## 25. Difficulty and Skill Ceiling

Difficulty should come from several sources:

- higher Fate targets;
- fewer casts;
- stricter Decrees;
- limited Nudges;
- increasingly complex trade-offs;
- dice damage or instability;
- build consistency requirements.

Higher difficulties should ideally make the game demand stronger understanding rather than simply inflating numbers.

Potential advanced difficulty rules:

- fewer rerolls;
- more severe Great Decrees;
- cracked dice appear more often;
- certain face modifications become more expensive;
- more demanding scoring targets;
- permanent consequences for certain failed Judgements.

---

## 26. Failure

A run ends when the player fails to satisfy a required Judgement.

Failure should feel clean and quick.

The player returns to the Cabinet with:

- newly discovered entries;
- collection progress;
- run statistics;
- notable synergies;
- perhaps a seed or run code.

There should not be a long punishment sequence.

The desire should be:

> “I want another run because I know how I could build that better.”

---

## 27. Run Variety

Runs should differ because of:

- available dice moulds;
- face upgrade offerings;
- materials;
- Decrees;
- face geometry;
- rare upgrades;
- player decisions;
- emergent synergies.

The game should avoid relying purely on random numerical variation.

The player should feel like they are constructing a different machine each time.

---

## 28. Example Early Run

### Start

Five Standard Dice:

1 / 2 / 3 / 4 / 5 / 6

The player has:

- 3 casts per Judgement;
- 1 Nudge per Judgement.

### Judgement I

Target: 80 Fate.

The player learns:

- shaking;
- throwing;
- holding;
- rerolling;
- arranging.

### Reward

Choose one:

- Crown engraving;
- Echo engraving;
- +1 value to any face.

The player chooses Echo and places it on Die 2's 1-face.

### Judgement II

A 1 now has strategic value.

The player deliberately keeps a low roll because Echo can copy the powerful die before it.

This demonstrates the core lesson:

**numbers are not inherently good or bad once the dice are modified.**

### Reward

Choose one:

- Loaded Die;
- swap two faces on any die;
- add a Halo engraving.

The build begins to develop an identity.

---

## 29. Example High-Level Run

Late in a run, the player rolls:

6🔥 / 1★ / Blank / 4 / Hunger

Instead of simply adding the values, the player must decide:

- whether to Nudge the 4;
- whether the Blank should copy the fire 6;
- where the star should sit;
- which die Hunger should consume;
- whether sacrificing a powerful die creates a larger total;
- whether a future Great Decree makes preserving a certain die more important than maximising this round.

The game has evolved from a simple dice roll into a compact optimisation puzzle.

---

## 30. Anti-Balatro Guardrails

Balatro is an inspiration in terms of clarity, run structure, discovery, escalating targets, and synergy.

The game should not simply reproduce its structure with dice.

Key guardrails:

### Do Not Build Around Poker-Like Dice Hands

Avoid making the central scoring system:

- pairs;
- straights;
- full houses;
- five-of-a-kind;
- Yahtzee-style combinations.

These can perhaps appear occasionally, but they should not define the game.

---

### Do Not Make Passive Items the Main Build

No primary equivalent of a Joker row.

The dice themselves should contain the build.

---

### Make Physical Geometry Matter

Adjacency, opposite faces, Nudging, and face layout should be important.

This is one of the game's strongest unique mechanics.

---

### Make Modification Visual

Players should physically see what has happened to their dice.

The build is not just a list of modifiers.

---

### Let Arrangement Matter

Dice resolving in sequence provides a layer of active optimisation that distinguishes the game from simply rolling combinations.

---

## 31. Things the Game Should Not Become

Avoid scope drift into:

- civilisation management;
- population simulation;
- tactical combat;
- dungeon crawling;
- board-game movement;
- character collecting;
- large narrative RPG systems;
- complex world maps;
- large inventory grids;
- a card game disguised as dice.

The table, the cup, and the dice should remain enough.

---

## 32. Prototype Priorities

The first prototype should answer whether the core loop is fun before any major content work begins.

### Prototype 1 — Basic Roll

Implement:

- five dice;
- dice cup;
- shake;
- throw;
- three casts;
- hold;
- reroll;
- Fate target.

Test whether simply interacting with the dice feels satisfying.

---

### Prototype 2 — Nudge

Add:

- physical face orientation;
- adjacency;
- one Nudge per round.

This is a crucial test.

If Nudge feels annoying or irrelevant, the design needs revision.

If it creates interesting decisions, it may become the game's defining mechanic.

---

### Prototype 3 — Arrange and Resolve

Add left-to-right arrangement.

Create 6–10 simple face effects such as:

- Echo;
- Crown;
- Halo;
- Mirror;
- Hunger.

Test whether arranging a roll creates meaningful puzzles.

---

### Prototype 4 — Face Modification

Allow the player to alter individual faces between Judgements.

Test whether players begin thinking of the dice as objects they are building rather than disposable random-number generators.

---

### Prototype 5 — Short Run

Create:

- one Age;
- three Judgements;
- one Great Decree;
- a small reward pool.

Target a 10–15 minute prototype run.

Only after this works should the game expand toward full 20–60 minute runs.

---

## 33. Prototype Questions

Important questions to answer early:

1. Is rolling satisfying enough to repeat hundreds of times?
2. Does Nudge create real decisions?
3. Does face geometry matter without becoming tedious?
4. Is arranging dice interesting every round?
5. Can players understand why a scoring chain happened?
6. Are modified low-number faces sometimes desirable?
7. Can multiple genuinely different build archetypes emerge?
8. Do players feel responsible for success despite randomness?
9. Do players become attached to individual dice?
10. Does discovering a new die or face effect feel exciting?
11. Does the game remain readable when synergies become extreme?
12. Does the minimalist table setting remain visually interesting for an entire run?

---

## 34. Potential Build Archetypes

These should emerge from systems rather than be rigid classes.

### Sixes
Build around producing and multiplying 6s.

### Ones
Turn traditionally weak rolls into powerful chain starters.

### Echo
Copy a small number of extremely powerful dice.

### Sacrifice
Destroy dice during resolution for huge temporary gains.

### Stable
Minimise variance and reliably meet every target.

### Chaos
Use wild faces, rerolls, and unpredictable high multipliers.

### Nudge
Build dice whose strongest faces are easily reachable through physical manipulation.

### Opposites
Exploit interactions between opposite faces.

### Adjacency
Build chains around neighbouring die effects.

### Cracked
Use fragile, extremely powerful faces and manage their lifespan.

### Memory
Build around previous casts and repeated sequences.

---

## 35. Possible Terminology

These are working terms and can change.

| Concept | Working Term |
|---|---|
| Score | Fate |
| Round | Judgement |
| Major round | Great Decree |
| Stage grouping | Age |
| Dice throw | Cast |
| Physical face adjustment | Nudge |
| Face effect | Engraving |
| Upgrade area | Workshop |
| Collection screen | Dice Cabinet |
| Passive resource | Will |
| Base die type | Mould |

The language should feel slightly ritualistic without becoming overly serious or fantasy-heavy.

---

## 36. Commercial / Production Strengths

The concept has several useful production advantages.

### Small Art Surface

The game does not require large environments or character animation.

### Expandable Content

New content can be added through:

- dice;
- faces;
- engravings;
- visual themes;
- materials;
- Decrees.

### Strong Screenshot Identity

A bizarre, heavily modified die can become instantly recognisable.

### Good Streaming Potential

Players can discuss:

- strange builds;
- rare dice;
- huge scoring chains;
- disastrous rolls;
- clever Nudges;
- unusual synergies.

### Collectibility

Visual dice sets give players a reason to pursue unlocks without requiring pay-to-win mechanics.

---

## 37. Core Risks

### Too Much Randomness

If player manipulation is insufficient, the game becomes frustrating.

**Response:** ensure Hold, Nudge, Arrange, upgrades, and build consistency provide meaningful control.

---

### Too Much Complexity on Faces

If every face contains paragraphs of text, the dice stop being readable.

**Response:** effects need strong icons, short descriptions, and consistent rules.

---

### Nudge Becomes an Obvious Choice

If the player always Nudges toward the highest number, the mechanic has failed.

**Response:** face effects must regularly make lower values or unusual faces desirable.

---

### Passive Systems Creep In

It will be tempting to add more relics, charms, gods, blessings, inventories, or cards.

**Response:** always ask whether the mechanic could live on a die instead.

---

### Dice Stop Feeling Physical

If upgrades become abstract menus, the game's strongest theme is weakened.

**Response:** modifications should be represented visually and physically whenever possible.

---

### Visual Monotony

A single table for 40 minutes could become dull.

**Response:** use subtle changes in lighting, table objects, dice materials, sound, Decree presentation, and accumulated modifications rather than adding large environments.

---

## 38. The Central Design Test

Every major new mechanic should be asked:

> **Does this make building, manipulating, understanding, or enjoying the dice themselves more interesting?**

If not, it is probably unnecessary.

---

## 39. One-Sentence Pitch

> **A minimalist roguelike where you roll fate, manipulate the result, and build custom dice one face at a time.**

Alternative:

> **A dice-building roguelike where every face can be modified, every roll is a puzzle, and tiny cubes decide the fate of unseen worlds.**

---

## 40. Core Design Statement

> **Roll imperfect information. Manipulate the result. Build increasingly impossible dice.**

And most importantly:

> **The player's build exists on the six faces of their dice.**

That principle should be protected throughout development.
"""

path = Path("/mnt/data/design.md")
path.write_text(content, encoding="utf-8")
print(f"Created {path} ({len(content.splitlines())} lines)")

## 

```bash
git add .
git commit -m ""
git push
```

