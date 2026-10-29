# A2Companion

Free modular companion for Aion 2. Previously named Aion2SmartMeter.

[Download the latest Companion release](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/latest)

Extract the Companion ZIP, close the previous application completely and run the new EXE. Open **Companion > Modules > Update installed** to update your tools. Character data and preferences are preserved. English, Italian and Estonian are supported.

## Latest: v1.312

- **Games / Mochipi 1.52:** playable card-battle training across four biomes, a fanned hand extending outside the battle window, red cooldown counters and animated critical hits.
- Family-specific unlockable skills, stage-4 specials, team support, one-turn shields and 33 distinct sound effects. Choose cards in the pet skills window before starting an encounter.
- Compact movable squad panel, loading centered on the Adventure window and a cozy results screen showing the current player's pet EXP preview.
- Gentler global stat-upgrade prices, displayed once below the growth-fragment balance. Existing points and balances are preserved.
- Party browser with public/private groups, organizer approval, member removal and readiness. GM redemption interface and GM Candy evolution item.
- **Online party requirement:** the dedicated Battles service must be privately redeployed with **rules 2** by its owner. Until then, use local training. Publishing these releases does not deploy Google Apps Script.
- **Training awards no rewards:** battle EXP, fragments and loot are previews, including in parties. World exploration remains separate from these training encounters.
- Update Companion first, then open **Modules > Update installed** and install **Games 1.52**.

[Full release notes and download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/v1.312)

## Modules

Update the Companion before installing new modules. Packages are verified through a signed catalog and SHA-256.

| Module | Version | Release |
|---|---|---|
| Games | 1.52 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/games-v1.52) |
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
