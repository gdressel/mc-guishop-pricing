# Changelog

Alle nennenswerten Änderungen an diesem Config-Paket werden hier dokumentiert.

Das Format orientiert sich an [Keep a Changelog](https://keepachangelog.com/de/1.0.0/).

---

## [Unreleased]

## [1.1.0] - 2026-09-29
### Changed
- **Schema-Korrektur:** Das gesamte Config-Paket referenzierte bisher ein erfundenes "GUIShop 15.4+"-Schema, das im echten Plugin nie existiert hat. Umstellung auf das reale Schema von [pablo67340/GUIShop](https://github.com/pablo67340/GUIShop) (aktuelle Version 9.4.4, api-version 1.13):
  - `shops.yml` → `menu.yml` (Hauptmenü verweist jetzt über `target-shop` auf die Kategorie-Shops, statt in einer fiktiven zentralen Datei alle Items zu referenzieren).
  - `material` → `id`, jeder Item-Eintrag bekommt zusätzlich `type: SHOP`.
  - `buy`/`sell` → `buy-price`/`sell-price`; Deaktivierung erfolgt über `false` statt über den Sentinel-Wert `-1`.
  - `name` → `shop-name`, `lore` → `shop-lore`.
  - Slot ist jetzt der Map-Key des Items selbst (kein separates `slot:`-Feld mehr); Items liegen unter `pages: PageN: items:` statt lose unter `items:`.
- **Entfernt (keine Entsprechung im echten Plugin):** `fill-item`, `buy-stack`/`sell-stack: 64`.
- **`daily-limit-sell` konvertiert:** GUIShop erzwingt keine Tageslimits. Der bisherige Wert wird jetzt als reiner Hinweistext in `shop-lore` dokumentiert (z. B. `&8Server-Richtwert: max. 2000/Tag verkaufen`), ohne technische Wirkung.
- Alle 581 Items 1:1 aus dem alten Schema übernommen (keine Item- oder Preisänderungen).
- **Betroffene Dateien:** `menu.yml` (neu, ersetzt `shops.yml`) und alle 15 `shops/*.yml`.
- Dokumentation (`README.md`, `RULES.md`, `PLAN-generate-config-pack.md`, `PROGRESS.md`) auf das reale Schema und GUIShop 9.4.4+ aktualisiert.

## [1.0.1] - 2026-09-29
### Fixed
- `shops/blocks.yml` war unvollständig (nur 51 von 140 in `ITEM_MAPPING.md` gelisteten Items). Datei komplett aus `ITEM_MAPPING.md` neu generiert:
  - Alle 16 fehlenden Wolle-Farbvarianten ergänzt (`BLUE_WOOL`, `BROWN_WOOL`, `CYAN_WOOL`, ...).
  - Alle 16 fehlenden gefärbten Glas-Varianten ergänzt (`BLACK_STAINED_GLASS` ... `YELLOW_STAINED_GLASS`).
  - Alle 14 fehlenden Beton-/Trockenbeton-Varianten ergänzt.
  - Alle 15 fehlenden Terrakotta-Farbvarianten ergänzt.
  - Alle 15 fehlenden Holz-Varianten ergänzt (restliche Planks-Sorten, alle `STRIPPED_*_LOG`).
  - Alle 16 fehlenden Sonderstein-Blöcke ergänzt (u. a. `BRICKS`, `MUD_BRICKS`, Sandstein-Familie, Deepslate-Ziegel/Fliesen, `CRYING_OBSIDIAN`).
  - Shop von 2 auf 5 Seiten erweitert, Slot-Zuordnung nach Subgruppen (Steine → Hölzer → Glas → Beton → Terrakotta → Wolle) neu sortiert.
- **Ergebnis:** `blocks.yml` deckt jetzt 140/140 Items aus `ITEM_MAPPING.md` ab (vorher 51/140, 36 %).

## [1.0.0] - 2026-09-27
### Added
- Erstversion für Minecraft 1.26.2 / GUIShop 15.4+.
- Alle 15 Shop-Kategorien (`blocks`, `minerals`, `farming`, `mobdrops`, `redstone`, `ocean`, `nether_end`, `decorations`, `tools`, `armor`, `enchantments`, `potions`, `spawners`, `custom_items`, `misc`).
- Zentrale `shops.yml` mit Referenzen auf alle Kategorien.
- `ITEM_MAPPING.md`: vollständiger Item-Katalog (581 Items) inkl. Farmbarkeit und Subgruppen.
- `RESEARCH_SOURCES.md`: Preis-Recherche-Dokumentation und Quellenbewertung.
- `RULES.md`: Ökonomische Balance-Regeln (Buy/Sell-Ratio, Farmbarkeit, `-1`-Regeln, Stack-Größen).
