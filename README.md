# mc-guishop-pricing

A complete, balanced [GUIShop](https://github.com/pablo67340/GUIShop) configuration pack for Minecraft Survival servers (Minecraft 1.26.2, GUIShop 9.4.4+).

## What is this?

This repo contains ready-to-use shop configs for GUIShop — a full vanilla item catalog organized into 15 category shops (blocks, minerals, farming, mob drops, redstone, ocean, nether/end, decorations, tools, armor, enchantments, potions, spawners, custom items, misc), covering 581 items in total.

Prices and limits are researched and balanced rather than guessed:

- Buy/sell ratios kept within a 3:1–5:1 range
- Daily sell limits on easily farmable items to prevent inflation
- `buy-price: false` / `sell-price: false` restrictions on items that shouldn't be tradeable both ways (e.g. spawners can't be bought, enchanted gear/potions/tools can't be sold)
- Pricing based on the official [Minecraft Wiki](https://minecraft.wiki/), survival economy guides, and aggregated community server data (see [`RESEARCH_SOURCES.md`](./RESEARCH_SOURCES.md))

## Structure

| File / Folder | Purpose |
|---|---|
| `menu.yml` | Main shop menu referencing all 15 category shops via `target-shop` |
| `shops/*.yml` | Individual category shop configs (15 files, 581 items) |
| `ITEM_MAPPING.md` | Full catalog of all items, grouped by category and subgroup |
| `RESEARCH_SOURCES.md` | Price research methodology and sources |
| `RULES.md` | Economic balancing rules applied to every item |
| `PROCESSES/` | Repeatable processes for item selection and price research |
| `TEMPLATES/` | Templates used to document item mapping and research sources |
| `CHANGELOG.md` | History of price, category, and rule changes |

## Usage

1. Copy `menu.yml` and the `shops/` folder into your server's `plugins/GUIShop/` directory.
2. Reload or restart GUIShop (or the server).
3. Open the shop in-game, e.g. `/shop` or `/shop open blocks`.

## Customizing

The pack is meant to be adapted to your own server's economy:

- Read [`RULES.md`](./RULES.md) first — it defines the balancing rules (buy/sell ratio, farmability tiers, the `buy-price`/`sell-price: false` rules) that every price follows.
- [`ITEM_MAPPING.md`](./ITEM_MAPPING.md) and [`RESEARCH_SOURCES.md`](./RESEARCH_SOURCES.md) document *why* each item ended up in its category and at its price — use them as a reference before changing values.
- The processes in [`PROCESSES/`](./PROCESSES/) describe how to redo item selection or price research (e.g. for a new Minecraft version).
- Any change (prices, categories, rules) should get an entry in [`CHANGELOG.md`](./CHANGELOG.md) — see the documentation policy in `RULES.md`.

## Compatibility

Built and validated against **Minecraft 1.26.2** and **GUIShop 9.4.4+**. Item IDs may need adjustment for other Minecraft or GUIShop versions.

## License

Licensed under [CC BY-NC-SA 4.0](./LICENSE.md) — free to use, share, and adapt for **non-commercial purposes**, as long as you give credit and share any derivative work under the same license.
