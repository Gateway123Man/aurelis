# Aurelis

> **Your world, in a new light.**

Aurelis is an independent, local-first **Minecraft: Java Edition launcher and Fabric client**, currently in development.

**Status: pre-alpha.** There is no public download yet. This repository is the official public information hub and website for the project.

- **Website:** https://YOUR-USERNAME.github.io/aurelis/
- **Privacy policy:** [PRIVACY.md](PRIVACY.md) · [privacy.html](privacy.html)
- **Contact:** [GitHub Issues](https://github.com/YOUR-USERNAME/aurelis/issues) · mvpthespear1st@gmail.com

---

## What is Aurelis?

Aurelis is being built as a focused desktop launcher with an optional in-game Fabric client. The goal is not to be the loudest client on the market. It is to be a clean, reliable place to manage Minecraft installations, accounts, mods, worlds, and servers — with a HUD that is useful, configurable, and fair.

The launcher is designed around isolated profiles. Each profile can have its own Minecraft version, mod loader, game directory, Java runtime, memory allocation, resolution, JVM arguments, mods, and HUD layout. Nothing is shared unless you choose to share it.

Aurelis is **not affiliated with Mojang Studios, Microsoft, Fabric, Modrinth, or any other third party**. Minecraft is a trademark of Mojang Synergies AB.

---

## Planned and in-development capabilities

### Accounts and profiles
- Microsoft account sign-in using the OAuth 2.0 device-code flow.
- Multiple legitimate Microsoft accounts with secure switching.
- No Microsoft passwords are ever requested or stored.
- Refresh tokens stored in the operating system credential vault.
- Isolated profiles for Vanilla, Fabric, Quilt, Forge, and NeoForge where those loaders are available.
- Per-profile game directory, Java runtime, memory, resolution, JVM arguments, and launch options.

### Mods and modpacks
- Modrinth search, installation, updates, and dependency resolution.
- Enable/disable mods without deleting them.
- Duplicate, missing-dependency, loader, and version compatibility checks.
- Mod collection import and export.
- `.mrpack` modpack installation with hash and path validation.
- Config and mod-folder backups before changes.

### Client and HUD
- An optional Fabric client with fair-play HUD modules: CPS, keystrokes, FPS, ping, coordinates, direction, armor, potions, scoreboard styling, crosshair, zoom, stopwatch, clock, hit/combo counters, target HUD, and waypoints.
- HUD Studio with a live preview, drag-and-drop positioning, resizing, colors, fonts, opacity, backgrounds, rounded corners, and shadows.
- Multiple saved layouts, import/export, share codes, and per-server overrides.
- Local, client-only capes and cosmetic previews, clearly labelled as client-only.

### Worlds, servers, and utilities
- World scanning, icons, backups, restore, duplicate, and quick-play.
- Server list with groups, favourites, descriptions, icons, status ping, and quick connect.
- Per-server profile and HUD configuration.
- Screenshot manager, resource-pack and shader-pack file management, replay detection where supported, and keybind editing.

### Diagnostics and performance
- Crash detection with log and crash-report analysis.
- Missing dependency, Java version, mixin, and duplicate-mod hints with honest confidence levels.
- One-click repair that re-downloads only missing or corrupted managed files.
- Temporary Safe Mode for diagnosing mod problems.
- Real performance options and recommendations — not invented FPS promises.
- Session playtime and launch history stored locally.

---

## Fair play

Aurelis is a fair-play project.

- No kill aura, reach, aim assist, hitbox expansion, packet manipulation, or anti-cheat bypass.
- HUD modules only display information the game already provides.
- Optional modules can be disabled per server.
- Client-only cosmetics are explicitly labelled and are not represented as visible to other players.
- Aurelis will not help bypass Minecraft authentication, licensing, or server rules.

---

## Security and privacy

- Microsoft OAuth device-code flow: sign-in happens in your browser; Aurelis never sees your password or MFA codes.
- Refresh tokens are stored in the OS credential vault (Windows Credential Manager, macOS Keychain, or Linux Secret Service).
- Downloads are HTTPS-only and verified with published hashes where available.
- ZIP extraction is protected against path traversal.
- No telemetry or analytics by default.
- Game data, profiles, logs, and session statistics stay on your device unless you export them.
- Crash reports are generated locally and are never uploaded automatically.

Read the full [privacy policy](PRIVACY.md).

---

## Technology

The planned stack:

- **Desktop shell:** Tauri 2
- **Frontend:** React 19, TypeScript, Vite, Tailwind CSS
- **Backend:** Rust, Tokio, SQLite
- **Minecraft integration:** Mojang metadata, Microsoft/Xbox/Minecraft authentication, Fabric/Quilt metadata, official Forge/NeoForge installers where required
- **In-game client:** Fabric mod targeting Minecraft 26.3 initially
- **Content:** Modrinth API, official Mojang launcher content

The launcher and the in-game client are separate components. The launcher manages installations, authentication, downloads, profiles, and launching. The Fabric mod handles in-game HUD modules and client-side features.

---

## Roadmap

1. **Foundation** — app shell, design system, local data, settings, logging.
2. **Minecraft core** — metadata, downloads, Java management, vanilla installation, launching, Microsoft authentication.
3. **Mods, worlds, servers** — Modrinth, modpacks, compatibility checks, world backups, server ping and quick connect.
4. **Client and HUD** — Fabric client, HUD modules, HUD Studio, layouts, cosmetics.
5. **Diagnostics and beta** — crash analysis, repair, Safe Mode, signed builds, documentation, public beta.

No dates are promised. The project will publish a build only when the core systems are genuinely usable.

---

## About this repository

This repository is the public information hub for Aurelis. It contains:

- `index.html` — the project landing page
- `privacy.html` — the website version of the privacy policy
- `PRIVACY.md` — the repository version of the privacy policy
- `README.md` — this document

The launcher source code may be published separately. The website is intentionally self-contained: no external fonts, scripts, trackers, or images.

---

## Disclaimer

Aurelis is an independent project. It is not affiliated with, endorsed by, or associated with Mojang Studios, Microsoft, Fabric, Modrinth, Adoptium, or any other third party. “Minecraft” is a trademark of Mojang Synergies AB. All other product names are used for identification only.

Third-party services have their own terms and privacy policies. Aurelis does not grant any rights to third-party content, trademarks, or assets.

---

## License

Website content © 2026 Aurelis. The Aurelis name, logo, and visual identity are project branding. No permission is granted to reuse the branding. The source-code license will be announced separately.
