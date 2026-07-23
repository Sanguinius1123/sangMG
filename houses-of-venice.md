# Houses of Venice — Design Document

*A megagame for 40–60 players, all-day format (~10am–5pm).*
*Working draft. Last updated during design session 3 (resources, the East, Ships, monument
upkeep, commons materials).*

---

## 0. How to use this document

This is the living source of truth for the design. Keep it yourself (a single Markdown
file, or in Google Drive) and paste/upload it at the start of a session to continue.
Sections are numbered for easy reference. Open questions are collected in §12.

**Status key:** ✅ decided · 🔶 leaning / provisional · ❓ open question

---

## 1. Premise & pitch

Each team is a noble/merchant **House** of Venice. Houses generate wealth, power, and
reputation, all of which funnel into a single visible score, **Renown**. The house with
the most Renown (and thus the most influence) wins. The real texture of play is
**negotiating, buying and selling, building alliances, and backstabbing**, balanced
against the need to **cooperate against outside threats** to the city.

- **Player count:** 40–60. ✅
- **Session:** ~10am–5pm, 30-min lunch → ~5 hours of actual play. ✅
- **Feeling target:** scheming merchant-nobles; competition vs. collective defense.

---

## 2. Core design philosophy

- **Minimal Control reliance for the standard loop.** ✅ Routine actions (produce,
  process, trade, sell, donate) are fully self-service with physical components. Control
  is reserved for the *exceptional* (special actions, events, outcome resolution).
- **Self-policing / social enforcement over anti-cheat.** ✅ Cheaters get caught and
  ejected; no elaborate policing mechanics. Physical/visible components (tapping, shared
  tables) provide passive enforcement.
- **Structural/systemic anti-runaway over interventionist.** ✅ Clamps emerge from the
  fiction (food upkeep, travel time, market saturation, taxation, threats), not from
  referee fiat.
- **Control bandwidth is finite** — prefer mechanics that self-regulate.
- **Ship the smallest complete loop first;** treat crusades, missions, extra special
  roles, etc. as later modules. Prove the core before adding.

---

## 3. Renown (the single score) ✅

Renown is the win condition, the council voting weight, AND a spendable resource. One
number doing triple duty makes it genuinely agonizing to manage.

- **Leaderboard:** visible to the whole room. Doubles as a *targeting reticle* — the room
  coalesces against whoever leads.
- **Voting power:** in council, your vote weight scales with your Renown. Higher Renown =
  more influence; as you fall, so does your say.
- **Spendable:** you can burn Renown for advantage (see §7 vote proposals), gambling that
  the spend earns back more than it cost.

### 3.1 Progressive decay ✅ (curve 🔶)
Renown decays each season to force continual work to stay ahead.
- **Progressive**, not flat: top houses lose a bigger slice, trailing houses lose little
  or nothing. Reads as "fame is fickle; the mighty fall furthest," and protects trailing
  players from feeling locked out by mid-afternoon.
- Provisional starting shape: leader & runner-up lose a chunk, middle loses a little,
  bottom loses ~nothing. Tune against real renown-swing sizes in playtest.
- Decay creates *pressure* but not *overtake* on its own — overtake must come from
  earned/lost Renown in play, so **renown sources must produce swings at least as big as
  a season's decay** or the board stalls.
- Tempo dial: churny (thrashing board, knife-fight endgame) vs. sticky (stable, decided
  early). Given ~8–10 seasons, err churny but not so hard that work feels to evaporate.
  Playtest tell: same house leads season 2→end = too light; leading is meaningless = too
  heavy.

### 3.2 Renown sinks must be *gambles*, not taxes
Every place you spend Renown should have a credible path back to *more* Renown. "Pay N
renown to draw a card" feels bad; "sponsor a feast that raises your standing" is a
compelling gamble. Always ask: what's the path back to more renown from this spend?

---

## 4. Economy

### 4.1 Resources ✅ — see `content/resources.md` for the full roster
Superseded by session 3's resource-generation pass: the original "~a dozen kinds, ~5 chains"
target was deliberately relaxed in favor of richness (variety-bonus texture on Foods,
Textiles, Furnishings), then **aggressively trimmed** back down wherever two items would
have behaved identically (see `content/resources.md` §0 for the merge list — Meat, Wild
Game, Rare Catch, Bullion). Every remaining item earns a distinct mechanical job; nothing
survives purely for flavor.

- **Market categories** ✅ (renamed/reorganized from the original list): Foods, Alcohol,
  Luxury Foods, Textiles (was Clothing), Precious/Mined (was Luxury Goods), Furnishings,
  Entertainment (settled: no raw good feeds this, Project/service-only). Full item-by-
  category roster, sourcing, and the gathering/processing rules (including the three
  distinct commons-material scarcity mechanics for Timber/Stone/Clay) live in
  `content/resources.md`.
