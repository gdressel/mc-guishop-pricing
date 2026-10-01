# Changelog

Alle nennenswerten Änderungen an diesem Config-Paket werden hier dokumentiert.

Das Format orientiert sich an [Keep a Changelog](https://keepachangelog.com/de/1.0.0/).

---

## [Unreleased]
### Changed
- Header-Metadaten (`Datum`, `Erstellt von`/`Durchgeführt von: Antigravity AI`, `Status`) sowie die Footer-Zeile `Letzte Aktualisierung` aus `ITEM_MAPPING.md`, `RESEARCH_SOURCES.md`, `RULES.md` und `PLAN-generate-config-pack.md` entfernt — Autoren- und Datumsangaben werden inzwischen durch git-Historie abgedeckt, die Sole-Attribution an Antigravity AI war nicht mehr akkurat. `PROGRESS.md` zusätzlich auf den tatsächlichen Stand aktualisiert (Phase 3, Doku und Deployment sind fertig bzw. live auf dem Server im Einsatz, nicht mehr "als nächstes dran"/"noch nicht begonnen").

### Fixed
- `RULES.md`: Phantom-Items `DIRT`/`SAND`/`GRAVEL` (existieren nicht im Katalog) durch reale Beispiele ersetzt; Preis-Leitfaden-Tabelle auf reale Shop-Werte aktualisiert; Preisbänder der Farmbarkeit-Kategorien-Tabelle erweitert (0.7–0.8 und 0.3–0.6 waren zu eng für `BONE`/`STRING`/`EMERALD`), inkl. Fußnoten zu Kompaktblock-Preisaufschlag und Emerald-Handelswert-Ausnahme; Spawner-Sell-Obergrenze auf real `100000.0` korrigiert; Beispielwerte/-IDs für Rüstung, Zauberbücher und Tränke berichtigt; `custom_items.yml` und `buy-price: false`-Belohnungsauslöser als neue Abschnitte ergänzt.
- `RESEARCH_SOURCES.md`: Phantom-Zeile `DIRT`/`SAND` in Abschnitt 6 durch reale Items ersetzt.
- `ITEM_MAPPING.md`: veralteten `-1`-Sentinel durchgängig auf `false` umgestellt (162 Stellen), zur Konsistenz mit dem seit `[1.1.0]` echten GUIShop-Schema — keine Preisänderungen.
- `RESEARCH_SOURCES.md`: mehrere fabrizierte/falsch zugeschriebene Quellen ersetzt (zwei nicht-existente Kernquellen, Tier-1–4-Matrix fälschlich als Wiki-Inhalt deklariert, erfundene Ausreißer-Tabelle in Abschnitt 5 entfernt); Tier-2-Preiskorridor korrigiert (`EMERALD_ORE`/`DEEPSLATE_EMERALD_ORE` sprengten ihn); veraltete `-1`-Sentinel-Referenzen auf `false` aktualisiert. Keine Preisänderungen an Shop-Configs.
- Farmbarkeit von `ENDER_PEARL`, `NETHER_STAR`, `SHULKER_SHELL`, `TOTEM_OF_UNDYING`, `WITHER_SKELETON_SKULL` korrigiert (waren fälschlich als "kaum farmbar" wie `DIAMOND` eingestuft, sind aber via AFK-Farmen unbegrenzt erneuerbar); neue Zwischenkategorie "Aufwändig, aber erneuerbar" (0.3–0.4) in `RULES.md`. Details: `RESEARCH_SOURCES.md` Abschnitt 6b.
- **Versionsschema-Korrektur:** Das gesamte Paket referenzierte durchgängig die erfundene Version "Minecraft 1.26.2" (`1.x.x` existiert seit dem Versionsschema-Wechsel 2026 nicht mehr; letzte `1.x`-Version war `1.21`). Alle Vorkommen in `README.md`, `ITEM_MAPPING.md`, `RESEARCH_SOURCES.md`, `RULES.md`, `PROGRESS.md`, `PLAN-generate-config-pack.md` und den `TEMPLATES/` auf das reale Jahres-Schema `JJ.N` (`26.3`) korrigiert; `TRIAL_KEY`/`HEAVY_CORE`/`TRIAL_SPAWNER` korrekt auf ihre tatsächliche Einführungsversion `1.21` ("Tricky Trials") statt `1.26.2` datiert. Zusätzlich: `menu.yml`-Lore zeigte Spielern noch den veralteten `sell: -1`/`buy: -1`-Sentinel an (5 Stellen) statt des seit `[1.1.0]` realen `false`-Werts — behoben. Keine Preis- oder Item-Änderungen.

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
