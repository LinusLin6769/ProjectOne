# DIY display panel — flat entrance (T-007)
## Goal
A wall-mounted display for the flat entrance. Phase 1: passive info panel showing ProjectOne notes/summaries/briefs. Phase 2 (later): accept input (touch/buttons/voice) so it becomes a two-way interface.
First hardware + software project of this kind for the user — no prior experience assumed.
## Researched approaches
1. **E-ink dashboard — InkyPi** (github.com/fatihak/InkyPi, 4k+ stars, active): Raspberry Pi + Waveshare/Inky e-paper HAT, local web UI for config, plugin system (calendar, weather, AI-generated text, image upload). Paper-like, no backlight/glare, minimal distraction, looks like art rather than a gadget. This is the recommended default for phase 1.
   - Rough cost: Pi Zero 2 W (~$20-30) + Waveshare e-ink HAT 7.3"-13.3" (~$60-160 depending on size/color) + enclosure (3D-printed or a repurposed photo frame, e.g. Ikea Rödalm) + microSD + USB-C PSU ≈ $100-250 total.
   - Limitation: e-ink refresh is slow (~0.5s partial, periodic full refresh needed) — not a good fit for interactive/touch input later.
2. **Self-hosted LCD dashboard — Home Screens** (homescreens.dev): Next.js app on a Pi, 42 built-in modules, drag-and-drop visual editor, Home Assistant integration, no cloud. Regular LCD means no e-ink refresh lag, and it's much easier to bolt on a touchscreen for phase 2 input later.
3. Other prior art worth knowing about (mostly Pi + e-ink variants, useful for enclosure/mounting ideas): Inkycal, MagInkDash (battery-powered Inkplate), jaroz.ink's Infodisplay (custom 3D-printed IKEA-frame backplate), DIY Machines' colour e-ink dashboard build tutorial.
## Recommendation
**Decided (2026-08-29): going with InkyPi on a Raspberry Pi Zero 2 W + Waveshare e-ink HAT for phase 1.** Cheapest, calmest, fastest to ship, and a gentle first hardware project. Revisit the LCD/touchscreen route only once phase-2 input becomes a near-term priority, since switching display technology later means redoing the hardware, not just the software.
## Open decisions needed before ordering hardware
- Budget ceiling.
- Display size (4"–13.3": bigger = more info shown but pricier and harder to source/mount).
- Color vs black & white e-ink.
- Enclosure: 3D-printed, repurposed photo frame, or a bought frame?
- Mounting: wall bracket vs adhesive strips (depends on the flat's walls/tenancy situation).
- How soon phase-2 input is actually wanted — changes the recommended display tech if it's "soon" rather than "eventually".
## Starter parts list (default suggestion, adjust once budget/size are set)
- Raspberry Pi Zero 2 W (~$20-30)
- Waveshare 7.5" e-Paper HAT, black & white (~$60-70) — good balance of readable size and cost for a first build; upgrade to 7.3"/13.3" colour later if wanted
- MicroSD card 16-32GB (~$10)
- USB-C 5V/3A power supply (~$10-15)
- Enclosure: start with a cheap photo frame (e.g. Ikea Rödalm) rather than 3D printing, to avoid needing a 3D printer for a first project
- Est. total: ~$110-140
## Next steps once decisions are made
1. Order hardware.
2. Flash Raspberry Pi OS, enable SPI, install InkyPi.
3. Build/print the enclosure and mount it.
4. Wire up a custom InkyPi plugin that pulls ProjectOne notes/briefs (likely reading from this repo, or a future ProjectOne API) onto the display.
