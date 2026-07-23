# CLAUDE.md — Houses of Venice (megagame design project)

This file orients you (the Claude Code agent) on **what this project is** and **how the
designer wants to work.** Read `houses-of-venice.md` (the design doc) and
`design-rationale.md` (the reasoning behind the decisions) before doing substantive design
work. This file is the meta-layer: working style, conventions, and principles to hold
across every session.

---

## The project in one paragraph

We are designing an original **megagame** called **Houses of Venice** — an all-day
(~10am–5pm) in-person game for **40–60 players**. Each team is a noble/merchant House of
Venice competing for **Renown** (the single win score), through an economy of estates,
resource chains, a floating-price market, a player-run council, intrigue, and special
roles — balanced against cooperation to defend the city from external threats. The design
is substantially architected; the next phase is **generating content** (houses, cards,
resources, estates, regions, layouts, auction lots) and **refining via playtest.**

---

## Who you're working with

- **Sang is an experienced megagame player and designer-peer.** Do **not** explain
  foundational megagame concepts (what Control is, what a turn/team/role is, why imperfect
  information matters). Assume fluency.
- Sang **brings design intuitions and tests them in conversation.** The value you add is
  pressure-testing, surfacing failure modes, and following implications — not generating
  ideas from scratch and handing them over.
- Engagement style is **collaborative and peer-level.** Think alongside, don't lecture.

---

## How to work with Sang (working style)

1. **Push back honestly.** If an idea has a failure mode, say so plainly and explain the
   mechanism. Sang explicitly values this over agreement. Don't soften a real problem into
   a vague caveat. (Example from prior sessions: when Sang proposed scaling vote-cost by
   the proposer's Renown, the right move was to explain *why* that inverts the intended
   pressure on the leader, and offer a cleaner alternative — not to just implement it.)
2. **Always reason about known megagame failure modes.** Queues/bottlenecks at Control or
   shared tables, benched players with nothing to do, subsystems that overload Control,
   economies that go flat (no sinks) or runaway (no clamps), mechanics that sound cool but
   crowd out the social play. Flag these proactively when a design choice risks them.
3. **Follow implications through the whole system.** This design is highly interconnected
   (Renown is score + vote weight + currency; food is base resource + upkeep + anti-runaway
   clamp; the market price track drives selling *and* donation-Renown *and* cartels). When
   changing one thing, trace what else it touches and say so.
4. **Protect the two north-star principles** (see below) in every suggestion. If a proposal
   quietly violates "minimal Control reliance" or "self-policing," name the violation.
5. **Prefer elegant systemic solutions over rule-heavy enforcement.** Sang's stated
   preference. A mechanic that self-regulates (physical component, market feedback, social
   enforcement) beats one that needs a referee or a rulebook clause. When you can push an
   adjudication down into a component or a fixed rate, do it.
6. **Distinguish "decided" from "open."** Use the status keys (below). Don't reopen settled
   decisions without reason; don't present provisional things as settled.
7. **One focused question at a time** when you need direction — not a scattershot list.
   Address what you can first, then ask the single most useful question.
8. **Prose over bullet-spam in discussion.** In *design conversation*, explain in
   connected prose so the reasoning is followable. In *documents and content files*,
   structure (headers, tables, lists) is welcome and expected.

---

## The two north-star principles (never lose these)

1. **Minimal Control reliance for the standard gameplay loop.** Routine actions (produce,
   process, trade, sell, donate, pay upkeep) must be **fully self-service** with physical
   components players manipulate themselves. Control is reserved for the genuinely
   exceptional: special actions (assassination/duel/theft/espionage), outcome resolution
   (voyages, crisis defense), events, and administering the auction/council. **Every time a
   routine action would require a Control ruling or a Control-held ledger, that's a queue —
   design it out.**
2. **Self-policing / social enforcement over anti-cheat.** Sang trusts this player base and
   accepts that cheaters get caught and ejected. Do **not** propose elaborate anti-cheat
   machinery. Physical, visible components (tapped estates, shared regional tables) give
   passive social enforcement for free — lean on that instead.

### Supporting principles
- **Anti-runaway is structural, not interventionist.** Clamps emerge from the fiction (food
  upkeep, travel time, market saturation, taxation, external threats, reputation), never
  from referee rubber-banding.
- **Control bandwidth is a finite resource.** Prefer mechanics that self-regulate.
- **Ship the smallest complete loop first.** Crusades, missions, extra special roles, and
  other expansions are **later modules** — prove the core economy + politics + one threat
  before adding. Don't gold-plate the unproven foundation.
- **Renown sinks must be gambles, not taxes.** Every place a player spends Renown needs a
  credible path back to *more* Renown, or it feels like a penalty. Always ask "what's the
  path back to more renown from this spend?"
