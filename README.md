# A2Companion

Free modular companion for Aion 2. Previously named Aion2SmartMeter.

[Download the latest Companion release](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/latest)

Extract the Companion ZIP, close the previous application completely and run the new EXE. Open **Companion > Modules > Update installed** to update your tools. Character data and preferences are preserved. English, Italian and Estonian are supported.

## Latest: v1.271

- Mochipi has a compact Pet Store, larger item icons, right-aligned prices, a 50,000 Kinah medical kit and a visit countdown beside the pet name. Installing Games automatically installs Loot if missing.
- Persistent poop and translucent green vomit can be cleaned with a brush cursor. Messes affect care stats until removed. New sleeping poses, nap bonuses and dreams extend pet care.
- Friends supports search, expandable groups and removal. Last-known lists remain available during temporary service failures. Visits include shared purchases, floating EXP, reward summaries and early returns with proportional rewards and a 20% penalty.
- Morning/day/night scenery follows local time. The hourly exchange market sits beside the resource panel and updates after offline periods.
- Fixed auto-hide crashes and window restoration. Module windows support edge snapping while shared monitor edges remain free. Event timers have expandable, reorderable categories and drag previews.

[Full release notes and download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/v1.271)

## Modules

Update the Companion before installing the new modules. Packages are verified through a signed catalog and SHA-256.

| Module | Version | Release |
|---|---|---|
| Games | 1.16 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/games-v1.16) |
| Market | 1.5 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/market-v1.5) |
| DPS Meter | 1.6 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/dps_meter-v1.6) |
| DPS Check | 1.0 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/dps_check-v1.0) |
| Soul Tracking | 1.14 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/soul_tracking-v1.14) |
| Loot | 1.10 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/loot-v1.10) |
| Eventi | 1.11 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/events-v1.11) |
| Browser | 1.4 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/browser-v1.4) |
| Aion2Pedia | 1.38 | [Download](https://github.com/panparsifaluniverse/Aion2SmartMeter/releases/tag/aion2pedia-v1.38) |

Only Companion releases use **Latest**. The current signed catalog is [`module-repository/catalog-v3.json`](module-repository/catalog-v3.json). Legacy catalogs remain unchanged for older Companion versions.

## Mochipi Friends service

New social features require the updated [Google Apps Script](server/A2Companion.gs). Redeploy the existing project without changing its URL, properties or spreadsheets and without rerunning setup. [Deployment instructions](server/README.md). Updating Companion does not redeploy Google Apps Script automatically.

The combat bridge is based on [RATmeter](https://github.com/Kuroukihime/AIon2-Dps-Meter). License information is included in the release ZIP and repository [LICENSE](LICENSE).
