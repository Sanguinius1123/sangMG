# Houses of Venice — Design Rationale

*The reasoning behind the design. Read alongside `houses-of-venice.md` (which says **what**
the game is); this doc says **why**, what alternatives were rejected, what tensions remain,
and what to watch. Its purpose is to stop future changes from silently unwinding decisions
whose reasons aren't obvious from the conclusion alone.*

---

## How to read this doc

Each entry states the **decision**, the **reasoning**, the **alternative(s) rejected** and
why, and (where relevant) **what to watch**. If you're about to change a decision, read its
rationale first — several choices here look arbitrary but are load-bearing.

---

## A. The central architectural bet: Renown as one number doing three jobs

**Decision.** Renown is simultaneously the win score, the council voting weight, and a
spendable resource.

**Reasoning.** Collapsing three currencies (wealth, power, reputation) into one true score
avoids the classic "find the cheapest pile to farm" degenerate strategy. Wealth and power
become *means* to Renown rather than parallel win-tracks. Making the same number the voting
weight means the leader is structurally powerful (more votes), which *sounds* like runaway
but is actually self-correcting: the visible leaderboard becomes a **targeting reticle** —
the rest of the room can see who's ahead and has both the votes and the motive to gang up,
tax, and legislate against them. Making Renown *spendable* turns every point into an
agonizing choice (progress vs. muscle vs. currency).

**Alternatives rejected.**
- *Three separate point-piles tallied at the end* — degenerates into farming the cheapest
  pile; no interaction between axes.
- *Wealth as the win condition* — makes the economy the whole game and starves the politics
  and intrigue.

**What to watch.** The whole design assumes Renown **swings** (can be lost, not just
gained). If Renown only ratchets upward, the leaderboard stalls and the game is decided by
mid-afternoon. Every subsystem that *removes* Renown (decay, scandal, failed ventures,
caught vices, spent proposals) exists to keep the board churning. Guard this: if you add a
Renown source, check there's a matching way to lose it somewhere in play.

---

## B. Progressive decay (not flat)

**Decision.** Renown decays each season, progressively — top houses lose a bigger slice,
trailing houses lose little or nothing.

**Reasoning.** Decay forces continual work to stay ahead (you can't coast on an early
lead). Progressive rather than flat because (1) it pulls the leader back hardest, which is
the churn we want; (2) it protects trailing players from feeling mathematically locked out
over a long day — a morale consideration that matters across 7 hours; (3) it reads
thematically ("fame is fickle; the mighty fall furthest").

**Subtlety that's easy to miss.** Percentage/progressive decay creates *pressure* but not
*overtake* — everyone shrinking proportionally never changes the *order*. Overtake must come
from Renown actively earned and lost in play. **Therefore renown sources must produce
per-season swings at least as large as decay**, or the board freezes despite the decay.
This is why decay magnitude can't be set independently of source magnitude (see §F).

**Alternatives rejected.**
- *Flat percentage decay* — never reorders the board on its own, and feels punishing to a
  trailing house that plays well but still shrinks.
- *No decay* — early leader coasts; game decided too soon.

**What to watch (playtest dials).** Too light: same house leads season 2→end. Too heavy:
leading feels meaningless because you'll lose it next turn regardless. Want: the lead is
worth having *and* worth fearing to lose. Set the curve only after observing real swing
sizes.

---

## C. The floating-price market as the economic heart

**Decision.** Each market category has a physical price ladder. Selling hands over a good,
pays the current price, and slides the marker down one step (player-manipulated). Markers
drift back toward baseline at upkeep.

**Reasoning.** This is the mechanism that makes a *supply-responsive* economy run with
**zero Control math** — the usual reason floating prices are hard to run at scale. But its
deeper value is that it **manufactures the game's core social play**: because selling is
sequential and prices fall as goods pile in, houses have a concrete reason to form
**cartels** (hold the price by not dumping), and every cartel creates the temptation to
**defect** (dump first while the price is high). Backstabbing emerges from the economic
rules themselves rather than being scripted. This is why the price track is treated as the
beating heart, not a subsystem — remove it and you lose both the self-service economy and
the emergent betrayal.

