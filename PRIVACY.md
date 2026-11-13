# Aurelis Privacy Policy

**Last updated:** 13 November 2026
**Applies to:** the Aurelis desktop launcher, the Aurelis Fabric client mod, and this website.

Aurelis is an independent, local-first project. This policy explains exactly what is stored, what leaves your device, and what does not. It is written to be read, not to hide things.

If something here is unclear, contact **mvpthespear1st@gmail.com**.

---

## The short version

- Aurelis has **no telemetry and no analytics**.
- Your Microsoft password is **never** requested, seen, or stored.
- Account tokens are stored in your operating system's credential vault, not in plain files.
- Profiles, worlds, mods, logs, screenshots, and playtime stay **on your device**.
- Crash reports and logs are **never uploaded automatically**.
- The only network requests are the ones needed to do what you asked: sign in, download game files and mods, check server status, and fetch metadata.
- This website uses **no cookies, no trackers, and no external scripts**.

---

## 1. Who is responsible

Aurelis is an independent project maintained by its developer. For any privacy question, request, or complaint, contact **mvpthespear1st@gmail.com**.

Aurelis is **not affiliated with** Mojang Studios, Microsoft, Fabric, Modrinth, Adoptium, or any other third party. Those services have their own privacy policies, which apply when you use them through Aurelis.

---

## 2. What Aurelis stores on your device

Aurelis uses its own managed data directory. It does not read or copy account data from other launchers.

### 2.1 Account information

| Data | Where it is stored | Why |
| --- | --- | --- |
| Microsoft account identifier (UUID) | Local database | To tell accounts apart |
| Minecraft profile name and UUID | Local database | Display and launch arguments |
| Account skin and cape URLs | Local cache | Display in the launcher |
| OAuth refresh token | OS credential vault | To keep you signed in without re-authenticating |
| OAuth access token | Memory only | Short-lived; used for API calls and launch |
| Token expiry timestamps | Local database | To refresh before expiry |

The refresh token is stored using the operating system credential store:

- **Windows:** Credential Manager (DPAPI-protected)
- **macOS:** Keychain
- **Linux:** Secret Service (GNOME Keyring, KWallet, or equivalent)

If the credential vault is unavailable, Aurelis will tell you rather than silently writing the token to a plain file.

**Aurelis never stores:** your Microsoft password, MFA codes, recovery codes, or payment information. Sign-in happens on Microsoft's own pages in your browser.

### 2.2 Profiles and game data

Stored locally, under the Aurelis data directory:

- Profiles: name, Minecraft version, mod loader and loader version, game directory, Java path, memory settings, resolution, JVM and game arguments, mod list, HUD layout.
- Game files, libraries, assets, and Java runtimes downloaded for each installation.
- Mods, resource packs, shader packs, and modpack files you install.
- Worlds and world backups you create.
- Server entries: name, address, port, group, favourite flag, notes, and per-server overrides.
- HUD layouts and module settings.
- Screenshots and logs produced by the game.
- Launch history and session playtime.
- Launcher settings, including theme and accent colour.

### 2.3 Diagnostics

- Launcher logs and game logs are written locally.
- Crash analysis runs locally on those logs.
- Diagnostic reports are only created when you explicitly export them.
- Exported reports redact account tokens, session identifiers, and access tokens before writing.

### 2.4 What Aurelis does not collect

Aurelis does not collect or transmit: your name, email address, IP-based location profiles, device fingerprint, contact list, browsing history, keystrokes outside the game, clipboard contents, or files unrelated to Minecraft.

---

## 3. What leaves your device, and when

Aurelis only makes network requests needed for a feature you used. Every outbound request falls into one of these categories.

### 3.1 Microsoft and Xbox authentication

When you add or refresh an account, Aurelis contacts Microsoft identity and Xbox Live endpoints to complete the OAuth 2.0 device-code flow and obtain Minecraft access.

- Data sent: your OAuth request, device code, and refresh token.
- Data received: access tokens and your Xbox/Minecraft account identifiers.
- Microsoft's privacy statement: https://privacy.microsoft.com/privacystatement

The device-code flow means you enter a code on Microsoft's website in your browser. Aurelis never handles your password.

### 3.2 Mojang and Minecraft services

To install and launch the game, Aurelis contacts Mojang/Microsoft services for:

- Version manifests and asset indexes
- Library and asset downloads
- Java runtime metadata
- News and patch notes shown in the launcher
- Your Minecraft profile, entitlements, and skins

