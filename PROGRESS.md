# Projektfortschritt: GUIShop Config-Paket

**Projektziel:** Vollständiges, ausbalanciertes Best-Practice GUIShop-Paket für Minecraft Survival (Version 1.26.2 / GUIShop 9.4.4+).  
**Letzte Aktualisierung:** 2026-09-28  
**Aktueller Status:** **Phase 1 & Phase 2 vollständig abgeschlossen | Bereit für Phase 3 (Shop-Generierung)**

---

## 📊 Phasen-Übersicht & Status

| Phase | Bezeichnung | Status | Erstellte / Relevante Dateien |
|:---:|:---|:---:|:---|
| **Framework** | Regeln, Prozesse & Vorlagen | ✅ Abgeschlossen | [`PLAN-generate-config-pack.md`](./PLAN-generate-config-pack.md)<br>[`RULES.md`](./RULES.md)<br>[`PROCESSES/`](./PROCESSES/)<br>[`TEMPLATES/`](./TEMPLATES/) |
| **Phase 1** | **Item-Bestimmung & Katalog** | ✅ **Abgeschlossen** | [`ITEM_MAPPING.md`](./ITEM_MAPPING.md) |
| **Phase 2** | **Preis-Recherche & Quellendokumentation** | ✅ **Abgeschlossen** | [`RESEARCH_SOURCES.md`](./RESEARCH_SOURCES.md) |
| **Phase 3** | **Shop-Generierung (YAML)** | ⏳ **Als nächstes dran** | Ziel: `menu.yml` & `shops/*.yml` (15 Dateien) |
| **Phase 4** | **Deployment & Validierung** | ⏹ Noch nicht begonnen | `plugins/GUIShop/shops/`, Tests |
| **Doku** | **Dokumentation & Changelog** | ⏹ Noch nicht begonnen | `README.md`, `CHANGELOG.md` |

---

## ✅ Ergebnisse aus Phase 1 (Item-Bestimmung)

1. **Vollständiger Katalog erstellt:**  
   Die Datei [`ITEM_MAPPING.md`](./ITEM_MAPPING.md) wurde gemäß [`PROCESSES/ITEM_SELECTION.md`](./PROCESSES/ITEM_SELECTION.md) erzeugt.
2. **15 Kategorien & Subgruppen abgedeckt:**
   - `blocks.yml`, `minerals.yml`, `farming.yml`, `mobdrops.yml`, `redstone.yml`, `ocean.yml`, `nether_end.yml`, `decorations.yml`, `tools.yml`, `armor.yml`, `enchantments.yml`, `potions.yml`, `spawners.yml`, `custom_items.yml`, `misc.yml`.
3. **Moderne Minecraft-Inhalte integriert:**
   - Waffen & Tools: `MACE`, `WIND_BURST_3`, `DENSITY_5`, `BREACH_4`, `BRUSH`.
   - Blöcke & Automatisierung: `CRAFTER`, `COPPER_BULB`, Tuff-Varianten.
   - Trial Chambers: `TRIAL_KEY`, `OMINOUS_TRIAL_KEY`, `HEAVY_CORE`, `BREEZE_ROD`.
   - Tränke: `POTION_WIND_CHARGED`, `POTION_WEAVING`, `POTION_OOZING`, `POTION_INFESTED`.
   - Wolfsrüstung & Hornschilde: `WOLF_ARMOR`, `ARMADILLO_SCUTE`.

---

## ✅ Ergebnisse aus Phase 2 (Preis-Recherche & Manipulationsschutz)

1. **Manipulationssichere Recherche dokumentiert ([`RESEARCH_SOURCES.md`](./RESEARCH_SOURCES.md)):**
   - **Primärbasis (50%):** Offizielles [`minecraft.wiki`](https://minecraft.wiki/) zur Bestimmung der 4 Progressions-Stufen (Tier 1 Early Game bis Tier 4 End Game).
   - **Praxis-Benchmark (35%):** Mineseed Economy Guide für langzeitstabile Überlebensökonomien.
   - **Aggregierte Marktdaten (15%):** SpigotMC/Paper Multi-Server-Erhebungen (Einzelmeinungen ausgeschlossen).
2. **Ausreißer-Filterung & Manipulationsabwehr:**
   - Unverhältnismäßige Forenvorschläge (z. B. spekulative Preise für Cobblestone, Elytren, Diamanten) wurden abgewiesen und protokolliert.
3. **Wirtschafts- & Farmbarkeitsregeln fixiert:**
   - Tägliche Verkaufslimits (`daily-limit-sell`) für Güter mit Farmbarkeit $\ge 0.7$ definiert.
   - Mathematische 3:1 bis 5:1 Buy/Sell-Ratios eingehalten.
   - Missbrauchsschutz (`sell-price: false`) und Anti-AFK-Schutz (`buy-price: false`) bestätigt.

---

## 🚀 Anleitung für den Wiedereinstieg: Start von Phase 3

Wenn die Arbeit fortgesetzt wird, genau an diesem Punkt anknüpfen:

### Ziel von Phase 3: Shop-Generierung (YAML)
Erzeugung aller produktiven Konfigurationsdateien im GUIShop-Schema:
- **Hauptmenü:** `menu.yml` (Referenziert alle 15 Kategorien per `target-shop`, mit Icons und Slots).
- **15 Shop-Dateien im Ordner `shops/`:**
  1. `shops/blocks.yml`
  2. `shops/minerals.yml`
  3. `shops/farming.yml`
  4. `shops/mobdrops.yml`
  5. `shops/redstone.yml`
  6. `shops/ocean.yml`
  7. `shops/nether_end.yml`
  8. `shops/decorations.yml`
  9. `shops/tools.yml`
  10. `shops/armor.yml`
  11. `shops/enchantments.yml`
  12. `shops/potions.yml`
  13. `shops/spawners.yml`
  14. `shops/custom_items.yml`
  15. `shops/misc.yml`
- **Regeln:**
  - Exakte Syntax nach echtem GUIShop 9.4.4+ (`type: SHOP`, `id`, `buy-price`/`sell-price` mit `false` statt `-1`, `shop-name`/`shop-lore`). Es gibt **kein** `fill-item`, `buy-stack`/`sell-stack` oder `daily-limit-sell` im echten Plugin — Tageslimits werden nur als Hinweistext in `shop-lore` dokumentiert.
  - Slot-Sortierung nach Subgruppen.
  - YAML-Syntax-Validierung.
