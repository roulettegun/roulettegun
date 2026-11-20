# Revan · `@roulettegun`

macOS developer tools, Luau/Lua static analysis, and Roblox security utilities.

[![Portfolio: roulettegun.github.io](https://img.shields.io/badge/PORTFOLIO-roulettegun.github.io-0d1117?style=for-the-badge&labelColor=21262d)](https://roulettegun.github.io)
[![Web: pretty.rich/revan](https://img.shields.io/badge/WEB-pretty.rich%2Frevan-0d1117?style=for-the-badge&labelColor=21262d)](https://pretty.rich/revan)
[![PyPI: rcdebug](https://img.shields.io/badge/PYPI-rcdebug-0d1117?style=for-the-badge&labelColor=21262d)](https://pypi.org/project/rcdebug/)
[![Email: oscrevan@gmail.com](https://img.shields.io/badge/EMAIL-oscrevan%40gmail.com-0d1117?style=for-the-badge&labelColor=21262d)](mailto:oscrevan@gmail.com)

---

### `[01]` Flagship Projects

#### [rcdebug](https://github.com/roulettegun/rcdebug)
[![PyPI version](https://badgen.net/pypi/v/rcdebug?color=0d1117&labelColor=21262d)](https://pypi.org/project/rcdebug/)
[![Python compatibility](https://badgen.net/pypi/python/rcdebug?color=0d1117&labelColor=21262d)](https://pypi.org/project/rcdebug/)
![Dependencies: stdlib-only](https://badgen.net/badge/deps/stdlib-only/0d1117?labelColor=21262d)
[![Last commit](https://badgen.net/github/last-commit/roulettegun/rcdebug?color=0d1117&labelColor=21262d)](https://github.com/roulettegun/rcdebug/commits)

Command-line debugger and security scanner for Roblox games on macOS (`pip install rcdebug`). Built strictly on the Python 3 standard library. It streams live client errors while you play (`--client`), checks `.rbxlx` place files and Luau scripts for unsafe remotes or receipt vulnerabilities (`--server`), and searches a 120,000-entry flaw index in under 10ms (`--catalog`).

#### [LUA-Deobfuscater](https://github.com/roulettegun/LUA-Deobfuscater)
![Runtime: Python 3](https://badgen.net/badge/runtime/Python%203/0d1117?labelColor=21262d)
![Mode: static-only](https://badgen.net/badge/mode/static-only/0d1117?labelColor=21262d)
![Dependencies: stdlib-only](https://badgen.net/badge/deps/stdlib-only/0d1117?labelColor=21262d)
[![Last commit](https://badgen.net/github/last-commit/roulettegun/LUA-Deobfuscater?color=0d1117&labelColor=21262d)](https://github.com/roulettegun/LUA-Deobfuscater/commits)

Static unpacker and constant-folder for obfuscated Lua 5.1 and Luau scripts (`lua_deobfuscator.py`). Reconstructs readable source code from Prometheus VMs, rolling-XOR string tables, seeded PRNG ciphers, and nested `loadstring` wrappers directly on disk without running untrusted code.

---

### `[02]` Repository & Gist Index

| Project | Stack | Summary |
| :--- | :--- | :--- |
| [SillyRAT-Remastered](https://github.com/roulettegun/SillyRAT-Remastered) | `Python 3` | macOS compatibility update fixing payload builders, socket polling loops, and terminal output. |
| [WristTok](https://github.com/roulettegun/WristTok) | `Swift` | watchOS app built around a custom TikTok feed parser. |
| [antigravity-skills](https://github.com/roulettegun/antigravity-skills) | `Markdown` | Reusable agent skills and workflow rules for Google Antigravity. |
| [gist:crossover.sh](https://gist.github.com/roulettegun/4d5ea45bc5afce9c71404358a3cd4a66) | `POSIX Shell` | macOS helper script for CrossOver. |
