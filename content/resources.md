# Resources — Houses of Venice

*Content file. See `houses-of-venice.md` §4 for the underlying economic framework
(estates, market categories, the wealth→Renown pump) and §6/§11 for regions, the East, and
Projects. This file is the concrete resource roster and the gathering/processing rules.
Numbers (yields, upkeep costs, recipe ratios) are deliberately left as playtest dials per
`houses-of-venice.md` §F — only shapes and categories are locked in here.*

---

## 0. How this list got here

This roster went through a heavy trim pass in session. The guiding rule: every surviving
item has to do a **distinct mechanical job** — if two items would behave identically, they
were merged. Cut/merged along the way: Poultry + Pork + Beef → **Meat**; Venison + Boar →
**Wild Game**; Caviar + Clams + misc. rare catches → **Rare Catch**; Gold + Silver + Copper →
**Bullion** (no token at all — see §4); Soda Ash dropped from Glass's recipe (folded into a
flat ducat cost). Iron was considered and explicitly declined — see `CLAUDE.md`'s
"stay out of the combat/weapons economy" principle; it's a later-module idea at most, not
core content.

---

## 1. Market categories and the full roster

Each category is **one shared floating price track** (§4.4) — everything in a category
rises/falls together when anyone sells or donates into it. Individual item identity is kept
only for **variety-bonus purposes** (Project guest attendance, specific objectives that call
for a named good) and for recipe requirements — not for separate pricing.

### Foods
*Only Bread is direct-donation-eligible in this category (Beer moved to Alcohol, see below).*

| Item | Source | Notes |
|---|---|---|
| Grain | Farmlands | Feeds Bread |
| Fish | Coast/Islands | |
| Dairy | Farmlands | |
| Meat | Farmlands | Poultry/Pork/Beef flavor-merged into one token |
| Grapes | Farmlands | **Triple-use**: basic Food, Luxury Food (table grapes), or Wine |
| Bread | *processed from Grain* | Donation floor — Renown floats with this category's price |

### Alcohol
| Item | Source | Notes |
|---|---|---|
| Beer | *processed from Grain* | Cheap tier, **direct-donation eligible** (moved here from Foods; Renown now floats with Alcohol's price, not Foods') |
| Cider | Foreign Merchants (Northern trade flavor) | Mid tier; import-only, no domestic estate |
| Wine | *processed from Grapes* | Premium tier; not directly donatable — Project fuel or market. Also the standard Cathedral-monument upkeep good |

### Luxury Foods
| Item | Source | Notes |
|---|---|---|
| Oil | *processed from Olives* | Moved here from Furnishings — cooking oil is a food, not a furnishing |
| Spices | East (trade route) / Foreign Merchants | The historical flagship import |
| Sugar → Confections | East only | |
| Wild Game | Hunting mission (Mountains/Woodlands) | Merged Venison+Boar; noble-only special action, Tier 2 |
| Rare Catch | Fishing mission (Coast/Islands-adjacent) | Merged sturgeon/caviar/clams/etc.; noble-only special action, Tier 2 |

### Textiles
| Item | Source | Notes |
|---|---|---|
| Wool | Farmlands/Hills | → Cloth or Tapestry |
| Flax | Farmlands | → Linen or Tapestry |
| Hemp | Farmlands (cultivated) | Flexible — sellable as a generic Textile good, *or* used for Ships. Not naval-exclusive |
| Silk (raw) | **East only** | Flagship good → Silk Cloth or Tapestry |

### Precious/Mined
| Item | Source | Notes |
|---|---|---|
| Gems | East / Foreign Merchants | → Jewelry |
| Amber | Foreign Merchants (Northern trade) | Similar uses to Gems — Jewelry or standalone Luxury Goods |
| *(Bullion)* | Northern-trade Mine (owned, auctioned foreign estate) | **No token** — a Mine simply yields **ducats directly** each season instead of a raw good. Gold/Silver/Copper collapsed into this one concept |

### Furnishings
| Item | Source | Notes |
|---|---|---|
| Furniture | *processed from Timber* | |
| Tapestry | *processed from Wool/Flax/Silk* | |
| Pottery | *processed from Clay* | |
| Glass | *processed from Silica only* | Soda Ash folded into a flat ducat cost, not tracked. **Multi-use**: sell as Furnishings, feed Jewelry (with/instead of Gems or Amber), or spend as a Plot/monument construction material (stained glass in a cathedral) |

### Commons materials
*Always available, no ownership required — see §3 for the gathering rules, which differ per
material.*

| Item | Source | Feeds |
|---|---|---|
| Timber | Mountains/Woodlands | Ships, Furniture, estate upgrades |
| Stone | Hills/Mountains | Statues, monument construction |
| Clay | Coast/Islands (lagoon sandbanks) | Pottery |
| Silica | Coast/Islands | Glass |

### Naval
| Item | Source | Notes |
|---|---|---|
| Ships | *built from Timber + Hemp + ducats, at a City Industry estate ("the Arsenal")* | Consumed for voyages, naval defense contributions, or committing to an East trade route — or sold hand-to-hand (§4.5) if a house builds more than it needs. **No dedicated market category.** |

### Entertainment
No raw good feeds this category. Settled as **Project/service-only** — a running theatre or
troupe generates Entertainment value directly, not through a resource chain.

