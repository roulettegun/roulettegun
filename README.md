# Revan (@roulettegun)

I build macOS developer tools, Luau/Lua code analyzers, and Roblox debugging utilities.

[![Portfolio](https://img.shields.io/badge/Portfolio-0D1117?style=for-the-badge&logo=github&logoColor=white)](https://roulettegun.github.io)
[![Web](https://img.shields.io/badge/pretty.rich%2Frevan-111111?style=for-the-badge&logo=safari&logoColor=white)](https://pretty.rich/revan)
[![PyPI rcdebug](https://img.shields.io/badge/PyPI_rcdebug-3775A9?style=for-the-badge&logo=pypi&logoColor=white)](https://pypi.org/project/rcdebug/)
[![Contact](https://img.shields.io/badge/oscrevan%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:oscrevan@gmail.com)

![Python 3](https://img.shields.io/badge/Python_3-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Luau / Lua](https://img.shields.io/badge/Luau_%2F_Lua-2C2D72?style=for-the-badge&logo=lua&logoColor=white)
![macOS](https://img.shields.io/badge/macOS-000000?style=for-the-badge&logo=apple&logoColor=white)
![Swift](https://img.shields.io/badge/Swift-F05138?style=for-the-badge&logo=swift&logoColor=white)
![POSIX Shell](https://img.shields.io/badge/POSIX_Shell-121011?style=for-the-badge&logo=gnu-bash&logoColor=white)

---

### `[01]` Flagship Tool: [rcdebug](https://github.com/roulettegun/rcdebug)

[![PyPI version](https://badgen.net/pypi/v/rcdebug)](https://pypi.org/project/rcdebug/)
[![Python compatibility](https://badgen.net/pypi/python/rcdebug)](https://pypi.org/project/rcdebug/)
![Dependencies: Zero](https://badgen.net/badge/dependencies/zero/green)
![Platform: macOS](https://badgen.net/badge/platform/macOS/black)
[![Last commit](https://badgen.net/github/last-commit/roulettegun/rcdebug)](https://github.com/roulettegun/rcdebug/commits)

A macOS command-line debugger and security scanner for Roblox games (`pip install rcdebug`). It uses only the Python 3 standard library, so you can install and run it without third-party packages.

- **Live Game Inspection (`--client`):** Starts a local server on `127.0.0.1:8765` (or `8766` if busy), copies a small diagnostic script to your macOS clipboard via `pbcopy`, and watches your local Roblox logs (`~/Library/Logs/Roblox/*_last.log`) to catch errors and events while you play.
- **Place & Script Security Check (`--server`):** Checks `.luau` and `.lua` scripts, `.rbxlx` place files, or an active Roblox Studio session for common security mistakes. It flags unprotected remote events, unanchored parts, unsafe `loadstring()` calls, and purchase handlers (`ProcessReceipt`) that could process the same receipt twice.
- **Fast Flaw Lookup (`--catalog`):** Searches a built-in index of 120,000 known flaw patterns (`RCD-000001` to `RCD-120000`) and 120 Luau code checks (`LDP-001` to `LDP-120`) in under 10 milliseconds using memory-mapped files (`mmap`).

---

### `[02]` Static Analysis: [LUA-Deobfuscater](https://github.com/roulettegun/LUA-Deobfuscater)

![Runtime: Python 3](https://badgen.net/badge/runtime/Python%203/blue)
![Dependencies: Zero](https://badgen.net/badge/dependencies/zero/green)
![Execution: Static Only](https://badgen.net/badge/execution/static-only/orange)
[![Last commit](https://badgen.net/github/last-commit/roulettegun/LUA-Deobfuscater)](https://github.com/roulettegun/LUA-Deobfuscater/commits)

A Python tool (`lua_deobfuscator.py`) that unpacks and cleans up obfuscated Luau and Lua 5.1 scripts. It reads and simplifies the code directly on disk without running it, keeping your machine safe from untrusted scripts:

| Engine | What It Targets | How It Cleans the Code |
| :--- | :--- | :--- |
| `prometheus_vm` | Prometheus Medium / Strong VM presets | Decodes scrambled Base64/ASCII85 lookup tables, recovers random number generator constants, and labels virtual machine instructions. |
| `prometheus_strings` | Prometheus Weak / Constant-Array presets | Decodes string tables, puts hidden strings back into their actual code positions, removes decoder boilerplate, and simplifies math expressions. |
| `rolling_xor_table` | Rolling-XOR string tables (`bit32.bxor`) | Finds the XOR encryption keys automatically, strips out fake trap code blocks (`do ... end`), and restores readable strings. |
| `seeded_prng_cipher` | Seeded random number ciphers (`math.randomseed`) | Solves custom random number loops and simulates Luau's 64-bit `PCG32` random generator to decrypt scrambled text. |
| `loadstring_packer` | Nested `loadstring("...")()` and `string.char(...)` wrappers | Peels back up to 5 layers of nested `loadstring` wrappers and byte-level math loops. |
| `constant_array` | Shuffled string arrays | Reverses `table.insert` and `table.remove` array rotations to put strings back in their real order. |
| `math_expression` | Scrambled math and bitwise formulas | Calculates `math.*`, `bit32.*`, `string.*`, and joined strings ahead of time and replaces them with plain values. |

---

### `[03]` Public Repositories & Gists

| Project | Status / Badges | Stack | What It Does |
| :--- | :--- | :--- | :--- |
| [roulettegun/rcdebug](https://github.com/roulettegun/rcdebug) | [![PyPI](https://badgen.net/pypi/v/rcdebug)](https://pypi.org/project/rcdebug/) [![Commits](https://badgen.net/github/commits/roulettegun/rcdebug)](https://github.com/roulettegun/rcdebug) | Python 3 / Luau | macOS command-line debugger and security scanner for Roblox games. |
| [roulettegun/LUA-Deobfuscater](https://github.com/roulettegun/LUA-Deobfuscater) | [![Commits](https://badgen.net/github/commits/roulettegun/LUA-Deobfuscater)](https://github.com/roulettegun/LUA-Deobfuscater) ![Static](https://badgen.net/badge/mode/static/orange) | Python 3 / Luau | Unpacks and simplifies obfuscated Lua 5.1 and Luau scripts without running them. |
| [roulettegun/SillyRAT-Remastered](https://github.com/roulettegun/SillyRAT-Remastered) | [![Commits](https://badgen.net/github/commits/roulettegun/SillyRAT-Remastered)](https://github.com/roulettegun/SillyRAT-Remastered) ![macOS](https://badgen.net/badge/platform/macOS/black) | Python 3 | macOS-compatible update that fixes payload building, high-CPU network loops (`recv_data()`), and terminal colors. |
| [roulettegun/WristTok](https://github.com/roulettegun/WristTok) | [![Commits](https://badgen.net/github/commits/roulettegun/WristTok)](https://github.com/roulettegun/WristTok) ![watchOS](https://badgen.net/badge/platform/watchOS/orange) | Swift | Apple Watch app built around a custom TikTok feed scraper. |
| [roulettegun/antigravity-skills](https://github.com/roulettegun/antigravity-skills) | [![Commits](https://badgen.net/github/commits/roulettegun/antigravity-skills)](https://github.com/roulettegun/antigravity-skills) ![Skills](https://badgen.net/badge/format/SKILL.md/purple) | Markdown | Collection of workflow and coding skills for Google Antigravity. |
| [gist:crossover.sh](https://gist.github.com/roulettegun/4d5ea45bc5afce9c71404358a3cd4a66) | ![Gist](https://badgen.net/badge/gist/crossover.sh/black) | POSIX Shell | macOS shell utility script for CrossOver. |
