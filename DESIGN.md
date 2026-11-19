# DESIGN.md: Revan (@roulettegun) Portfolio

## Identity & Character
- **Owner:** Revan (`@roulettegun`, `@revanganteng.site`)
- **Domain:** Systems tooling, Luau/Lua static analysis, Roblox runtime security auditing, and macOS debugging utilities.
- **Voice & Personality:** Direct, technical, zero-fluff engineering dossier. Speaks in concrete capabilities (`mmap` offset indexes, 64-bit PCG32 PRNG simulation, zero-dependency Python standard library tools) rather than abstract adjectives.
- **Identity Motif:** Architectural index markers (`[01]`, `[02]`, `[RCD-120K]`) paired with crisp `1px solid` structural hairlines and an editorial serif/sans/mono triad.

## Dials
- `Dial: ENERGY 2 / RHYTHM 3 / MOTION 1`
- **ENERGY 2 (Balanced):** High typographic contrast and structural clarity without theatrical noise.
- **RHYTHM 3 (Varied):**
  - Section 00 (Header & Hero): Asymmetric two-column dossier header with direct jump actions and live telemetry strip.
  - Section 01 (Flagship Spotlight : `rcdebug`): Full-width architectural deep-dive with real dual screenshots (`roblox-devconsole.jpg` and `cli-listener.jpg`) and interactive audit-vector tabs (`--client`, `--server`, `--catalog`).
  - Section 02 (Static Deobfuscation Engine : `LUA-Deobfuscater`): Split specification table and interactive algorithm filter across the 7 unpacking engines (`prometheus_vm`, `rolling_xor_table`, `seeded_prng_cipher`, etc.) plus actual tool output screenshot (`lua-deobfuscater.png`).
  - Section 03 (Live Repository & Gist Ledger): Searchable, language-filterable live index wired to the GitHub REST API (`api.github.com/users/roulettegun/repos`) with explicit Loading, Empty, and Error states and a manual state simulator for resilience verification.
- **MOTION 1 (Calm):** Instantaneous or crisp hover/focus states only; zero looping animations, zero floating elements, full respect for `prefers-reduced-motion: reduce`.

## Color System (2 Core + 1 Accent)
All pairings verified with `contrast-check.py` for WCAG AA compliance (4.5:1 normal text, 3.0:1 large text and non-text UI boundaries):

### Dark Theme (Default : justified by macOS terminal & developer tool domain, R-21)
- **Canvas Primary (`--bg`):** `#111110` (Carbon Ink)
- **Canvas Elevated (`--surface`):** `#1A1A18` (Graphite Plate)
- **Text Primary (`--fg`):** `#F4F2EE` (16.90:1 on `--bg`, 15.59:1 on `--surface`)
- **Text Secondary (`--fg-muted`):** `#B4B1A9` (8.82:1 on `--bg`, 8.14:1 on `--surface`)
- **Structural Hairline / Control Border (`--border-strong`):** `#82807A` (4.65:1 on `--bg`, passing 3:1 non-text contrast)
- **Subtle Rule (`--border-subtle`):** `#2E2E2B` (decorative divider paired with spatial layout)
- **Deliberate Accent (`--accent`):** `#ED5A42` (Signal Vermilion : 5.53:1 on `#111110`, 5.10:1 on `#1A1A18`)

### Light Theme (Full parity toggle, R-21 & R-34)
- **Canvas Primary (`--bg`):** `#F4F2EE` (Warm Archival Paper)
- **Canvas Elevated (`--surface`):** `#EAE7E1` (Stone Plate)
- **Text Primary (`--fg`):** `#111110` (16.90:1 on `--bg`, 15.31:1 on `--surface`)
- **Text Secondary (`--fg-muted`):** `#4E4D49` (7.57:1 on `--bg`, 6.86:1 on `--surface`)
- **Structural Hairline / Control Border (`--border-strong`):** `#6D6B66` (4.76:1 on `--bg`, passing 3:1 non-text contrast)
- **Subtle Rule (`--border-subtle`):** `#D5D1C8`
- **Deliberate Accent (`--accent`):** `#B82914` (Archival Vermilion : 5.58:1 on `#F4F2EE`, 5.06:1 on `#EAE7E1`, 6.24:1 with `#FFFFFF` text)

## Typography (Written Reasons, R-06 & R-31)
- **Display & Section Headings:** `'Instrument Serif', Georgia, serif` : gives the portfolio a distinct editorial Monograph identity that breaks away from generic SaaS developer templates.
- **Body & UI Controls:** `'Plus Jakarta Sans', -apple-system, BlinkMacSystemFont, sans-serif` : clean geometric legibility at small sizes for dense technical descriptions and table cells.
- **Code, Flags & Identifiers:** `'JetBrains Mono', ui-monospace, SFMono-Regular, monospace` : restricted strictly to actual CLI commands, flags (`--client`, `--algo`), file paths, and commit/rule identifiers (`RCD-000001`), never used for large decorative headings.

## One-Line Decision Log (R-31)
- **Why this color palette?** Warm archival paper (`#F4F2EE`) and carbon ink (`#111110`) with a single signal vermilion accent (`#B82914` / `#ED5A42`) evoke technical hardware manuals and avoid AI blue-purple gradients (R-01, R-29).
- **Why this layout?** Each section takes the shape of its actual content: a dual-screenshot tabbed breakdown for `rcdebug`, an interactive 7-engine matrix for `LUA-Deobfuscater`, and a filterable live ledger for GitHub repositories (R-05, C-3).
- **Why this typography?** Pairing an editorial serif display face with a high-legibility sans body and strict monospace code blocks separates prose narrative from executable syntax (R-06).
- **Why this spacing?** Fluid spacing via `clamp()` creates deliberate density shifts between the expansive hero and the compact technical tables while scaling cleanly to mobile viewports (R-03, R-05).
- **Why no uniform feature cards?** Projects differ in depth and evidence, so the flagship tool gets a full-width architectural showcase while smaller utilities sit in a structured ledger (R-14).
- **Why no decorative icons or badges?** Every visual asset is either a real screenshot from the repository (`roblox-devconsole.jpg`, `cli-listener.jpg`, `lua-deobfuscater.png`) or functional UI feedback (R-04, R-09, R-22).
