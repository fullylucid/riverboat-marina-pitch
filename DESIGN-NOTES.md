# Riverboat Marina — design notes (draft 1, 2026-11-20)

## The object (law 6): the site IS the signpost at the gate
The timber sign at 106 W. Brannan Island Rd (client photo `img/gate-sign.webp`) already does the
site's job: it names the marina, lists the businesses inside, and advertises berths by length.

| Sign device | Site component |
|---|---|
| Arched stained-timber crown board, routed white caps | header bar + hero `h1` (`.crown`) |
| Stacked white boards in spruce frames, each in its tenant's own lettering | hero directory (`.board` b-heavy / b-slab / b-script), "Inside the gate" cards (`.tenant` t-*) |
| Green BERTHS swing sign + hanging 30′/35′/40′/50′ tags | header `.tag-cta`, hero `.swing`, rate filter `.sizes` (radio tags + `:has()`) |
| Black "106" address plate | `.addr`, history `.year` plates |
| Manila rope rail between posts | `.rail` dividers |
| Flower planter at the base | `.planter`, footer `.planter-band` |

Palette sampled from that photo (median-cut per component): timber `#342C29`/`#1F1917`, board frame
`#323D3C`, swing sign `#42615A`, board white `#F4F4F7`, rope `#B9BC95`, geranium `#C23A31`.
Engraved motif: tules + great blue heron (the client's rookery, 100+ nests), one drawing reused by crop.

Layout cues from the brief's references: Korth's Pirates Lair (split nav over full-bleed aerial,
heritage block, amenities, location/hours footer) and Alameda Marina (persistent reserve button,
live conditions strip, slip-rate table with effective date, date-led event cards — reserved for phase 2).
Korth's is a direct competitor at 169 W. Brannan Island Rd: structure borrowed, look not.

## Live element (law 4)
Next high/low tide from NOAA CO-OPS station 9415229 (harmonic, ~200 m from the docks; named by number,
not by its NOAA name, which is the competitor's harbor) + air/wind from Open-Meteo. Keyless, CORS-open.
Seeded figures in markup; terminal states: green "Live · updated" / amber "Indicative figures".

## Sources & facts to confirm with the client (do not ship to production unconfirmed)
- **Moore's Riverboat Restaurant was destroyed by arson on 2022-07-06** (CBS Sacramento, Latitude 38).
  Their live site still advertises it. This draft treats it as history only; the client decides how
  the timeline acknowledges 2022.
- Rate card is the most recent published (effective 2018-05-01). Source lists dry-storage units as
  "25′ and 35′" in prose but 25′/30′ in the table; the table is used.
- Tenant list (Delta Boat Works, Rubicon Yachts, Custom Marine, DTDF office) is as published in 2013;
  Rubicon's own site no longer mentions the marina. The 2013 sign also shows Pacific Yacht Imports.
- The Wheelhouse clubroom (parties up to 25): confirm it survived the fire / is in use.
- "Family" ownership since 1984 is stated as history only; current ownership not verified.
- Swing sign reads INQUIRE, not AVAILABLE, until availability is confirmed.
- Map pin uses the client's own 2013 Google embed point (38.09983, −121.56681). Third-party
  listings (marinas.com) put the marina's pin on Korth's mobile-home park — verified against OSM +
  imagery; do not "correct" to those.

## Phase two slots (planned, not built — MD-Q-2026-005 is a draft)
Leasing portal → behind the BERTHS tag / `#berths` inquiry · event booking → the Wheelhouse CTA ·
tenant login/payments → footer link · bait shop → an "Inside the gate" board. Each currently routes to
phone/email, so they attach without restructuring.

## Gate evidence (draft 1)
Width law PASS 390/834/1280 (chromium) · axe-core 0 violations at all three · CLS 0.0000 load and
after scroll cycle (390, 4× CPU, slow network, 3 runs) · LCP ~0.8 s · JS off complete · reduced motion:
0 animations, 0 hidden reveals · feeds blocked → amber, seeded figures · impeccable 3.3.1: only the
documented body overflow-x backstop (`.impeccable/config.json`). WebKit capture not run on this box
(missing system libs) — verify on Schyler's iPad Safari.
