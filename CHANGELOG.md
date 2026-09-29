# Changelog

Alle nennenswerten Änderungen an diesem Config-Paket werden hier dokumentiert.

Das Format orientiert sich an [Keep a Changelog](https://keepachangelog.com/de/1.0.0/).

---

## [Unreleased]
### Fixed
- **`RESEARCH_SOURCES.md` enthielt mehrere fabrizierte/fehlerhaft zugeschriebene Quellen:** Bei einer Überprüfung (Verdacht auf KI-Halluzination durch den ursprünglichen Autor "Antigravity AI") stellte sich heraus, dass zwei der drei zitierten Kern-Praxisquellen (35 % + 15 % Gewichtung) nicht existieren bzw. falsch beschrieben waren, und ein ganzer Abschnitt (Tier-1–4-Matrix) fälschlich dem Minecraft Wiki zugeschrieben wurde.
  - **Quelle "Mineseed Economy Guide" (`mineseed.net/economy`):** URL existiert nicht (Domain nicht erreichbar). Ersetzt durch die echte Quelle `docs.mineseed.org/mineseed/the-official-price-guide` — mit korrigierter Beschreibung (Mindestpreis-Floor-System für Chestshops, kein Buy/Sell-Ratio-Modell wie ursprünglich behauptet).
  - **Quelle "SpigotMC / Paper Economy Aggregate" (`spigotmc.org/forums/economy`):** Existiert nicht — SpigotMC hat keinen Economy-Diskussionsbereich, nur eine Plugin-Download-Kategorie. Ersetzt durch `minecraft-economy-price-guide.net` (verzion's/Biggsen's community-gepflegte Preisdatenbank, 1800+ Items, mit Quellcode-Link).
  - **Abschnitt 3 (Tier-1–4-Preismatrix):** War fälschlich als "Minecraft Wiki Basis" betitelt — das Wiki hat kein solches Preis-Progressionsschema, nur ein rein kosmetisches Rarity-System (Common/Uncommon/Rare/Epic) ohne Preisbezug. Jetzt korrekt als eigenes, projektinternes Klassifikationsschema gekennzeichnet. Zusätzlich wurde der Tier-2-Preiskorridor korrigiert (`10.0–350.0` → `10.0–1500.0` Buy), da `EMERALD_ORE` (500.0) und `DEEPSLATE_EMERALD_ORE` (1500.0) den alten Korridor überschritten.
  - **Abschnitt 5 ("Gefilterte Ausreißer"):** Enthielt eine Tabelle mit sechs erfundenen Foren-Preisvorschlägen samt fiktiver Quellenangaben ("Foren-Thread", "Diskussion" etc.), die einen nie stattgefundenen Recherche-Prozess vortäuschte. Entfernt und durch die reine Bereinigungs-Prinzip-Beschreibung ersetzt.
  - **Veraltete `-1`-Sentinel-Referenzen:** Abschnitte 4.7, 4.9, 4.10, 4.11 und 7 nutzten noch den alten `buy: -1` / `sell: -1`-Sentinel aus dem fiktiven Schema. Auf `buy-price: false` / `sell-price: false` aktualisiert (Konsistenz mit der echten Schema-Migration aus `[1.1.0]`, die diese Datei damals nicht mit aktualisiert hatte).
  - `RULES.md` Abschnitt "Quellenvalidierung & Manipulationsschutz" entsprechend angepasst (Tier-1–4 nicht mehr als Wiki-Inhalt dargestellt).
  - **Keine Preisänderungen** an den Shop-Configs — ausschließlich Dokumentationskorrektur.
- **Farmbarkeits-Fehleinschätzung korrigiert:** `RULES.md` stufte `ENDER_PEARL`, `NETHER_STAR`, `SHULKER_SHELL`, `TOTEM_OF_UNDYING` und `WITHER_SKELETON_SKULL` fälschlich in dieselbe "kaum farmbar"-Klasse (0.0–0.2) wie echte Weltgenerierungs-Unikate (DIAMOND, NETHERITE_INGOT) ein. Gegen das Minecraft Wiki geprüft: Alle fünf Items sind über bekannte AFK-fähige Farm-Mechaniken (Enderman-Farm, Wither-Zyklus, Shulker-Duplikation, Raid-Farm, Fortress-Farm) unbegrenzt erneuerbar, nur mit höherem Aufwand als Standard-Mob-Loot.
  - Neue Zwischenkategorie "Aufwändig, aber erneuerbar" (Farmbarkeit 0.3–0.4) in `RULES.md` eingeführt.
  - `ITEM_MAPPING.md`: Farmbarkeitswerte korrigiert — `ENDER_PEARL` 0.4→0.6, `NETHER_STAR` 0.1→0.35, `SHULKER_SHELL` 0.3→0.35, `TOTEM_OF_UNDYING` 0.4→0.35, `WITHER_SKELETON_SKULL` 0.2→0.35.
  - Keine Preisänderungen nötig — bestehende Buy/Sell-Werte in `shops/misc.yml`, `shops/mobdrops.yml`, `shops/nether_end.yml` passen bereits in die korrigierten Preisbänder.
  - Details und Quellen: siehe `RESEARCH_SOURCES.md` Abschnitt 6b.

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
