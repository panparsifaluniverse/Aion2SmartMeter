# A2Companion

Free modular companion for Aion 2. Previously named Aion2SmartMeter.

[Download the latest Companion release](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/latest)

Extract the Companion ZIP, close the previous application completely and run the new EXE. Open **Companion > Modules > Update installed** to update your tools. Character data and preferences are preserved. English, Italian and Estonian are supported.

## Latest: v1.314

- **DPS Meter:** boss encounter duration freezes when the boss dies, even if a secondary target remains active. Verified against a recorded Nuakum fight and the packaged EXE; 85 tests cover timing, resets, metrics and archives.
- **Games 1.53:** expiring GM Gift codes support unlimited recipients, once per person. Interrupted deliveries remain recoverable after expiry; single-use codes remain available.
- Clearer redemption messages for expired codes and incompatible service versions.
- Update Companion first, then open **Modules > Update installed** and install **Games 1.53**. The DPS fix requires the new Companion EXE.
- Expiring gifts require a private Battles service update by its owner, setupGifts and redeployment. Publishing these releases does not deploy Google Apps Script; private scripts are not included.
- Mochipi battle training still awards no EXP, items or growth fragments.

[Full release notes and download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/v1.314)

## Modules

Update the Companion before installing new modules. Packages are verified through a signed catalog and SHA-256.

| Module | Version | Release |
|---|---|---|
| Games | 1.53 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/games-v1.53) |
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
