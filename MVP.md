# Gemstones — MVP

## Problem

Players asked for gems: "Diamond, emerald, pearl, Ruby, hessonite". Two of those already exist and are already spoken for — diamond makes tools, emerald buys villager trades. What is missing is a class of item that is purely valuable: something to find, hoard, gift, tax and trade, with no crafting use to anchor its price.

## Target environment

Spigot, Minecraft 26.1, **vanilla clients**.

**The appearance question decides this plugin's shape**, and it is shared with [Conquest-Recipes](https://github.com/Dans-Plugins/Conquest-Recipes). That plugin builds its 73 medieval items by setting a display name and lore on a vanilla material and setting **no `CustomModelData`** — so without a resource pack that keys off item name, a "Steel Longsword" is a renamed iron sword. Gemstones faces exactly the same choice and must not answer it differently, or the server ends up running two incompatible item conventions.

## The smallest shippable slice

### v1 does

1. **A gem roster.** Named items for stones vanilla lacks — ruby, sapphire, pearl, hessonite, amber, onyx — each with its own lore line and rarity tier. Diamond and emerald are left alone; they already have jobs.
2. **Sources.** Gems drop from mining stone at configurable, low, per-gem rates, and appear in generated-structure loot. Rare enough to be an event, common enough that a mining session can produce one.
3. **Configuration** for every rate, so an operator can tune the whole economy from one file.
4. **A give command** for operators, for events and for seeding a market.
5. **One appearance strategy, documented**, chosen deliberately and matching whatever Conquest-Recipes settles on.

### v1 does not

- **Ship a resource pack.** See the open question — but v1 must work, and be worth installing, with no pack at all.
- **Add gem ores or worldgen.** Custom ore blocks mean either new blocks (impossible on a vanilla client without a pack) or reskinned existing ones, plus a worldgen pass. Drops-from-stone gets the same economic effect for a fraction of the work, and does not require a world reset to take effect on existing terrain.
- **Add socketing, enchanting, or gem-powered gear.** That is an entire second plugin, and it would give gems a crafting use — destroying the "purely valuable" property that is the point.
- **Add gem tools or armour.**
- **Set prices, or contain any economy logic.** Gems are goods. [Merchants](https://github.com/Dans-Plugins/Merchants) prices them.
- **Add cutting, polishing or quality tiers.**

## Why these non-goals

A gem is only worth something because it is scarce and useless. The moment a ruby is a crafting ingredient, its price is set by whatever it crafts, and it stops being treasure. v1's job is to introduce scarcity correctly and then stay out of the way.

Skipping worldgen is also what makes this installable mid-season rather than only at a world reset.

## Open questions

- **`CustomModelData` or display-name matching?** Conquest-Recipes uses display names, which historically worked through OptiFine's Custom Item Textures. `CustomModelData` works with a plain server-pushed resource pack and no client mod. If the server ever pushes its own pack, `CustomModelData` is the better road — and Conquest-Recipes would want the same change. **Decide this once, for both plugins.**
- Which base material for each gem? An unpacked ruby that is visibly a redstone dust reads worse than one that is visibly an emerald in the wrong colour.
- Should this simply be part of Conquest-Recipes instead of a separate plugin? Its `ItemStackService` already does most of the work, and there is a real argument that "named medieval items" wants one home. Kept separate here because gems are economy goods with rarity and drop rates, not craftables — but this is worth revisiting before code is written.
- Hessonite is an unusual ask and a real garnet variety. Worth keeping the roster to stones a player can picture.

## Dependencies

None. Pairs with [Medieval Economy](https://github.com/Dans-Plugins/Medieval-Economy) and [Merchants](https://github.com/Dans-Plugins/Merchants).
