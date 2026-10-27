# A2Companion

Free modular companion for Aion 2. Previously named Aion2SmartMeter.

[Download the latest Companion release](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/latest)

Extract the Companion ZIP, close the previous application completely and run the new EXE. Open **Companion > Modules > Update installed** to update your tools. Character data and preferences are preserved. English, Italian and Estonian are supported.

## Latest: v1.295

- **Shared cleanup fix:** a visit that is still synchronizing no longer incorrectly asks to update the Google script. Reloaded pets reuse capabilities already confirmed in the current session. Wait for Friends to sync and retry cleanup.

- **Startup fix:** the Companion starts with older Games installations. Open Modules and update Games to 1.36. Sleep, live EXP and shared messes are negotiated with the installed module.

- **Games / Mochipi 1.36:** 100 challenge levels with progress filters, notifications and bulk claiming; store inventory, nighttime sleep, smoother animations and performance fixes.
- Visits grant live EXP to both pets, synchronize sleep and messes, and include repeat-visit and farming bonuses. The Friends Google deployment must also be updated.
- Guardian-stage Adventure includes family-specific RPG stats, equipment slots, 45 equipment templates, backpack, upgrades, dismantling and a progressively unlocked bestiary.
- Episode 1 assets and technical foundations cover plains, forest, quarry and the Golem King's fortress, with open regions, dungeon maps, directional sprites and centered transparent treasure chests. **Playable world exploration and combat are not included yet.**
- **Soul Tracking / Collection 1.17:** individual map filter including Verteron and Altgard, with the shared Bootstrap selector style.

[Full release notes and download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/v1.295)

## Modules

Update the Companion before installing new modules. Packages are verified through a signed catalog and SHA-256.

| Module | Version | Release |
|---|---|---|
| Games | 1.36 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/games-v1.36) |
| Market | 1.5 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/market-v1.5) |
| DPS Meter | 1.6 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/dps_meter-v1.6) |
| DPS Check | 1.0 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/dps_check-v1.0) |
| Soul Tracking | 1.17 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/soul_tracking-v1.17) |
| Loot | 1.10 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/loot-v1.10) |
| Eventi | 1.11 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/events-v1.11) |
| Browser | 1.4 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/browser-v1.4) |
| Aion2Pedia | 1.38 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/aion2pedia-v1.38) |

Only Companion releases use **Latest**. The current signed catalog is [`module-repository/catalog-v3.json`](module-repository/catalog-v3.json). Legacy catalogs remain unchanged for older Companion versions.

## Mochipi Friends service

Live EXP, shared messes, synchronized sleep and farming bonuses require the updated Google Apps Script, distributed privately. Redeploy the existing project without changing its URL, properties or spreadsheets and without rerunning setup. [Deployment instructions](server/README.md). Publishing GitHub releases does not redeploy Google Apps Script.

The combat bridge is based on [RATmeter](https://github.com/Kuroukihime/AIon2-Dps-Meter). License information is included in the application archive.
