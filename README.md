# Revan (@roulettegun)

Systems tooling, Luau/Lua static analysis, and macOS runtime debugging.

- **Portfolio & Live Repository Ledger:** [roulettegun.github.io](https://roulettegun.github.io)
- **Web:** [pretty.rich/revan](https://pretty.rich/revan) · `@revanganteng.site`
- **PyPI:** [pypi.org/project/rcdebug](https://pypi.org/project/rcdebug/)
- **Contact:** [oscrevan@gmail.com](mailto:oscrevan@gmail.com)

---

### `[01]` Flagship Tool: [rcdebug](https://github.com/roulettegun/rcdebug)

macOS command-line debugger and security auditor for Roblox games (`pip install rcdebug`). Zero external dependencies; built strictly on the Python 3 standard library.

- **Live Client Bridge (`--client`):** Binds a local HTTP/WebSocket listener on `127.0.0.1:8765` (with automatic fallback to `8766`), copies the client diagnostic payload to the macOS clipboard via `pbcopy`, and tails `~/Library/Logs/Roblox/*_last.log` for `[rcdebug-wire:*]` frames.
- **Static Server & StudioMCP Audit (`--server`):** Scans local `.luau`/`.lua` scripts, `.rbxlx` place files, or an open Roblox Studio session over StudioMCP for exposed remotes, unanchored physics parts, `loadstring()` sinks, missing `ProcessReceipt` deduplication, and unvalidated `OnServerEvent` listeners.
- **120,000-Flaw `mmap` Index (`--catalog`):** Sub-10ms binary offset search across `RCD-000001` through `RCD-120000` plus 120 static Luau diagnostic probes (`LDP-001` to `LDP-120`).

---

### `[02]` Static Analysis: [LUA-Deobfuscater](https://github.com/roulettegun/LUA-Deobfuscater)

Zero-dependency Python static unpacker and constant-folder for obfuscated Luau and Lua 5.1 scripts (`lua_deobfuscator.py`). Tokenizes and resolves obfuscated scripts without running untrusted code:

| Engine | Target Pattern | Resolution Method |
| :--- | :--- | :--- |
| `prometheus_vm` | Prometheus Medium / Strong VM presets | Solves custom Base64/ASCII85 Layer-1 tables, extracts 45-bit LCG + mod 257 PRNG constants, and annotates VM dispatch leaves. |
| `prometheus_strings` | Prometheus Weak / Constant-Array presets | Solves Layer-1 tables, inlines index offsets, strips decoder headers, and folds arithmetic expressions. |
| `rolling_xor_table` | IIFE Rolling-XOR tables (`bit32.bxor`, `(K + i + j) % 256`) | Recovers rolling XOR keys with UTF-8 scoring fallback, prunes honeypot `do ... end` blocks, and inlines string arrays. |
| `seeded_prng_cipher` | Custom pure-Lua LCG or `math.randomseed(S)` | Resolves custom LCG loops and simulates Luau's bit-exact 64-bit PCG32 PRNG engine. |
| `loadstring_packer` | `loadstring("...")()`, `string.char(...)` payloads | Unwraps nested `loadstring` layers and byte XOR/add/sub loops up to 5 layers deep. |
| `constant_array` | String array queue rotation packers | Simulates `table.insert` / `table.remove` rotations and resolves index offsets. |
| `math_expression` | Bitwise, string-byte, and arithmetic obfuscation | Precedence-exact constant folding for `math.*`, `bit32.*`, `string.*`, and concatenations. |

---

### `[03]` Public Repository & Gist Index

| Repository | Stack | Summary |
| :--- | :--- | :--- |
| [roulettegun/rcdebug](https://github.com/roulettegun/rcdebug) | Python 3 / Luau | macOS command-line debugger and security auditor for Roblox games ([PyPI](https://pypi.org/project/rcdebug/)). |
| [roulettegun/LUA-Deobfuscater](https://github.com/roulettegun/LUA-Deobfuscater) | Python 3 / Luau | Static unpacker, PRNG solver, and constant-folder for obfuscated Lua 5.1 and Luau scripts. |
| [roulettegun/SillyRAT-Remastered](https://github.com/roulettegun/SillyRAT-Remastered) | Python 3 | macOS-compatible ("Darwin") remaster fixing payload generation, `recv_data()` spin loops, and terminal color output. |
| [roulettegun/WristTok](https://github.com/roulettegun/WristTok) | Swift (watchOS) | Apple Watch client built around a scraped TikTok API. |
| [roulettegun/antigravity-skills](https://github.com/roulettegun/antigravity-skills) | Markdown / Skills | Curated collection of agent skills for Google Antigravity. |
| [gist:crossover.sh](https://gist.github.com/roulettegun/4d5ea45bc5afce9c71404358a3cd4a66) | POSIX Shell | macOS shell utility script (`crossover.sh`). |
