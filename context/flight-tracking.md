# Flight tracking — London ↔ Taiwan (T-008)
## Trip brief
- Route: London ↔ Taiwan (Taipei). ~2-week holiday, covering the last week of November (this year-end).
- Goal: track fares, flag good deals, initiate purchase once a good one is found (purchase itself needs user approval/payment).
## Open questions (need user input before locking a target)
- Preferred London airport: LHR, LGW, or open to STN/LTN if cheaper?
- Preferred Taipei airport: TPE (Taoyuan, main hub) vs TSA (Songshan, closer to city, fewer long-haul options)?
- Exact date flexibility around "last week of November" — fixed dates yet, or +/- a few days?
- Budget ceiling (return, economy)?
- Direct only, or open to 1-stop for savings?
- Checked bags needed? Just 1 traveler?
## Market snapshot (checked 2026-08-29, via Kayak/momondo/Cheapflights/hotukdeals — indicative, changes daily)
- LHR-TPE direct (China Airlines, ~13-17h): ~£578-£580 return for Nov date pairs (e.g. 13 Nov–1 Dec, 14 Nov–27 Nov).
- LHR/LGW-TPE 1-stop (China Eastern, Air China, Etihad, Shenzhen): commonly £480-£540 return for Nov windows (e.g. Mon 23 Nov–Fri 27 Nov ≈ £491-£495; Thu 5 Nov–Tue 17 Nov ≈ £496-£501).
- LGW-TPE via Beijing (Air China), 1 checked bag incl.: a hotukdeals-posted fare of £323 return for 16 Nov departures (6-13 nights) — expired/time-limited deal, but shows sub-£350 is achievable opportunistically.
- Context: November is not the cheapest month (January tends to be, ~£505-£653 avg return); Nov sits in a moderate band, well below Dec/July peak (~£1,000+).
## Working "good deal" heuristic (refine once budget is known)
- 1-stop return ≤ £480 → flag as a good deal.
- Direct return ≤ £580 → flag as a good deal.
## Tracking process
No persistent daemon exists in this repo — checks happen once per session. Each time this task is picked up:
1. Search current fares for the target date window on LHR/LGW → TPE/TSA (Google Flights, Kayak, momondo).
2. Append a row to the price log below.
3. If a fare meets the "good deal" heuristic, flag it to the user immediately (don't wait for session-end) so they can approve a purchase.
## Price log
| Date checked | Route/dates searched | Price | Airline | Notes |
| 2026-08-29 | LHR/LGW→TPE, various Nov date pairs | £488-£503 (1-stop) / £578-£580 (direct) | China Eastern / Air China / China Airlines | Initial market scan, no fixed dates yet — see open questions |