- **Only Bread and Beer are direct-donation eligible** ✅ — donation-eligibility is attached
  to those two specific goods, not a whole category (Beer moved to Alcohol but kept its
  basic-good status; its Renown now floats with Alcohol's price instead of Foods').

### 4.2 Estates ✅
Estates are the production engine and the engine-building layer.

- Each estate is a **specific type**:
  - **Agriculture** (mainland / *terraferma*): produces *raw* goods (wheat, grapes, flax,
    olives). Cannot process.
  - **Industry** (in the city): *converts* raw → finished (e.g. grapes→wine). Produces no
    raw of its own; must be fed.
- **Split is deliberately incomplete** so nobody is self-sufficient → forces trade. A
  pure-industry house is a wine empire that can't grow a grape or feed a worker; a
  pure-agriculture house drowns in raw goods it can't refine. Neither thrives alone.
- **Development:** estates have building slots; spend ducats + resources to add workshops
  (bakery unlocks bread, weavery unlocks cloth) or improve raw output.
- **New estates** come up for auction (§5), roughly once per season.
- **Two distinct auction commodities** ✅: (a) **developed estates** — already built,
  producing immediately, whether freshly seeded by Control or a liquidated estate a house
  sold back; (b) **raw land** — an undeveloped plot that must be developed (via the
  development spend, above) into a working estate before it produces anything. Control
  seeds and throttles both supply lines independently — if either is being snapped up too
  fast, Control slows its release.
- **No hard cap on estates per region** ✅ — the limiting factor is availability (however
  many developed estates/land plots Control has released) and cost, not table space or a
  printed slot count.
- **Houses may sell estates back** ✅ — an estate a house can't service (travel time, §6;
  food, §4.3) or would rather convert to ducats returns to the developed-estate auction
  pool. Gives both the travel-time and food clamps a real exit valve instead of leaving a
  dead, unfed asset sitting on the books.
- **Leaning:** each house starts with a leaning = starting bonus + signature ability, NOT
  a restriction. A banking house *can* pivot to politics, just at a disadvantage.

### 4.3 Food as the soft anti-runaway clamp ✅
- Every estate must be **fed each season** to operate. More estates = bigger food bill.
- At upkeep each house counts active estates, pays that much food to the bank; any estate
  it can't feed simply **doesn't produce** that season.
- Scales automatically with size, fully self-service (just counting), and creates trade
  leverage ("nice weaveries — shame if nobody sold you grain this turn").

### 4.4 The Market — self-service floating price tracks ✅ (the economic heart)
Each market **category** (Foods, Alcohol, Luxury Foods, Textiles, Precious/Mined,
Furnishings, Entertainment — renamed/reorganized in session 3, see §4.1 and
`content/resources.md`) has a physical **price ladder** (e.g. 1–10 ducats), marker starting
at a baseline (~5). **Sell-only** — there is no symmetric "buy from the market"; a good you
don't produce has to come from another player (§4.5) or Foreign Merchants (§4.6), never an
impersonal bank purchase. This is deliberate: it's what keeps the incomplete-production-split
(§4.2) actually forcing trade instead of being routed around.

- **To sell:** hand over the good, take the current marked price from the bank, slide the
  marker **down one step** yourself. Next seller gets less.
- **Renewal:** at upkeep every marker drifts back **up** a step or two toward baseline.
- **No Control math** — players manipulate the tracks; saturation is visible across the
  room.
- **Base price** each good drifts toward; unmet demand pushes value up, oversupply pushes
  it down.
- **Emergent cartels & betrayal:** because selling is sequential and prices fall as goods
  pile in, houses form cartels to hold prices — and each cartel invites a defector to dump
  first while the price is high. Backstabbing emerges from the economy itself.

### 4.5 Player-to-player trade ✅
Hand-to-hand, at will, zero Control, nothing logged. "I give you 3 spice, you give me 5
ducats," done.

### 4.6 Foreign merchants — fixed printed backstop ✅
A printed board with fixed buy/sell rates (e.g. foreigners buy grain at 2, sell spice at
8). No live Control person needed; Control only touches it when an event shifts rates.
Acts as a guaranteed-but-unattractive floor/ceiling so nobody is ever truly stuck.

