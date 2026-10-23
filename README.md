# Gemstones

## Description

Gemstones is a Minecraft plugin that adds precious stones — ruby, sapphire, pearl, hessonite and others — as findable, tradeable goods.

Vanilla has two gems, and both are currency-by-accident: diamond is a tool material and emerald is a villager token. Neither is a *treasure*. Gemstones adds stones whose only purpose is to be rare, to be worth something, and to be traded — which is what a roleplay economy actually needs out of a gem.

This plugin was proposed from a Kingdom: First Era player request on 2026-09-04.

## Project Status

**Pre-implementation.** The repository holds a buildable, empty plugin skeleton; no gameplay features exist yet. The scope of the first release is defined in [MVP.md](MVP.md).

## Planned Features

- A roster of named gemstone items — ruby, sapphire, pearl, hessonite, amber and onyx — each with its own lore line and rarity tier
- Gems as drops from mining stone and as loot in generated structures
- A configurable rate for every gem source
- An operator command to give gems, for events and for seeding a market
- One documented item-appearance strategy, shared with [Conquest-Recipes](https://github.com/Dans-Plugins/Conquest-Recipes)

Gems have no crafting use and Gemstones sets no prices: pricing is left to [Merchants](https://github.com/Dans-Plugins/Merchants).

## Installation

Not yet released. Once released, installation will follow the usual DPC pattern: drop the jar in `plugins/` and restart. It will also be available through [Dan's Plugin Manager](https://github.com/Dans-Plugins/Dans-Plugin-Manager).

### Development builds

Each merge to `main` that changes more than documentation is published as a rolling `dev` prerelease. It is unreleased, unreviewed code — at this stage an empty skeleton with no gameplay — and should not be run on a server without a backup. To opt in with Dan's Plugin Manager:

```
/dpm get gemstones --experimental
```

Return to published releases with `/dpm get gemstones --stable`.

### Building from source

Requires JDK 21.

```bash
./gradlew clean build
```

The jar is written to `build/libs/`.

### Dependencies

None. Designed to pair with [Medieval Economy](https://github.com/Dans-Plugins/Medieval-Economy) and [Merchants](https://github.com/Dans-Plugins/Merchants), and to share an item-appearance strategy with [Conquest-Recipes](https://github.com/Dans-Plugins/Conquest-Recipes).

## Usage

### Documentation

- [MVP](MVP.md) – Scope of the first release, and its deliberate non-goals

`USER_GUIDE.md`, `COMMANDS.md`, `CONFIG.md` and `CHANGELOG.md` land with the first release, per [DOCUMENTATION_PRACTICES.md](https://github.com/Dans-Plugins/dpc-conventions/blob/main/docs/DOCUMENTATION_PRACTICES.md).

## Support

You can find the support Discord server [here](https://discord.gg/xXtuAQ2).

### Experiencing a bug?

Please fill out a bug report [here](https://github.com/Dans-Plugins/Gemstones/issues/new).

## Contributing

This repository follows the standards in [dpc-conventions](https://github.com/Dans-Plugins/dpc-conventions).

## License

This project is licensed under the [GNU General Public License v3.0](LICENSE).

See the [LICENSE](LICENSE) file for full details.