**Alternatives rejected.**
- *Control-tracked prices* — recreates the queue/bottleneck the whole design avoids.
- *Fixed prices* — no saturation, no cartels, no reason to diversify production.

---

## D. Why donation-Renown floats with the market price (and replaces hand-pricing)

**Decision.** Renown from donating a good is proportional to that good's *current* market
price on the same track; donating also pushes the price down a step (same lever as
selling). Only **basic** goods (bread, beer) donate directly for Renown; high-value goods
must become **Projects** or be sold.

**Reasoning.** Originally the plan was to hand-price each Renown source (food donation = X,
art = Y…) and pray the constants stayed balanced — a fragile tuning spreadsheet that would
collapse into a single dominant conversion if any rate was off. Tying donation-Renown to
the *floating* price solves this with one rule: if everyone piles into donating one good,
its value (and its donation-Renown) craters, pushing the next house toward a less-crowded
good. **The market prices the Renown sources dynamically, so the room self-sorts into
diverse production without any hand-tuned constants.** This directly delivers Sang's goal of
players "organizing themselves" into different niches.

The basic-vs-high-value split (only bread/beer donate directly; wine/jewelry/luxury must
become Projects) creates a clean **strategy spread across the wealth spectrum**: the poor
landed house grinds low-value basic donations for modest steady Renown (the floor); the rich
house makes splashy high-investment Project endowments for big Renown (the ceiling).

**Deliberately chosen consequence.** Donations and sales push the *same* lever (no separate
"civic demand" pool). This means dumping food for Renown *also* craters the food sale price
for the landed houses who live off it — a feature, not a bug: it lets a house **flood a
market to harm a food-focused rival.** (The gentler alternative — a separate civic-demand
pool that refills — was considered and rejected as less dramatic and less in keeping with
the "everything interconnects" philosophy. If playtest shows the shared-lever version makes
a trade too punishing to be viable, the fallback is to have donation *also* nudge a separate
pool, i.e. split the difference.)

**What to watch — PROTECT THE FLOOR.** Because Renown tracks market value, luxury Projects
will always out-earn basic donation per unit. That's correct (a great artwork *should* earn
more prestige than dumped grain), but basic donation must stay **viable for a poor house**
even though it's low — it's the trailing houses' honest ladder. If the floor collapses to
near-zero, trailing players have no honest path and the game gets grim for them by
mid-afternoon. This is the single most important tuning guardrail in the economy.

---

## E. The three-tier renown-source framework (and why it exists)

**Decision.** Every Renown source is classified by *who determines the amount*:
- **Tier 1 — fixed/market-rate:** self-service, zero Control (basic donation at floating
  price; Projects at declared cost).
- **Tier 2 — outcome-based:** amount depends on an uncertain resolution, and *only* attaches
  to things already routing through Control (crisis defense, voyages, crusades). The Renown
  rides along on a die roll Control was making anyway — no new queue.
- **Tier 3 — negotiated/discretionary:** genuinely subjective; handled by **special roles**
  (see §G) so it becomes in-fiction content rather than referee fiat.

**Reasoning.** This framework is a **design tool, not just a taxonomy.** It tells you, for
any new Renown source, exactly how much Control load it costs and where it belongs. The rule
of thumb it encodes: push sources *down* toward Tier 1 (printed/market rate) wherever
possible; only accept Tier 2 when it piggybacks on an existing Control interaction; reserve
Tier 3 (the expensive, dramatic, bottleneck-prone kind) for the handful of set-piece moments
where the social drama is worth the overhead. Use this classifier on every future source.

---

## F. Why the renown numbers and decay curve are deliberately left open

**Decision.** Source magnitudes and the decay curve are *not* hard-coded; only their
*shapes* are designed.

**Reasoning.** They're mutually dependent (§B): decay must be smaller than typical earned
swings or the board freezes; but "typical earned swing" depends on how big the sources are.
You cannot solve this in the abstract — you need to observe a real session's Renown flow. So
the design commits to *shapes* (progressive decay; a protected low floor; luxury ceiling;
sinks-as-gambles) and leaves *constants* as playtest dials. **Do not let a future session
invent precise numbers and present them as settled** — flag them as provisional and tie them
to playtest observation.