### Northern trade (a Foreign Merchants flavor, not a parallel mechanic)
Amber, Furs, Cider, and Bullion-Mines are all conceptually **Northern-trade** goods — the
historical Amber Road terminated at Venice, and the Fondaco dei Tedeschi was the real German
merchants' trading house there. Unlike the East, this doesn't get its own committed-ships/
trade-route mechanic (at least not yet) — Amber, Furs, and Cider are just Foreign Merchants
goods (§4.6) with Northern flavor; Bullion is the one exception, sourced from an actual owned/
auctioned foreign Mine estate rather than the fixed backstop, since mines are scarce and
contestable the way a generic import isn't.

---

## 2. Buying, selling, and Renown conversion

Applies uniformly to everything above (see `houses-of-venice.md` §4.4–§4.6, §11 Tier 1):

- **Sell to market** — hand over the good, take the category's current price, price drops a
  step. **Sell-only** — there is no symmetric "buy from the market." If you need a good you
  don't produce, you negotiate with a house that does.
- **Player trade** (§4.5) — hand-to-hand, any ratio, zero Control. Works for everything,
  including Ships and East-exclusive goods.
- **Foreign Merchants** (§4.6) — fixed buy/sell rate, no negotiation. Reserved for genuine
  pure-imports (Cider, Furs, Amber, and anything East-exclusive if a house hasn't developed
  its own trade route).
- **Donate for Renown** — **only Bread (Foods) and Beer (Alcohol)** are directly donatable.
  Renown = the category's current market price; donating also pushes that price down a step,
  same lever as selling.
- **Feed a Project** — everything else of value (Wine, Cloth/Linen/Silk Cloth, Jewelry, Oil,
  Glass, Confections, Statues) funds Projects instead, per the declared-cost model in §11
  Tier 1.

---

## 3. Gathering and processing

### 3.1 Gathering (owned Agriculture estates — Grain, Fish, Dairy, Meat, Grapes, Wool, Flax,
Hemp)
Reuses the travel + tap system, nothing new:
1. Travel to the estate's region (travel mechanism itself is ❓ not committed — see
   `houses-of-venice.md` §6.2).
2. Tap the estate — one use per season.
3. Take the estate's fixed yield from that region's token bank.
4. Carry the tokens home — no separate cost for the return leg.

### 3.2 Processing (owned Industry estates — Bread, Cured goods→Meat stays raw per the trim,
Wine, Beer, Cloth/Linen/Tapestry, Jewelry, Furniture, Pottery, Glass, Confections, Ships)
Same tap mechanic, consuming inputs instead of yielding from nothing:
1. Get the raw tokens physically to the Industry estate's region (usually the City) — costed
   by whatever travel already brought the goods home, no additional charge.
2. Move within the City to the specific Industry estate — **free**, per the established "no
   travel time within a region/city" rule.
3. Tap the Industry estate — one use per season.
4. Exchange the required raw inputs for finished output at a fixed printed ratio. Some
   recipes need more than one input at once (Glass: Silica [+ a flat ducat cost standing in
   for the soda-ash flux]; Ships: Timber + Hemp + ducats) — that's a pattern, not an
   exception.

### 3.3 Commons gathering (Timber, Stone, Clay, Silica — unowned, always available)
No estate to buy or own. Instead:
1. Travel to the commons region (Mountains/Woodlands for Timber; Hills/Mountains for Stone;
   Coast/Islands for Clay and Silica).
2. Bring **1 Food item per unit** of material you want to gather, up to whatever the region
   allows that visit.
3. Spend the harvesting time itself (❓ still open whether this scales with quantity
   gathered, or is a flat per-visit cost regardless of how much you bring food for).
4. Return home with the material.

**Scarcity is deliberately different per material — three distinct, physical mechanics, not
one rule reused three times:**
- **Timber** — a shared, **depleting pool of harvestable trees per season**, first-come-
  first-served. Physical prop: a pile of tree tokens at the table that shrinks as houses
  claim them, refilling at season start.
- **Stone** — a **fixed number of concurrent mining slots**. Physical prop: a literal limited
  number of spots at the quarry table. ❓ Still open: do slots free up during a season as
  miners finish and leave (a queue), or is it a one-time-per-season claim like Timber's pool
  (a land-grab)?
- **Clay and Silica** — **no hard cap at all**; gather as much as you can afford in Food.
  Clay's balancing cost instead is **inefficiency** — it takes more Clay than Stone or Timber
  to achieve an equivalent building result, so unlimited access doesn't trivially dominate.

This scarcity gradient is tuned to match a recipe-quantity gradient: a typical construction
project wants the **most** Timber, a **medium** amount of Clay, and the **least** Stone —
so the hardest material to get is needed in the smallest amount, and total effort stays
roughly comparable across which material a house leans on.

---

## 4. Open items (playtest dials or genuinely undecided, not oversights)
- Exact yields, upkeep costs, and recipe ratios — all magnitudes, per `houses-of-venice.md`
  §F's convention of designing shapes and leaving constants tunable.
- Whether Stone's mining slots refill mid-season or are claimed once per season (§3.3).
- Whether commons-material harvesting time scales with quantity gathered, or is flat per
  visit (§3.3).
- The domestic travel mechanism itself (carriage/schedule vs. a personal timer whenever a
  player chooses to go) — see `houses-of-venice.md` §6.2, explicitly not committed.