- **Northern trade** ✅ (session 3): this backstop isn't only flavored as Levantine — Amber,
  Furs, and Cider are Northern-trade goods (the historical Amber Road terminated at Venice;
  the Fondaco dei Tedeschi was Venice's real German-merchant trading house), bought here at
  the same fixed rate. Doesn't need its own mechanic the way the East does (§6.3) — one
  backstop, two flavors of origin. The one exception is **Bullion** (former Gold/Silver/
  Copper): sourced from an actual ownable, auctioned Northern Mine estate rather than the
  fixed board, since mines are scarce/contestable the way a generic import isn't.

---

## 5. The Auction ✅
- **Always running**, a persistent table players visit at will (not a whole-room event).
- One dedicated Control auctioneer is justified here.
- Sells **new estates** (roughly one per season) and other lots; Control may seed cheap
  lots early. Control takes a **fee** (a Renown/ducat sink).
- 🔶 Throughput: sealed-bid scales best for volume; reserve open-outcry for a few marquee
  lots (a great estate, a trade monopoly). Decide the exact mix later.

---

## 6. Spatial model — regional tables ✅ (a key structural idea)
Estates are **locations** spread across the room, not at house tables. Regions each get a
table: **City, Coast/Islands, Farmlands, Hills**, etc. Each region holds several estates.

- Players **physically travel** to a region to tap their estate and grab resource tokens,
  then ferry them back to production estates or the market.
- **Travel time = third self-enforcing anti-runaway clamp** (stacks with food + tax). A
  sprawling house is *time-starved* — only so many minutes per season — as well as
  food-starved. Time can't be bought or traded. Creates a real question: is a 9th estate
  worth it if you can't service what you own?
- Emergent **labor market:** a big house that can't cover all estates may hire/lease to
  another player → more dependency and negotiation.
- **Localized threats:** pirates hit the Coast table, plague hits the Hills, etc. Threats
  become physical space ("the hills are burning, my quarries are dark this season").
- **The City region hosts three distinct kinds of location** ✅ — kept deliberately
  separate so "estate" doesn't get overloaded:
  - **Production estates** (§4.2 — *estates* proper, raw materials + processing only):
    mostly Industry (processing) estates, plus a **rare** exception of actual
    resource-producing estates (planting, mining, lumber) — a deliberate break from
    "agriculture is mainland-only." These cost **zero travel time**, so they carry a real
    convenience premium left to the auction to bid up naturally rather than hand-priced;
    likely the single most contested lot type in the game and a good candidate for a
    marquee **open-outcry** slot (§5's still-open throughput question).
  - **Plots** (a separate category, *not* an estate — see §11 Tier 1): sites for
    Renown-generating Projects (historical sites, churches, theatres, monuments). Auctioned
    fresh **each season** alongside estates, and deliberately priced near-prohibitively to
    develop, keeping City land genuinely scarce.
  - **Each house's own City residence** 🔶 (name TBD): every house has one dedicated
    home-base location in the City — storage + seat, distinct from both estates and plots.
    Not auctioned; a starting fixture.
  - None of the above are threat-immune despite the travel-time immunity — **The People's
    "rise up" mechanic (§11.5)** is the City's own localized threat, structurally equivalent
    to pirates on the Coast or plague in the Hills.

### 6.1 Layout cautions ❓→🔶
- **Physical placement of regional tables carries no mechanical weight** ✅ (superseded by
  §6.2): since travel is represented abstractly (shared clock + sand timer), not by real
  room distance, tables can sit anywhere relative to each other with no effect on the
  clamp — there's no travel time *within* a region or within the City either, so free
  movement there is fine. The old "space regions physically far apart to disperse crowds"
  mitigation is **stale and removed** — distance no longer disperses anything, because
  distance no longer costs anything.
- **The bottleneck risk didn't disappear, it relocated:** since every regional trip departs
  from the City's carriage points, a bell-triggered convergence now concentrates at **the
  City hub**, not at the destination regions. Mitigations that still apply:
  - **Token banks live at each regional table** (harvest is one stop, not two).
  - Distribute estates **evenly** across regions so no single carriage line gets
    disproportionate traffic and turns its City-side boarding point into a crush.
  - Maybe a passive steward at the busiest **City carriage point** (not a regional table),
    not an adjudicator.
- **Pacing risk:** if a season is mostly walking/tapping/ferrying, negotiation gets
  crowded out. Danger sign: everyone busy, nobody talking. Keep stops-per-season modest so
  a focused house finishes its circuit in the first third and has the rest to scheme.
  Target rhythm: **bell → burst of movement out → gravitational settle back** to house
  tables/market where the talking happens.

### 6.2 Travel mechanism: carriages ❓ (not committed — one candidate among options)
Real physical walking distance won't reliably create meaningful travel time in a smaller
room, so travel is represented with dedicated components instead of relying on the room's
actual footprint. **This whole carriage/schedule system is explicitly not locked in** —
Sang flagged it as something he was never fully committed to. Kept below as a live option
rather than deleted, but don't treat any of it as settled.

- **Live alternative, possibly simpler:** just flip your own sand timer whenever you
  personally choose to travel — no public/private split, no shared-clock schedule, no ducat
  toll. This still delivers the one thing that actually matters (real, physical,
  unbypassable time, self-enforcing via the timer) without the scheduling machinery below.
  It also sidesteps the City-hub-convergence problem the scheduled version creates in the
  first place (§6.1) — if nobody's waiting on a shared departure moment, nobody converges on
  one. Confirmed as the leading direction for the (still-undocumented) Eastern trade-route
  concept discussed in session, and plausibly the right call for the domestic regions too,
  but not yet decided there.

- **Public carriage** ✅: each region has its own carriage running a fixed schedule keyed to
  the shared room clock (the same big clock that counts up the season) — e.g. departs on the
  even minute, both directions. **Free, no capacity limit, zero Control** — players just
  show up at the right clock-minute. No need to stagger schedules across regions relative to
  one another; individual travel decisions during a season are expected to spread naturally
  (only the season-opening bell forces simultaneous movement) — watch in playtest for
  unexpected clustering (e.g. everyone reacting to the same event at once).
- **Private carriage** 🔶: pay a flat ducat fee (provisional: **1 ducat**) to depart
  immediately instead of waiting for the public schedule.
- **The transit itself still costs real, committed time regardless of which carriage** —
  represented physically by a **sand timer** (🔶 not committed to the exact component;
  duration TBD) flipped when travel begins. No physical puzzle, just a visible wait — fits
  the self-policing/physical-component principle and is accessible by design.
- **What the ducat buys is the wait, not the time.** Paying never skips the sand timer — it
  only skips waiting for the next scheduled departure. This keeps the travel-time clamp
  (§8) genuinely unbypassable even by a wealthy house; see rationale §R.
- Private-carriage ducats are paid **to the bank** (a pure toll/sink), same treatment as the
  Project-attendance ducat (§11 Tier 1) — consistent, and prevents convenience purchases from
  quietly becoming a way to escape the clamp.

### 6.3 The East — foreign trade routes ✅ (shape locked, magnitudes TBD)
A way to acquire genuinely foreign goods (raw Silk, Spices, Sugar, Gems) as real production
rather than only through the flat Foreign Merchants backstop (§4.6).

- **Auctioned like land, developed like an estate** ✅: the Auction (§5) sells "trade route"
  lots the same way it sells raw land (§4.2/rationale §S) — a house wins the *opportunity*,
  then *develops* it by **permanently committing built Ships** (instead of the usual
  ducats+goods development spend). Once committed, the route produces its good every season
  like any other estate.
- **No reclaiming committed ships** ✅: ships locked into a route can't be pulled back out to
  liquid status — that spend is consumed into the asset, the same way estate-development
  spend doesn't "un-develop." The only exit is **selling the whole package** (route + its
  committed ships) to another house, mirroring how a developed estate can be resold.
- **Has its own physical table** ✅: unlike domestic regions, the East's table placement
  *does* matter, because the point isn't distance — it's transit length. Committed ships sit
  visibly on the trade-route card (ownership + investment level, at a glance, no Control
  needed to verify).
- **No shared schedule — you leave whenever you want** ✅: it's your ship and your route, so
  there's no public/private carriage distinction here. Just flip the sand timer(s) whenever
  you choose to go — **a longer sequence than domestic trips** (a couple of flips, representing
  a real Levant voyage), still just the timer-only travel model, not the (uncommitted)
  carriage/schedule system.
- **Social isolation while there** ✅: players at the East table can only talk to whoever
  else is physically there — cut off from the rest of the room's negotiation for the
  duration. A deliberate use of physical space to create a real strategic tradeoff (§J), not
  a punishment — mitigated by houses sending a specific representative rather than their
  whole team going dark. Naturally means only houses with people to spare can run this
  strategy comfortably (historically apt — only big trading houses ran months-long
  Levant voyages).
- **The cost is the crowd control** ✅: because visiting is expensive in time and
  isolating socially, nobody floods the East casually — only houses with a genuinely good
  reason go. One mechanism (the transit cost) does double duty: it's both what makes a
  visit meaningful *and* what prevents the table from becoming a bottleneck. No separate
  crowd-control rule needed.
- **Separate from one-off risky voyages** ✅: *routine* collection from an already-committed
  route is self-service and safe-but-costly (no Control, just the timer). A standalone risky
  voyage — Control-adjudicated, a die roll, Tier 2 Renown (§11) — is a different action you'd
  take when you *don't* have an established route yet, or want to gamble instead of invest.
- 🔶 **Possible later addition**: a Control-run or player-occupied "foreign trade
  representative" at the East table — directly maps onto the already-named "Foreign
  Ambassador" later-module special role (§11.5). Whether this is a full special role now or a
  lighter Control presence (like the Auction's dedicated auctioneer, §5) is undecided —
  moving up a "later module" early is a deliberate choice, not a default.

### 6.4 Ships ✅ (a finished good, not a persistent tracked asset with its own systems)
- **Built from Timber + Hemp + ducats** at a City Industry estate (the historical Arsenal was
  literally in Venice, fed by Terraferma timber) — the same multi-input recipe pattern as
  Glass, not a novel exception.
- **Two jobs, one resource:** committed permanently to a East trade route (§6.3, safe/steady),
  or spent one-off on a risky voyage (Tier 2 Renown, Control-adjudicated) or a naval/threat-
  defense contribution (§9 — the exact resource cost of any given threat is a **content-level
  choice per event card**, not a universal rule; some threats may want Timber+Hemp+ducats,
  others may just want ducats for mercenaries).
- **No dedicated market category** ✅: a Ship is consumed directly when spent, or — if a house
  builds more than it needs — sold hand-to-hand to another house via ordinary player trade
  (§4.5). No auction lot, no price track, no new machinery; a shipbuilding-focused house is a
  viable niche using mechanics that already exist.

---

## 7. The Council ✅
The political spine. Same institution serves both **selfish competition** (control it to
tax rivals) and **collective defense** (coordinate against threats) — so the tension is
structural. Every crisis asks: do we trust the current officeholders to spend common tax
fairly, or is the Doge steering the navy to guard his own routes?

- Voting weight = Renown (§3).
- Offices grant real levers: set tax rates, authorize investigations, control the auction
  fee, etc. Scramble for office is self-sustaining drama.
- 🔶 Venetian institutions to draw on: Doge, Council of Ten, Great Council. Elected/voted
  by players → runs on player action, ~zero Control.
- A council clerk (Control) is justified to administer.

### 7.1 Proposing legislation costs Renown ✅
To stop vote-spam and make proposing a commitment:
- **Flat 1 Renown** to submit a proposal and call a vote. ✅ (Chosen over content-based
  pricing, which is an adjudication nightmare — never ask Control to price a law by
  content.)
- Players may freely discuss, bribe, and draft anything; the cost is only paid at the
  moment someone *submits* for a vote.
- **Do NOT scale cost by proposer's Renown** — that would price the leader (whom the room
  most wants to constrain) out of the arena and double up with decay. ✅
- **Fallback if spam persists:** escalating cost by *count* within a season (1st proposal
  costs 1, 2nd costs 2…), resetting each season. Still zero adjudication — just counting.
- **Cost-sharing:** one *or more* players can jointly pay to trigger a vote → trailing
  houses pool Renown to force proposals; leaders may bribe someone *not* to co-sponsor.

### 7.2 Taxation = the political anti-runaway clamp ✅
Whoever holds office levies taxes; assessed on wealth/estate count, leaders pay
disproportionately. The have-nots have the votes and motive to elect a council that soaks
the leader — clamp applied by players, not rules.

---

## 8. Anti-runaway stack (summary) ✅
Four complementary clamps, all emergent from fiction:
1. **Food upkeep** — automatic *soft* clamp on expansion (scales with estate count).
2. **Travel time** — automatic *soft* clamp (sprawl is time-starved).
3. **Taxation** — *political* clamp the room aims at the leader.
4. **External threats** — *catastrophic* clamp targeting whoever's most exposed.
5. **(Free bonus) Reputation/Renown** — grasping too hard costs standing; the economic
   leader is often the political pariah (classic Venetian bind).
Plus **progressive decay** (§3.1) as the continual pressure to keep earning.

---

## 9. External threats — cooperation engine ✅
Threats are the catastrophic clamp AND the pacing tool AND the thing that forces
cooperation. This is where Control belongs (the special-action tier).

- **Legible & escalating:** a visible pirate/threat track that worsens each season it's
  unaddressed, so inaction has mounting visible cost.
- **Localized** to regions (§6) so they target the exposed (the fat maritime house).
- **Collective solution requires coordination vulnerable to free-riding** (e.g. the navy
  needs 20 ducats pooled; every house hopes others pay so it can skip). A council tax is
  the natural funding tool → loops back to politics.
- **Individual contribution → Renown** (§11 tier 2): pay for mercenaries that clear the
  pirates → gain Renown; under-commit and get wiped → lose Renown.
- Pressure-release valve: a well-timed threat scrambles a stale board or a runaway leader.

---

## 10. Intrigue layer 🔶 (design for graceful failure)
Route almost everything through existing institutions + one shared special-action path, so
Control stays lean and the social mood stays healthy.

- **Secrets & vices:** private cards at setup ("your house secretly funds heretics"; "you
  have a gambling vice — spend 2 ducats at the auction each season or suffer"). Generate
  blackmail and paranoia on their own.
- **Discovery/verification** routes through the council/Ten: accusations can be
  investigated (a Control special action); **false accusation carries its own Renown
  risk.** Keeps accusations from being a costless weapon.
- **Secret societies** ✅ (great, nearly free): hidden cross-house membership with hidden
  objectives that route through systems already built (zealots' alcohol ban = a council
  vote; masons' war = threat-track manipulation). Keep membership **sparse** (a handful
  across 50). Being outed as a member costs house Renown — same discovery risk as vices,
  so the whole intrigue layer feels like one coherent thing.
- **Assassination, dueling, theft = one family of "aggressive special actions"** with a
  single shared resolution path: aggressor submits written intent + spend to Control;
  target may have spent on protection; Control resolves privately with a die and hands each
  side a result slip. One path, many flavors.
- **Guardrails:**
  - Attacks should **hit houses/assets, not benched players.** Assassination removes an
    heir / cripples an estate / forces a costly succession rather than sitting a human out
    for six hours.
  - Brief up front that it's the **houses** feuding, not the people — keep betrayal fun,
    not personally sour.

---

## 11. Renown sources — the three tiers ✅ (framework)
The list of renown sources *is* the list of viable win strategies. Sort every source by
**who determines the amount**:

### Tier 1 — Fixed-rate / market-rate (self-service, zero Control) ✅
The reliable, grindable floor and the main **wealth→Renown pump** (stops rich houses from
sitting on ducats; converting is a public act that paints a target).
- **Renown from donation floats with the market price** ✅ — this *replaces* hand-pricing
  each source. Donating a good gives Renown proportional to its **current market price** on
  the track you already built. If everyone piles into one good, its value (and its
  donation-Renown) craters, pushing the next house elsewhere → **the system self-balances
  toward diverse production with one rule instead of a tuned spreadsheet.**
  - Mechanic: donating ≈ selling, but you get Renown instead of ducats, and **the donation
    still pushes the price down a step** (you added to the glut) → self-limiting,
    first-mover advantage.
  - **Decision:** donations and sales push the **same** price lever — no separate civic
    pool. ✅ Flooding a food market to *harm a food-focused rival* is an intended,
    interesting mechanic.
  - **Only certain (basic) goods sell/donate directly for Renown** ✅ — e.g. **bread &
    beer** are the cheap direct goods for the People. Higher-value goods (wine, jewelry,
    luxury food) **can't** be donated directly; they're used to build **Projects** (below)
    or sold to market.
- **Projects = the high-value Renown path** 🔶: social buildings, art commissions, running
  a theatre, grand gardens, infrastructure (roads, harbors). A money+goods sink that
  produces Renown.
  - **Permanent/monument Projects need a physical site: a Plot** ✅ (§6) — a distinct
    auctionable category (historical sites, churches, theatres, monuments), *not* an estate,
    up for auction fresh each season. A house buys the plot, then funds the Project on it
    (the resource spend described here) to actually complete it. **Ephemeral Projects**
    (the "fancy party" below) don't need a plot — you can throw a party at your existing
    table.
  - **Physical payoff** ✅: completing a Project on a plot gets a **3D-printed model** placed
    on it. Zero Control needed to verify a Project is real — it's sitting there — and the
    City table becomes a visible, ever-growing skyline running in parallel with the Renown
    leaderboard, the same self-enforcing-physical-component logic as tapped estates and the
    sand-timer carriages.
  - **Monuments produce Renown every season, gated by upkeep** ✅: a completed monument-tier
    Plot (cathedral, grand civic building, etc.) doesn't just pay out once — it keeps paying
    a **small, reliable Renown trickle each season**, as long as it's fed a recurring resource
    cost (e.g. a cathedral needs Wine — communion — every upkeep). This reuses the *exact*
    same clamp already governing estates (§4.3): an unfed monument simply produces no Renown
    that season, same forgiving failure state as an unfed estate, no further penalty.
    - **This is deliberately a risk ladder, not a flat rule** 🔶: cheaper monuments (a Statue)
      need no upkeep but only ever produce a small flat amount (e.g. 1 Renown/season, no way
      to boost it); expensive ones (a Cathedral) need real recurring upkeep in exchange for a
      larger, more reliable trickle. Bigger investment = bigger commitment = bigger payoff,
      but also a bigger target.
    - **Why upkeep-gating instead of a flat passive trickle:** every other Renown source in
      the game is one-time/per-action; an unconditional recurring trickle would be the first
      passive-income source and risks recreating the exact "same house leads season 2→end"
      failure state decay (§3.1) exists to prevent — whoever builds earliest just compounds
      forever. Gating it behind a recurring cost turns the monument into an **attackable
      target**: rivals can flood/monopolize/withhold the specific good it needs (the same
      "flood a market to harm a rival" principle already decided for Food, §D) to choke its
      supply. The anti-runaway pressure comes from players aiming economic warfare at each
      other, not a rule capping the mechanic — consistent with §P.2.
  - Example — **"throw a fancy party":** pay silver for staff + wine + a luxury food item;
    reward may get a **bonus if other houses' members show up** to role-play the event.
  - **Guest incentive** ✅ (resolves prior open question): attending costs the representative
    **1 ducat** (flavor: transport/outfit/gift), which is **spent to the bank** — a direct,
    small instance of the wealth→Renown pump. In exchange the attending house gets a flat
    **+1 Renown**. Fully self-service: the representative deposits a house token + the ducat
    at the party (physical, visible proof of attendance); each house moves its own Renown
    marker. The host separately gets a **bonus Renown** 🔶 (threshold/amount TBD — playtest
    dial) if enough guest tokens accumulate. Ducat-to-bank (not to host) is deliberate: it
    keeps the host's spend a real gamble (will people actually show?) rather than letting a
    well-attended party silently pay for itself.
  - **Shared Projects:** two houses co-fund a government building. **The players declare
    the Renown split** at the moment they pay (write it on the project card); Control just
    checks the total and hands it out — **Control notarizes, never judges.** ✅ All the
    scheming/backstabbing lives in the *negotiation over the split* and the risk that a
    promised split won't hold. Disputes route through council/special action, not a
    Control value judgment.
- **Protect the floor** ⚠️: basic-good donation must stay *viable* for a poor house even
  though it's low, so trailing houses always have an honest ladder. Luxury Projects are the
  high-investment ceiling for the rich; food/basic donation is the modest steady floor for
  the poor. Good spread across the wealth spectrum — but if the floor collapses to ~zero,
  the game gets grim for trailers.

### Tier 2 — Outcome-based (piggybacks on Control interactions already happening) ✅
Amount depends on how an uncertain event resolved. Only attach to things that *already*
route through Control (so no new queue): crisis/pirate defense, risky voyages, crusades
(later). The Renown result rides along on a die roll Control was making anyway.

- **Noble missions** ✅: send a representative, Control resolves a die roll — success yields
  a rare Luxury Food (and maybe a small Renown bump for the trophy/feast value), failure
  yields nothing. Two, both historically grounded as explicitly aristocratic pursuits, not
  routine gathering:
  - **Hunting** (Mountains/Woodlands) → **Wild Game** (content/resources.md — merged
    venison/boar into one token).
  - **A special fishing expedition**, distinct from routine lagoon Fish (Coast/Islands) →
    **Rare Catch** (merged sturgeon/caviar/clams/etc.).

### Tier 3 — Negotiated / discretionary → handled by Special Roles ✅
Made **diegetic** by giving the award to an in-fiction actor with an agenda, whom players
court/petition/flatter/bribe — so "subjective" becomes the point, not a fairness hazard.
See §11.5.

### 11.5 Special Roles ✅ (start with 2–3, cast carefully)
Turn tier-3 adjudication into content; also act as **distributed pressure-generators** that
run themselves and lighten Control.
- **Principles:** each role has its **own win condition/drive**; each has **its own pool of
  Renown + unique rewards** to grant in whatever deals it sees fit; keep them **few** (each
  is a single point of failure and another entity to track); **cast confident/fair/
  high-energy players.**
- **True players with published guardrails** 🔶: they have agenda and teeth (can take
  bribes, play favorites) but **can't simply gift huge Renown to allies** — award *rates*
  are semi-fixed; **access and goodwill** are what players negotiate for. A corrupt
  officeholder (e.g. a People's leader taking bribes while the people starve) triggers
  Control **events**.
- **The People** ✅: represents the city's populace. Objective = don't starve / keep a
  high quality of life. Neglect → they **rise up** (a player-generated, self-escalating
  crisis targeting the room's negligence). Fed/entertained → they thank and reward.
- **The Church — two rival players** ✅: each wants to be the **majority religion** (simple,
  legible goal). Each has its own Renown to grant and **unique rewards**. Natural engine
  for piety, suppression of rivals (heretics, maybe the alcohol trade), dedications of
  great works.
- **Later modules** (only after the core cast proves out): Foreign Ambassador, Guild
  Master, etc.
- **Dispensing model** ✅: **basic market donations dispense Renown automatically** at the
  floating rate (§Tier 1); **special roles grant from their own pool discretionarily**
  based on deals/goodwill. So both exist: an automatic floating-rate component + a
  discretionary bonus the cultivated role bestows.

---

## 12. Open questions / next design work
1. **Concrete renown-source numbers & the decay curve** — still the highest-value gap. The
   decay curve (§3.1) can't be set until we know typical per-season Renown swings, which
   depend on source magnitudes. Needs playtest data.
2. ~~**Project incentives for guests**~~ — **resolved** (§11 Tier 1): attending costs 1
   ducat (to the bank) for a flat +1 Renown; host gets a bonus at a guest-count threshold
   (threshold/amount still a playtest dial).
3. **Auction throughput mix** (§5): exact split of sealed-bid vs. open-outcry, and how the
   once-per-season land lot works.
4. **Regional layout specifics** (§6.1): number of regions and estates per region (density/
   balance) are still open. The **physical room plan no longer has mechanical stakes** —
   travel is abstracted via §6.2, so table placement is a pure logistics choice, not a design
   one — and the bottleneck to watch is now the **City carriage points**, not table
   position.
5. **Turn/season structure detail:** ~8–10 real-time seasons bracketed by shared bells
   (opening announcement/events + closing upkeep). Confirm the exact per-season length and
   what precisely happens on each bell. Upkeep must stay **fully parallel & player-run**
   (count estates, pay food, ready/un-tap estates, resolve scheduled council vote) — no
   Control bottleneck.
6. **Estate tapping** ✅ mechanic confirmed (tap/exhaust on use, ready-all at season change)
   — but confirm the physical component (card rotate vs. token flip).
   **Ownership marking** ✅: each house plants a small **heraldry flag** (its own colors/
   sigil, on a stick) at every estate and completed Plot monument it owns. Free passive
   proof of ownership — settles "whose estate is this" with a glance, no steward needed for
   that job (§6.1); swap the flag when an estate is sold/liquidated (§4.2). Same physical-
   component logic as tapping, carriages, and the 3D-printed monuments.
7. **Individual goals & house histories/grudges:** seed richly so season 1 has immediate
   motion. Individual goals should sometimes cut against the house's collective interest.
   Grudges seeded asymmetrically. (Framework agreed; content TBD.)
8. **Travel mechanism itself** (§6.2): whether the domestic carriage/schedule system is used
   at all, or travel is just a personal sand timer flipped whenever a player chooses to go
   (the leading alternative) — explicitly not committed, unlike almost everything else in
   this doc.
9. **Two small commons-gathering mechanics** (`content/resources.md` §3.3): whether Stone's
   mining slots refill mid-season (a queue) or are claimed once per season (a land-grab);
   whether harvesting time scales with quantity gathered or is flat per visit.
10. **The East's foreign trade representative** (§6.3): floated as a possible later addition
    mapping onto the already-named "Foreign Ambassador" special role (§11.5) — full special
    role now, a lighter Control presence, or deferred entirely, is undecided.

---

## 13. Decisions log (quick reference)
- Single score = **Renown**; also voting weight; also spendable. ✅
- **Progressive** decay (curve TBD). ✅
- Food = one universal token + engine base + soft clamp. ✅
- Agriculture vs. Industry estates, deliberately non-self-sufficient. ✅
- Self-service floating **price tracks** = economic heart. ✅
- Donations & sales share the **same** price lever; only **basic** goods donate directly
  for Renown; high-value goods → Projects or market. ✅
- **Flat 1-Renown** proposal fee; never content-priced; cost-sharing allowed; escalate by
  count only if needed. ✅
- Four-part anti-runaway stack + reputation bonus + progressive decay. ✅
- Threats: localized, legible, escalating, free-rider-prone; Control-run. ✅
- Intrigue routes through institutions + one shared special-action path. ✅
- Renown sources sorted into 3 tiers; tier-3 handled by **special roles**. ✅
- Special roles: **The People** + **two rival Church** players to start; true players with
  published guardrails; own Renown pool + unique rewards. ✅
- Project guest incentive: attending costs 1 ducat (spent to bank) for +1 Renown;
  self-service via token deposit; host gets a threshold-based bonus (amount TBD). ✅
- Travel: represented by a sand timer (unbypassable, physical) either way. ✅ Whether it's
  wrapped in a scheduled public/private-carriage system (❓ not committed, §6.2) or just a
  timer flipped whenever a player chooses to go (leading alternative) is still open.
- Monuments produce recurring per-season Renown, gated by upkeep (a required good each
  season, or it just doesn't produce that turn) — deliberately a risk ladder (cheap/
  no-upkeep/flat-small vs. expensive/upkeep/larger-but-attackable). ✅
- City land: three strictly separate categories — **estates** (production only), **plots**
  (auctioned Renown-Project sites, 3D-printed model on completion), each house's own
  **palazzo** (residence/storage, not auctioned). ✅
- **The East**: trade routes auctioned like land, developed by permanently committing built
  Ships (no reclaiming, only reselling the whole package); has a physical table, no shared
  schedule (leave whenever), longer transit, social isolation while there. ✅
- **Ships**: built from Timber+Hemp+ducats at a City Industry estate; consumed for voyages/
  defense/route-commitment, or traded hand-to-hand; no dedicated market category. ✅
- **Resources** (full roster in `content/resources.md`): heavily revised and trimmed —
  market categories renamed (Textiles, Precious/Mined), Beer moved to Alcohol, Oil moved to
  Luxury Foods, Timber/Stone/Clay/Silica gathered as unowned "commons materials" with three
  distinct scarcity mechanics, Northern trade added (Amber/Furs/Cider/Bullion) alongside the
  East. ✅
- Design philosophy: minimal Control, self-policing, systemic clamps, ship core first;
  **stay out of the combat/weapons economy** (see `CLAUDE.md`). ✅