Launching the game sends a normal Minecraft session request, as any launcher does.

### 3.3 Mod and modpack sources

- **Modrinth:** search, project metadata, version files, and `.mrpack` downloads. Requests include the search terms and project identifiers you use. See https://modrinth.com/legal/privacy.
- **CurseForge:** only if you configure an API key and use CurseForge features. See https://www.curseforge.com/legal/privacy.
- **Fabric, Quilt, Forge, NeoForge metadata:** loader versions and installer information.

Aurelis does not send your account tokens to mod sources. Downloads are fetched over HTTPS and verified against published hashes where the source provides them.

### 3.4 Server status and quick connect

When you refresh a server entry, Aurelis sends a standard Minecraft server-list ping to that server's address. That server will see your IP address, exactly as it would if you added it in the vanilla client. Aurelis does not ping servers in the background; pings happen when you request them or open the Servers page.

### 3.5 Update checks

If update checks are enabled, Aurelis requests a version manifest from the configured release endpoint. No account data is included.

### 3.6 Optional community features

If a future version offers a community layout gallery or similar service, it will be **opt-in**, will identify itself clearly, and will be described in an updated version of this policy before it is enabled. Aurelis will not turn such a feature on silently.

---

## 4. This website

This website is a set of static files. It contains:

- No cookies
- No analytics or tracking scripts
- No advertising
- No external fonts, images, or JavaScript
- No forms that submit data to us

The site is served by a hosting provider (for example, GitHub Pages), which may keep standard web server logs such as IP address, user agent, and requested page for security and operational purposes. Aurelis does not receive or analyse those logs.

If you email the project, your message and email address are used only to reply to you.

---

## 5. Sharing

Aurelis does not sell, rent, or share personal data. There is no data broker, advertising network, or analytics vendor involved.

Data leaves your device only in the cases described in section 3, or when **you** choose to export or share it — for example, exporting a diagnostic report, a HUD layout, or a mod list.

If you publish an exported file publicly, it is your responsibility to check what it contains.

---

## 6. Retention and deletion

Local data is kept until you delete it.

- **Remove an account** in Settings to delete its stored refresh token from the credential vault and its metadata from the local database.
- **Delete a profile** to remove its configuration; you choose whether to also delete its game directory.
- **Clear logs** or delete the Aurelis data directory to remove logs and caches.
- **Uninstalling** the launcher does not always remove the data directory or credential entries. Aurelis provides an in-app option to remove local data on uninstall where the platform allows it.

Because Aurelis has no server-side account database, there is no remote copy of your data to request or delete. Requests about data held by Microsoft, Mojang, Modrinth, or a Minecraft server must go to those providers.

---

## 7. Security

Aurelis takes the following measures:

- OAuth 2.0 device-code flow; no password handling.
- Refresh tokens in the OS credential vault.
- Access tokens kept in memory and excluded from logs.
- HTTPS for all network requests.
- Hash verification of downloads where the source publishes hashes.
- ZIP extraction that rejects path traversal and unexpected absolute paths.
- Redaction of tokens and session data in exported diagnostics.

No system is perfectly secure. If you believe you have found a vulnerability, please report it privately to **mvpthespear1st@gmail.com** rather than opening a public issue with exploit details.

---

## 8. Children

Aurelis is not directed at children under 13. It does not knowingly collect personal information from anyone. Because the launcher has no server-side user database, it does not build profiles of its users.

Minecraft accounts are Microsoft accounts, and Microsoft's own age requirements apply.

---

## 9. Your choices

- Use Aurelis without signing in, if you only need local features that do not require an account.
- Decline update checks.
- Avoid Modrinth or CurseForge features if you do not want those requests made.
- Remove accounts and delete local data at any time.
- Keep diagnostics on your device and never export them.

---

## 10. Changes to this policy

If this policy changes, the "Last updated" date at the top will change, and material changes will be described in the project's release notes or on this website.

If a future feature would send new categories of data off your device, it will be opt-in and disclosed before it is enabled.

---

## 11. Contact

**Email:** mvpthespear1st@gmail.com
**Repository:** https://github.com/Gateway123Man/aurelis
**Website:** https://Gateway123Man.github.io/aurelis/

---

Aurelis is an independent project. It is not affiliated with, endorsed by, or associated with Mojang Studios, Microsoft, Fabric, Modrinth, Adoptium, or any other third party. "Minecraft" is a trademark of Mojang Synergies AB.