---

## G. Special roles as the fix for Tier-3 adjudication

**Decision.** Subjective/negotiated Renown is dispensed by in-fiction **special roles** with
their own agendas and their own Renown pools + unique rewards. Start with **The People** and
**two rival Church** players. They are *true players with published guardrails*, not
Control-with-a-costume.

**Reasoning.** The original tier-3 plan ("Control decides the split based on who spun the
story best") is both a **bottleneck** (every ambiguous case becomes a mini-trial before a
harried referee) and a **fairness hazard** (whatever Control decides, someone feels robbed,
and Control becomes the villain — spending both bandwidth *and* neutrality). Handing the
award to an in-fiction actor with an agenda **makes the subjectivity diegetic**: you don't
petition a referee, you court the Patriarch. If you didn't get the Renown you wanted, you
should have cultivated him better. Subjectivity stops being a bug and becomes the content —
and it aligns with the core loop, which is persuasion and negotiation.

Special roles also double as **distributed, self-running pressure generators** that *reduce*
Control load: the People rising over hunger is a player-generated, self-escalating crisis
aimed at the room's collective negligence; the Church threatening to declare a house impious
is a Renown threat that emerges from play. This is why they serve the minimal-Control goal
rather than fighting it.

**Why "true players with guardrails" and not "impartial dispensers."** An impartial,
Control-aligned role is a fair vending machine — safe but lifeless. A self-interested player
role (can take bribes, play favorites, even be corrupt) is far more alive. The risk is that
unfettered power to grant Renown just becomes a gift to the role-player's friends. The
resolution: **award rates are semi-fixed; what players negotiate for is access and
goodwill, not arbitrary Renown injections.** A corrupt role (e.g. a People's leader taking
bribes while the populace starves) triggers Control **events** as a consequence. So they
have teeth and agenda without being unchecked kingmakers.

**Constraints that matter.**
- **Cast carefully** — these seats need confident, fair, high-energy players. A passive or
  overwhelmed special-role player leaves a hole in the game's pressure; a scene-stealer
  warps the room.
- **Keep them few** (2–3 to start). Each is a single point of failure (if that person is
  weak/absent, a whole subsystem sags) and another entity every house must track and court.
  Foreign Ambassador, Guild Master, etc. are *later modules* — same ship-the-core discipline
  as expansions.

**Dispensing model (how G connects to D).** Basic market donations dispense Renown
*automatically* at the floating rate (Tier 1). Special roles grant from *their own pool
discretionarily* based on deals and goodwill. Both coexist: an automatic floating-rate
component **plus** a discretionary bonus a cultivated role can bestow.

---

## H. The cooperation-vs-competition spine

**Decision.** The same institutions serve both selfish competition and collective defense.
The council you fight to control (to tax rivals) is the identical body that must coordinate
against external threats.

**Reasoning.** Putting both functions in one institution makes the central tension
*structural* rather than thematic decoration. Every crisis forces the question: do we trust
the current officeholders to spend common tax fairly, or is the Doge steering the navy to
protect his own trade routes and let rivals' ships burn? The threat is shared but the
response is administered by a self-interested player — that's where the drama lives. External
threats also serve as a **pacing/pressure-release valve**: a well-timed threat scrambles a
stale board or a runaway leader.

