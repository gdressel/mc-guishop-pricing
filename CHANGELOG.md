# Changelog

Alle nennenswerten Änderungen an diesem Config-Paket werden hier dokumentiert.

Das Format orientiert sich an [Keep a Changelog](https://keepachangelog.com/de/1.0.0/).

---

## [1.2.0] - 2026-10-01
### Changed
- Autoren-/Datums-Metadaten aus Docs entfernt — wird jetzt über Git-Historie abgedeckt.

### Fixed
- Phantom-Items, falsche Preisbänder und fehlerhafte Quellenangaben in `RULES.md`/`RESEARCH_SOURCES.md` korrigiert.
- `-1`-Sentinel durchgängig auf `false` migriert (Altlast vor dem echten GUIShop-Schema).
- Farmbarkeit mehrerer AFK-farmbarer Items (`ENDER_PEARL`, `NETHER_STAR` u. a.) korrigiert.
- Erfundene Minecraft-Version "1.26.2" repo-weit auf das reale `26.3`-Schema korrigiert; `menu.yml`-Lore zeigte zudem noch veraltete `-1`-Sentinel an.
- **Kritisch:** `enchantments.yml`/`potions.yml` nutzten nicht existierende Material-IDs (z. B. `SHARPNESS_5_BOOK`) — auf reales GUIShop-Schema (`ENCHANTED_BOOK`+`enchantments:`, `POTION`+`potion-info:`) umgestellt.

## [1.1.0] - 2026-09-29
### Changed
- **Schema-Korrektur:** Umstellung vom erfundenen "GUIShop 15.4+"-Schema auf das reale Schema von [pablo67340/GUIShop](https://github.com/pablo67340/GUIShop) 9.4.4 (`menu.yml` statt `shops.yml`, `id`/`buy-price`/`sell-price`/`shop-name`/`shop-lore` statt `material`/`buy`/`sell`/`name`/`lore`, `pages: PageN: items:`-Struktur). Keine Item- oder Preisänderungen.

## [1.0.1] - 2026-09-29
### Fixed
- `shops/blocks.yml` war unvollständig (51/140 Items) — vollständig aus `ITEM_MAPPING.md` neu generiert, jetzt 140/140.

## [1.0.0] - 2026-09-27
### Added
- Erstversion für Minecraft 1.26.2 / GUIShop 15.4+.
- Alle 15 Shop-Kategorien (`blocks`, `minerals`, `farming`, `mobdrops`, `redstone`, `ocean`, `nether_end`, `decorations`, `tools`, `armor`, `enchantments`, `potions`, `spawners`, `custom_items`, `misc`).
- Zentrale `shops.yml` mit Referenzen auf alle Kategorien.
- `ITEM_MAPPING.md`: vollständiger Item-Katalog (581 Items) inkl. Farmbarkeit und Subgruppen.
- `RESEARCH_SOURCES.md`: Preis-Recherche-Dokumentation und Quellenbewertung.
- `RULES.md`: Ökonomische Balance-Regeln (Buy/Sell-Ratio, Farmbarkeit, `-1`-Regeln, Stack-Größen).