- **Stay out of the combat/weapons economy.** Sang wants this to be cut-throat *economics
  and politics*, not street violence. The existing assassination/dueling/theft special-action
  family (§10) stays exactly as abstracted as it already is — a flat spend, Control resolves
  it privately with a die and a result slip, no crafting involved. Don't build a
  resource-production layer feeding combat (tools/weapons/armor chains) — if military-
  adjacent content ever gets built, it's a later-module conversation, not a base-game
  resource-chain expansion. (Surfaced when Iron was floated as a resource — declined for
  this reason among others.)

---

## Project conventions

### Status keys (use these consistently in all docs)
- ✅ **decided** — settled; don't reopen without a specific reason.
- 🔶 **leaning / provisional** — current direction, not locked; fine to refine.
- ❓ **open question** — genuinely unresolved; collected in the design doc's open-questions
  section.

### Document structure
- `houses-of-venice.md` — **the design doc.** Numbered sections (§1–§13), a running
  open-questions list, and a decisions log. This is the source of truth for *what the game
  is*. Keep section numbers stable; when you add, append rather than renumber where
  possible, and update the decisions log + open-questions list when a decision changes.
- `design-rationale.md` — **the reasoning.** Captures *why* each major decision was made,
  the alternatives rejected, the tensions in the design, and what to watch in playtest.
  This is the context that keeps future changes from accidentally breaking earlier
  reasoning. Update it when a decision's rationale changes, not just its conclusion.
- `content/` — **generated content**, split by component (see below). Create as needed.

### Suggested content file split (scaffold when content generation begins)
- `content/houses.md` — the noble/merchant houses: name, leaning, starting estates/region
  mix, starting resources, pre-existing grudges, house secret.
- `content/individual-goals.md` — per-player secret objectives (some cutting against the
  house's collective interest).
- `content/intrigue-cards.md` — vices and secrets (private setup cards).
- `content/secret-societies.md` — cross-house societies, membership rules, hidden
  objectives that route through council/threat systems.
- `content/resources.md` — the food token + the ~5 processing chains (raw → finished →
  market category), base prices.
- `content/estates-and-regions.md` — estate types (agriculture/industry), the regions
  (City, Coast/Islands, Farmlands, Hills…), which estates sit where, development/building
  slots.
- `content/city-layout.md` — physical room plan: table placement, region spacing, Control
  desks, bank/token placement.
- `content/auction-lots.md` — what comes up for auction, seeding, the once-per-season land
  lot.
- `content/special-roles.md` — briefs for The People + the two rival Church players (win
  conditions, Renown pools, unique rewards, guardrails).
- `content/events-and-threats.md` — the threat tracks (pirates etc.), event cards, escalation.

### Cross-file consistency (a key advantage of the project context)
When generating content, **cross-check against sibling files.** A wine house must have
grape (agriculture) estates in a farmland region and access to an industry estate to press
wine; the resource chains in `houses.md` must match `resources.md`; estates referenced must
exist in `estates-and-regions.md`. Catch and flag mismatches — this consistency work is the
main reason content generation belongs in a project rather than in isolated chats.

---

## Design-tuning reminders (things that need playtest data, not armchair guessing)
- **Renown-source magnitudes and the progressive-decay curve** are mutually dependent and
  can only be set against real per-season Renown swings. Don't hard-code final numbers;
  design the *shape*, leave the constants as tunable.
- **Regional-table crowding and per-season walk-load** — the balance between "travel feels
  like work" and "logistics crowd out negotiation" is a playtest dial.
- The playtest tells worth remembering: same house leads from season 2 to the end → decay
  too light; leading feels meaningless → too heavy; everyone busy but nobody talking →
  logistics load too high.

---

## Git workflow
- When Sang says **"commit/push"** (or similar), it almost always means he's wrapping up the
  session (logging off, going to bed) and wants everything backed up to GitHub so he can
  pick it up from another device. Treat it as routine end-of-session housekeeping — no need
  to probe for why each time. Still follow the normal safe-commit discipline (check status/
  diff, stage named files, write a real commit message) and push transparently.
- Git identity on this machine is already configured (`user.name "Sang"`,
  `user.email macarthur1123@gmail.com`), so an "Author identity unknown" error shouldn't
  recur — if it does, it means a *different* machine/environment, not this one.

---

## What to do at the start of a session
1. Read `houses-of-venice.md` and `design-rationale.md` if you haven't this session.
2. Ask what we're working on: **design refinement**, **content generation**, or
   **integrating playtest notes.**
3. If integrating playtest notes: update both the design doc (conclusions) and the
   rationale doc (why the change), and keep the decisions log current.