**Design requirements for threats to work** (so they don't become abstract number-management):
legible and *escalating* (a visible track that worsens each unaddressed season, so inaction
has mounting visible cost); *localized* to regions so they target the exposed (the fat
maritime house feels the pirates); and the collective solution must require *coordination
vulnerable to free-riding* (e.g. the navy needs a pooled sum, and every house hopes others
pay so it can skip). Threats are the proper home of Control (the special-action tier).

---

## I. The four-clamp anti-runaway stack (why each exists and why they're layered)

Runaway leaders were flagged early as the main risk (engine-builders snowball). The answer
is a **layered stack**, all emergent from fiction, no rubber-banding:

1. **Food upkeep = automatic soft clamp.** Every estate must be fed each season; more
   estates = bigger food bill; unfed estates don't produce. Scales with size automatically,
   fully self-service (counting only). Turns the least glamorous resource into the knot that
   ties the economy together, and creates trade leverage.
2. **Travel time = automatic soft clamp** (the regional-tables idea, §J). A sprawling house
   is *time-starved* — only so many minutes per season to walk, tap, and ferry — as well as
   food-starved. Time can't be bought or traded, so it's an especially hard cap. Raises a
   real strategic question: is a 9th estate worth it if you can't service what you own?
3. **Taxation = political clamp.** Office-holders tax; assessed on wealth/estate count,
   leaders pay disproportionately; the have-nots have the votes and motive to elect a
   soak-the-leader council. Applied *by players against the front-runner*, so it feels like
   politics, not punishment.
4. **External threats = catastrophic clamp.** Localized threats hit whoever's most exposed
   (usually the dominant trader). Leader either bleeds or pays through the nose; either way
   the gap closes.
- **(Free bonus) Reputation/Renown itself.** Grasping too hard for wealth costs standing;
  the economic leader is often the political pariah (the classic Venetian bind). Costs
  nothing extra to build because it's already in the win condition.

**Why layered rather than one big clamp.** Each targets a different runaway vector (physical
expansion, wealth, exposure) and each fails gracefully. A single heavy clamp would feel like
rubber-banding; four light emergent ones feel like the world pushing back. Progressive decay
(§B) sits on top as the continual pressure to keep earning.

---

## J. The regional-tables spatial model

**Decision.** Estates are *locations* spread across the room on regional tables (City,
Coast/Islands, Farmlands, Hills…), not at house tables. Players physically travel to tap
estates and grab tokens, then ferry them back.

**Reasoning.** This one idea does three jobs: (1) it *is* the travel-time clamp (§I.2); (2)
it makes threats **physical and local** ("the hills are burning, my quarries are dark") —
huge drama for free; (3) it creates an emergent **labor market** (a big house that can't
service all its estates hires/leases to another player → more dependency and negotiation).
The "travel as work" framing also gives players the satisfying feeling of *doing something*.

**Update (see §R): job (1) has moved.** Once the room proved too small for real walking
distance to carry the clamp, travel time was re-implemented as an abstract mechanism (shared
clock + sand timer, §6.2) decoupled from actual table position. The regional-tables model
still delivers jobs (2) and (3) — physical/local threats and the labor market — but it no
longer *is* the travel-time clamp itself; the clamp now lives in §6.2/§R regardless of where
tables physically sit.

**The cost this introduces (watch closely) — partially superseded, see §R.** Regional tables
were flagged as the **new bottleneck** — 50 players converging on 4–5 tables on the bell is a
scrum. The originally-proposed mitigation of spacing regions **physically far apart** is now
moot: since distance no longer costs anything, it no longer disperses anything either, and
that line should be read as struck. The bottleneck itself didn't go away, though — it
relocated to the **City-side carriage points**, since every regional trip now departs from
there. The mitigations that still hold: put token banks *at* each regional table (harvest is
one stop, not two); distribute estates *evenly* so no single carriage line gets
disproportionate traffic; maybe a passive steward at the busiest **City carriage point**
(not a regional table), *not* an adjudicator.

**The deeper pacing risk.** If a season is mostly walking/tapping/ferrying, the *negotiation*
that is the actual premise gets crowded out. **Danger sign: everyone busy, nobody talking.**
Target rhythm per season: *bell → burst of purposeful movement out to the regions →
gravitational settling back* toward house tables and market where the scheming happens. Keep
stops-per-season modest so a focused house finishes its circuit in the first third and has
the rest of the season to wheel and deal. If playtest shows people never stop walking, dial
down stops-per-season or token-hauling friction until the talking has room. **This is the
thing to watch hardest in the first playtest.**

---

## K. Real-time flow + shared beats (resolving a genuine tension)

**Decision.** The economy runs in continuous real-time; the day is punctuated by scheduled
shared bells (opening announcement/events + closing upkeep). Estates self-enforce the
once-per-season limit by **tapping** (exhaust on use, ready-all at season change).

**Reasoning.** Sang asked for two things in tension: "always in motion, real-time seasons"
(a real-time game) and "each estate used once per season" (a per-turn accounting rule). The
enforcement problem: in flowing real-time, what stops a player harvesting the same estate
repeatedly? If the answer is "Control watches," that recreates the surveillance/queue problem
the whole design avoids. **Tapping solves it physically and self-enforcingly** — an exhausted
(rotated/flipped) estate visibly can't be used again, cheating means un-flipping a card in
front of neighbors, and season change readies everything at once. This preserves real-time
flow *and* the per-season cap with zero Control.

But pure real-time dissolves the shared drama (when does the room gasp at the plague, or
gather to vote?). So the **hybrid**: economy flows freely between bells; the bells create the
shared rhythm (a season *turns*, events land, the leaderboard updates, upkeep resolves). Best
of both.

**Upkeep must stay fully parallel and player-run.** At the closing bell, every house
simultaneously counts estates, pays food, readies estates, and resolves any scheduled council
vote — all at its own table, no Control routing. A clumsy Control-bottlenecked upkeep would
cost ~10 min of dead time per season × ~9 seasons ≈ a lost hour and would kill the
"always in motion" feel. Keep upkeep off Control.

---

## L. The day's math (why ~8–10 seasons drives everything)

**Decision.** ~10am–5pm, 30-min lunch, minus a ~30–45 min open (rules + role reading +
house briefings for 50 people) and a ~20–30 min close (scoring + debrief) ≈ **5 hours of
play ≈ 8–10 seasons** at 30–40 min each.

**Reasoning & consequences.** 8–10 turns is a *short* runway, and it constrains hard:
- The economy must produce a **satisfying arc in ~8–10 turns**: ~2–3 seasons to specialize,
  a long middle of alliances/cartels/first threats, and a final season or two decided by the
  last votes and gambits. **Front-load the pressure** — if the economy takes 4 seasons to
  spin up, half the day is warmup. Tune so a house is making meaningful finished-goods money
  by end of season 2 and the first threat is already biting.
- The opening **can't be a cold blank slate**, or you burn a fifth of the game on people
  figuring out what to do. This is *why* pre-existing grudges, starting leanings, and
  individual goals matter so much: every house should sit down already knowing "we're the
  wine family, we hate the Contarini, and I personally want to marry into a noble house," so
  they act on season 1. **Seed the opening state richly** precisely because the clock is
  short.

---

## M. Intrigue — designed to fail gracefully

**Decision.** Secrets/vices as private setup cards; discovery/verification routes through the
council/Ten; assassination + dueling + theft collapse into a *single* family of "aggressive
special actions" with one shared Control resolution path (written intent + spend → target's
protection spend → private die → result slips).

