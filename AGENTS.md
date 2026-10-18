# StopStackingMe

Draws one sprite per cargo stack instead of a pile, in the cargo screen, trading, storage, loot
and the refit weapon picker. These instructions apply to this repository, including when it is
opened without the parent mod workspace. The workspace `AGENTS.md` one folder up governs releases,
packaging, Git identity and communication.

## Notion

Tasks and history: the **StopStackingMe board** in Andrzej's Notion, under **Starsector mods**
(`collection://5d60bc22-6ba2-4fc4-a9ae-d903929e50b2`). Working rules and game API notes, including
"Game API: core UI injection": **Claude Information**
(`collection://7bf9b1d6-b9e5-4b62-87f1-757bbaa51919`), starting with "Start here: working on
Starsector mods through Notion". Read the board before working, give every task a ticket (ticket
ids start with SSM) and keep it current. StopStackingMe is also bundled in Coalesced Little Mods:
bring every change over there too. The Notion tools are deferred: load them with ToolSearch first.

## Essentials

- id `stopstackingme`, package `stopstackingme`, Kotlin and Java, Gradle.
- Build: `./gradlew jar` (runs `checkNoForbiddenApis`). Package: stage `StopStackingMe/` with
  `data/`, `graphics/`, `jars/` and the metadata, and write `StopStackingMe.zip`. The root icon
  PNGs are forum art and stay out of the ZIP.
- Hide the extra sprites only (alpha 0 on `row2` and `row3`). Do not switch to the `scaleMult`
  trick: Andrzej chose against it.
- Keep the README short. Do not add a credits or license section back.

## Update metadata

Keep `mod_info.json`, `stopstackingme.version` and `data/config/version/version_files.csv`
consistent. Forum topic 35952.

- updateCheckURL and masterVersionFile:
  `https://raw.githubusercontent.com/andrzejsokolowski/starsector-stopstackingme/main/stopstackingme.version`
- directDownloadURL, asset `StopStackingMe.zip`:
  `https://github.com/andrzejsokolowski/starsector-stopstackingme/releases/latest/download/StopStackingMe.zip`