**Reasoning.** Secrets-and-assassination systems most easily overload Control or curdle the
social mood, so they're designed for graceful failure. Vices/secrets mostly self-run
(blackmail and paranoia emerge on their own). The wrinkle is **verification** — a false
accusation must not be a costless weapon, so accusations route through an institution and
carry their own Renown risk. Collapsing three aggressive actions into one resolution path
(rather than three bespoke systems) is essential at 50 players — you cannot have these
resolving ad hoc all over the room.

**Two guardrails that are non-negotiable.**
1. **Attacks hit houses/assets, not benched players.** Assassination should remove an heir,
   cripple an estate, or force a costly succession — *not* sit a human being out for six
   hours. A player with nothing to do for the back half of the day is the worst possible
   outcome.
2. **Frame it up front as houses feuding, not people.** Keeps betrayal fun rather than
   personally sour. Experienced players know this; still worth stating at briefing.

**Secret societies** ride on this same coherent intrigue logic: sparse cross-house
membership, hidden objectives that route through *existing* systems (zealots' alcohol ban =
a council vote; masons' war = threat-track manipulation), and being outed costs house Renown
— the same discovery risk as vices, so the whole intrigue layer feels like one thing rather
than three bolted-on systems.

---

## N. The vote-proposal cost (a worked example of the design method)

**Decision.** Proposing legislation costs a flat **1 Renown**. Never priced by content.
Cost-sharing allowed (multiple players co-pay). Fallback: escalate by *count* within a
season if spam persists.

**Reasoning.** This entry is preserved in detail because it's a clean illustration of *how
decisions get made in this project.* Sang's instinct was to gate vote-spam by making
proposals cost Renown, and to scale the cost by the proposer's Renown. The scaling was
pushed back on, for reasons worth internalizing:
- **Scaling cost by proposer's Renown inverts the intended pressure.** The leader is exactly
  whom the room most wants to constrain and whom the design wants *forced into the arena* —
  but that rule would price the leader *out* of legislating while making it cheap for
  trailers to spam. It also stacks with progressive decay (which already hits the leader
  hardest) into double jeopardy on one house, making leading feel purely punishing.
- **The actual goal was anti-spam**, and the thing to scale is the *proposal or the
  frequency*, not the proposer. A flat fee gates frivolity; escalating-by-count gates spam;
  neither requires Control to *adjudicate* anything (content-pricing a law is an adjudication
  nightmare — every proposer argues their law is minor). **Flat 1, escalate by count only if
  needed.**
- **Cost-sharing** was added because it deepens the politics: trailing houses can pool Renown
  to force a proposal none could afford alone (have-nots banding together, paid in the very
  currency they're short on), and a canny leader might *bribe* someone not to co-sponsor
  (looping the economy back into politics).

The method on display: identify what the mechanic is *actually* trying to achieve, check
whether the proposed implementation points the same way as the rest of the system's
pressures, and prefer the version that needs zero adjudication.

---

## O. Standing tensions / things not yet resolved

1. **Renown-source magnitudes ↔ decay curve** (§B, §F) — the foundational numeric gap; needs
   playtest.
2. ~~**Project guest incentives**~~ — **resolved, see §Q.**
3. **Auction throughput** — sealed-bid vs. open-outcry mix; how the once-per-season land lot
   works.
4. **Regional layout specifics** — region count, estates per region, stewarding, room plan.
5. **Individual-goal / grudge content** — framework agreed (goals sometimes cut against the
   house; grudges seeded asymmetrically); actual content TBD.

---

## P. Meta-principles distilled (the taste of this design)

If you internalize nothing else, hold these — they generated most of the decisions above:
1. **Make the system do the refereeing.** Every time a rule would need a human judgment,
   look for a component, a fixed rate, a market feedback, or an in-fiction actor that can
   carry it instead.
2. **Make pressure emerge from the fiction, aimed by the players.** Clamps that players aim
   at each other (tax the leader, flood a rival's market, out a rival's vice) feel like
   politics; clamps the rules apply feel like rubber-banding.
3. **One resource, many jobs; one path, many flavors.** Renown does three jobs; the market
   track drives three things; aggressive actions share one resolution path. Consolidation is
   a feature — it deepens decisions and shrinks Control load.
4. **Interconnection is the point.** The best ideas here (food, the price track, regional
   tables) each solve multiple problems at once and feed other systems. Favor additions that
   plug into existing systems over new standalone subsystems.
5. **Ship the core; modularize the rest.** Prove the economy + politics + one threat before
   crusades, extra roles, and expansions.

---

## Q. Project guest incentive: the 1-ducat RSVP

**Decision.** Attending a rival house's Project (e.g. a fancy party) costs the representative
**1 ducat**, spent to the **bank** (not to the host), in exchange for a flat **+1 Renown**.
The host separately earns a bonus Renown if enough guest tokens accumulate (threshold TBD).
Fully self-service: the guest deposits a house token + the ducat as physical, visible proof
of attendance, and moves their own Renown marker.

**Reasoning.** This closes the open question from §O — without a payoff, guests have no
reason to attend and the "bonus for good turnout" clause was dead on arrival. The 1-ducat
cost does more than gate the freebie: it turns attendance into a small, direct instance of
the existing wealth→Renown pump (§E, Tier 1), so the new mechanic doesn't need its own
bespoke logic — it's the same conversion the design already relies on, just gated behind
travel time and a party existing to attend.

**The fork that mattered: where does the ducat go?** Sending it to the host would read more
naturally as a literal gift, but it would let a well-attended party partially or fully pay for
itself — quietly deleting the one piece of real uncertainty in the mechanic (will people
actually show up to justify what I spent hosting?). Sending it to the bank instead keeps that
gamble intact: the host's Project spend is a bet on turnout with no guaranteed repayment, which
is exactly the "sinks must be gambles" principle (§3.2) doing its job without needing a
separate rule for it.

**What to watch.** (1) Because attendance costs only a flat, small ducat and travel time, with
no negotiation or risk beyond affordability, watch for two houses simply trading hosting
duties back and forth as a low-friction mutual Renown trickle — probably fine as alliance
behavior, but it's the one corner of this system with no betrayal risk baked in. (2) Because
this is *also* a floor-level Renown source (no goods or production required, just a spare
ducat and a trip), check it against the "protect the floor" guardrail (§D): if showing up to
parties is easier than grinding basic-good donation, a poor house might disengage from the
production economy entirely and live as a professional guest. Not necessarily bad, but worth
watching in playtest.

---

## R. Travel: splitting transit time (unbuyable) from wait time (buyable)

**Decision.** Travel to a region is represented by dedicated components rather than real
room footprint (the play space isn't large enough for walking distance alone to create
meaningful travel time). Each region runs a **public carriage** on a fixed schedule keyed to
the shared room clock, free and uncapped. A **private carriage** costs a flat ducat fee to
depart immediately instead of waiting for the schedule. Either way, the transit itself is
represented by a **sand timer** that must be waited out — paying never skips it.

**Reasoning.** §I.2 calls out travel time as valuable specifically *because* it can't be
bought — the one clamp immune to wealth. A naive "pay a ducat, travel instantly" mechanic
would quietly delete that: if the price is trivial, every house just pays it every time and
the clamp evaporates; if the price is steep enough to matter, wealth is now buying back time
after all, which may be fine but would be a real, unstated departure from §I.2's logic. The
fix that emerged in discussion avoids the dilemma by splitting travel into two separable
costs: the **transit duration** (fixed, universal, embodied by the sand timer, identical for
the poorest and richest house alike) and the **wait for the next scheduled departure**
(elastic, and the only piece that's for sale). This preserves the hard clamp exactly where it
matters — nobody, at any price, gets to skip the timer — while still giving ducats a real,
legible thing to buy: convenience, not time itself.

**Alternatives rejected.**
- *Rely on real walking distance alone* — rejected because the room isn't large enough to
  generate meaningful travel time this way; the clamp would be too weak to matter.
- *A single shared carriage prop that physically shuttles back and forth* — rejected as a
  capacity bottleneck at 40–60 players; individual sand timers referenced against one shared
  clock scale to any number of simultaneous travelers with no shared object to contend over.
- *Staggering carriage departure times across regions* — considered, to prevent a
  synchronized crowd-pulse at the City hub every time the clock hits an even minute, but
  judged unnecessary: only the season-opening bell forces simultaneous movement; routine
  mid-season travel is driven by individual, staggered player decisions. Left as a playtest
  watch-item rather than a preemptive fix — cheap to add later if real play clusters more
  than expected (e.g. everyone reacting to the same event at once).

**What to watch.** (1) Whether the provisional 1-ducat private-fare and the (still
undetermined) sand-timer duration actually produce a felt choice at the table, rather than
the private option being either always-obviously-worth-it or never-worth-it. (2) Whether
carriage-avoidance costs, which scale with trip frequency and therefore with estate count,
meaningfully reinforce the food-upkeep clamp (§I.1) as intended, or feel like a redundant
second tax on the same houses. (3) The hub-crowding assumption above — confirm in playtest
that mid-season travel really does stay staggered.

---

## S. Land vs. developed estates, and the City's convenience premium

**Decision.** The auction (§5) deals in two distinct commodities: **developed estates**
(already built and producing — freshly seeded by Control, or a liquidated estate a house
sold back) and **raw land** (an undeveloped plot the buyer must develop, via the existing
development spend of §4.2, before it produces anything). Neither type is capped per region;
availability and price are the only limits, and Control can throttle either supply line
independently. The **City** region holds both types too, and because City estates cost zero
travel time, they carry a real convenience premium — left unpriced by rule and instead set
by open auction competition, with developing new City land deliberately priced
near-prohibitively.

**Reasoning.** This composes out of pieces the design already has rather than adding new
machinery: the auction already exists, the development spend already exists, and letting
bidding — not a hand-written multiplier — price the City's convenience premium is the same
"make the system do the refereeing" move used everywhere else (§P.1). Splitting "estate" from
"land" as two lot types also gives the estate-liquidation idea (houses sell what they can't
service, §I) somewhere concrete to land: sold-back estates feed the *developed* pool, not a
separate discard.

**The threat-symmetry check that resolved cleanly.** Zero travel cost plus a scarcity-priced
premium could have made City real estate a strictly dominant, no-downside asset class,
undercutting the "high value, high exposure" logic the rest of the anti-runaway stack relies
on (§I). It doesn't, because **The People's "rise up" mechanic (§11.5) already is the City's
localized threat** — structurally equivalent to pirates on the Coast or plague in the Hills,
just not labeled that way originally. No new threat needed; the existing special-role design
already covers this gap.

**What to watch.** (1) "Near-prohibitive" is a relative term that will drift as the ducat
economy inflates or deflates over a session — treat the actual number as a playtest dial like
everything else in §F, not a fixed constant. (2) The People's uprising is a slower-building,
negligence-triggered event rather than a per-season rolled threat — confirm in playtest that
it actually fires often enough to give City-estate holders real exposure, rather than being
rare enough that City real estate is dominant in practice even though it's threatened in
principle.

**Follow-up: three distinct City categories, not one blurred "City land."** The first pass
at this (above) conflated Project-building sites with estates under one "City land" umbrella.
Corrected to three kept-separate things:
- **Production estates** — the *only* thing "estate" means going forward: raw materials and
  processing, full stop. In the City this is mostly Industry (already established in §4.2)
  plus a **rare** exception of actual resource-producing estates (planting, mining, lumber) —
  a deliberate break from "agriculture is mainland-only," and probably the single most
  contested lot type in the game since it stacks zero travel cost on top of raw production,
  something no other estate can claim. Worth seeding rarely and reserving for **open-outcry**
  (§5's still-open throughput question) rather than sealed-bid — exactly the kind of
  everyone-watches moment that format exists for.
- **Plots** — a *separate* category, explicitly not an estate: sites for permanent/
  monument-tier Projects (historical sites, churches, theatres, monuments), auctioned fresh
  each season. This resolves the loose thread from earlier discussion about whether Projects
  need a physical site: permanent ones do (a plot), ephemeral ones (a fancy party) don't and
  can happen at an existing table.
- **Each house's own City residence** — a storage-and-seat home base every house starts with,
  not auctioned, not a production estate, not a plot.

**Why keep the three strictly separate rather than one "City location" type.** Overloading
"estate" to mean anything sitting on City ground would blur the one category (§4.2) the whole
economy is built on — food upkeep, development spend, and the agriculture/industry split all
key off "estate" meaning production. Keeping Plots and the house residence as their own named
things costs nothing and avoids that ambiguity leaking into every other section that
references estates.

**The 3D-printed model idea.** Completing a Project on a plot gets a physical model placed on
it — a strong fit for the design's existing taste for physical, self-enforcing components
(tapped estates, sand-timer carriages, house-token party RSVPs). It needs zero Control
verification (the model is either there or it isn't) and it turns the City table into a
second, physical scoreboard running alongside the Renown leaderboard — the room visibly
watches Venice get built over the course of the day. Purely a production/craft cost, no
mechanical risk.

**Open naming question.** What to call the house's own City residence — floated options
include *Palazzo* (period-appropriate, evocative) — is still unresolved.
