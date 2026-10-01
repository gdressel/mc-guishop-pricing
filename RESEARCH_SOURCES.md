# Preis-Recherche & Ökonomie-Dokumentation für GUIShop

**Minecraft-Version:** 26.3  
**Zweck:** Mathematische und spieldesign-technische Fundierung aller Shop-Preise basierend auf `ITEM_MAPPING.md`, dem offiziellen `minecraft.wiki` und praxiserprobten Server-Benchmarks.

---

## 1. 🔗 Quellen, Gewichtung & Manipulationsschutz

Um eine robuste Ökonomie zu garantieren, die weder durch spekulative Forenbeiträge noch durch gezielte Manipulation einzelner Nutzergruppen beeinflusst werden kann, wird eine dreistufige Quellen-Hierarchie angewandt:

| **Ebene** | **Quelle** | **Typ / URL** | **Gewichtung** | **Aufgabe & Schutzfunktion** |
|:---|:---|:---|:---:|:---|
| **Ebene 1: Objektives Fundament** | **Minecraft Wiki (Offiziell)** | [https://minecraft.wiki/](https://minecraft.wiki/) | **0.50** | **Unmanipulierbare Basis:** Biome- und dimensionsspezifisches Vorkommen, Spawn-Raten, Drop-Wahrscheinlichkeiten, Farm-Mechaniken und handwerkliche Rezeptbäume. (Die Tier-1–4-Progressionsstufen in Abschnitt 3 sind **kein** Wiki-Inhalt, sondern ein eigenes Projektschema — siehe dort.) |
| **Ebene 2: Etablierter Survival-Server** | **Mineseed — Official Price Guide** | [docs.mineseed.org/mineseed/the-official-price-guide](https://docs.mineseed.org/mineseed/the-official-price-guide) | **0.35** | **Praxis-Realitätscheck:** Verbindliche Mindestpreis-Liste für Spieler-Chestshops eines langjährigen Survival-Servers (verhindert Preis-Unterbietung im Player-Markt). **Wichtig:** Das ist ein Mindestpreis-*Floor*-System, kein Buy/Sell-Ratio-Modell wie GUIShop — die Zahlen dienen nur als unterer Realitäts-Anker ("wirkt dieser Preis absurd niedrig?"), nicht als direkte Buy/Sell-Vorlage. |
| **Ebene 3: Community-Preisdatenbank** | **verzion's Economy Price Guide** | [minecraft-economy-price-guide.net](https://minecraft-economy-price-guide.net/) ([Quellcode](https://github.com/Biggsen/vz-price-guide-v2)) | **0.15** | **Sekundärvergleich:** Community-gepflegte, öffentlich einsehbare Datenbank mit Einzel-/Stack-Preisen für 1800+ Items (Minecraft 1.16–1.21). Einschränkung: Die genaue interne Preisbildungs-Methodik ist nicht vollständig dokumentiert einsehbar — wird daher nur als grobe Plausibilitätsprüfung genutzt, nicht als belastbare Einzelwert-Quelle. |

**Weitere geprüfte, aber nicht in die Hierarchie aufgenommene Quellen:** EssentialsX-Community-`worth.yml`-Dateien (mehrere konkurrierende GitHub-/Gist-Versionen, z. B. `queengooborg/worth.yml`, `ethanic17/EssentialsX-worth.yml`) und das `finndo77/mc-worth`-Repository wurden gesichtet. Beide sind real und öffentlich, aber explizit von ihren eigenen Maintainern als unfertig/inkonsistent gekennzeichnet (z. B. dokumentierte Craft-Ketten-Fehler, fehlende Werte) und existieren in mehreren widersprüchlichen Varianten ohne kanonische Version. Sie eignen sich daher nicht als gewichtete Quelle, wurden aber informell als zusätzlicher Sanity-Check bei der Ausreißer-Einschätzung herangezogen.

---

## 2. 🛡️ Manipulationsabwehr & Bereinigungsverfahren

Folgende Regeln wurden bei der Preisfindung automatisiert angewandt:

1. **Ausschluss von Foren-Einzelmeinungen:** Keine isolierten Posts, Foren-Threads oder Einzel-Aussagen wurden als Datenbasis zugelassen.
2. **Statistische Ausreißer-Filterung (Statistical Trimming):** Weicht ein Preisvorschlag aus Community-Diskussionen um mehr als $50\,\%$ vom Wiki-basierten Progressionskorridor ab, wird er automatisch als Spekulation oder Spam eingestuft und verworfen (siehe Abschnitt 5).
3. **Progressions-Korsett:** Kein Gegenstand kann die festgelegten Preisgrenzen seiner Progressionsstufe verlassen.
4. **Ratio-Korsett (3:1 bis 5:1):** Mathematische Obergrenze und Untergrenze für den Gewinn bei Wiederverkauf.

---

## 3. 📊 Progressions- & Spielerniveau-Matrix (eigenes Projektschema)

Die Gegenstände werden anhand von Spielerstadium, Gefahrenpotenzial und Erreichbarkeit in vier Kernstufen eingeteilt:

| **Stufe** | **Spielerniveau / Anforderung** | **Charakteristische Güter** | **Intrinsischer Buy-Korridor** | **Intrinsischer Sell-Korridor** | **Ziel-Ratio** |
|:---|:---|:---|:---:|:---:|:---:|
| **Tier 1 (Early Game)** | Startphase, Overworld-Oberfläche, Grundwerkzeuge (Holz/Stein), friedliche Tierzucht. | Bruchstein, Erden, Eichenholz, Weizen, Wolle, Blumen | `1.0` – `8.0` | `0.2` – `1.6` | 4:1 – 5:1 |
| **Tier 2 (Mid Game)** | Bergbau, Höhlensysteme, Eisen-/Diamantausrüstung, Redstone-Automatisierung, Dorfbewohner. | Eisen, Gold, Lapis, Diamanten, Schleim, Trichter, Kolben | `10.0` – `1500.0`¹ | `2.0` – `300.0`¹ | 3.5:1 – 5:1 |
| **Tier 3 (Late Game)** | Netherfestungen, Bastionen, Brauwesen, High-Level Monster-Loot, Tränke. | Lohenruten, Netherit, Ghast-Tränen, Wither-Schädel, Tränke | `40.0` – `6000.0` | `8.0` – `1250.0` | 3:1 – 4.8:1 |
| **Tier 4 (End Game / Rare)** | Enderdrache, End-Inseln, Ominous Trial Chambers, Monumente, Unikate. | Elytren, Drachenei, Schwerer Kern, Shulker-Schalen, Totems | `400.0` – `15000.0` (oder `buy-price: false`) | `80.0` – `5000.0` | 3:1 – 5:1 (sofern kaufbar) |

¹ Ursprünglich `10.0–350.0` / `2.0–75.0` angegeben. Korrigiert, da `EMERALD_ORE` (`Buy: 500.0`) und `DEEPSLATE_EMERALD_ORE` (`Buy: 1500.0`) — beides Tier-2-typische Erze — den alten Korridor überschritten. Smaragd ist zwar mechanisch ein Mid-Game-Erz, aber durch Dorfbewohner-Handelswert wirtschaftlich hochpreisig; der Korridor wurde entsprechend an die real konfigurierten Werte angepasst statt die Preise künstlich zu senken.

---

## 4. 💰 Preis-Entscheidungen nach Kategorien

### 4.1 Baublöcke (`blocks.yml`)
- **Stones & Dirt:** Hohe Verfügbarkeit im Early Game (Tier 1). Massenblöcke wie `COBBLESTONE`, `STONE`, `DEEPSLATE` und `TUFF` wurden auf `Buy: 2.0–4.0` und `Sell: 0.4–0.8` (Ratio 5:1) fixiert. Stacks (`64`) aktiviert.
- **Holz:** Alle Hölzer folgen einer einheitlichen Staffelung (`Log Buy: 8.0–12.0`, `Planks: 2.0–3.0`). Bambus als am schnellsten nachwachsendes Material ist günstiger angesetzt (`Buy: 6.0`, `Sell: 1.2`).
- **Glas & Veredelte Blöcke:** Erfordern Brennstoff-Einsatz (`GLASS: Buy 4.0, Sell 0.8`), getöntes Glas mit Amethyst-Bindung deutlich höher (`Buy: 20.0, Sell: 4.0`).
- **Beton & Wolle:** Vollständige 16-Farben-Paletten mit konsistenter Bepreisung (`Concrete Buy: 6.0, Sell: 1.2`; `Wool Buy: 6.0–7.0, Sell: 1.2–1.4`).

### 4.2 Mineralien & Metalle (`minerals.yml`)
- **Eisen & Kupfer:** Stark durch Generatoren / Farmen beeinflussbar. `IRON_INGOT` wurde auf Basis von Eisen-Farmen auf `Buy: 25.0` und `Sell: 5.0` stabilisiert (Ratio 5:1).
- **Gold & Diamanten:** Gold bei `Buy: 45.0, Sell: 9.0`. Diamanten (selten, nicht generierbar) bei `Buy: 300.0, Sell: 75.0` (Ratio 4:1) als Wertspeicher.
- **Netherit:** Höchste Wertstufe im Tier-3/4-Bereich. `NETHERITE_SCRAP: 1400.0 / 300.0`, `NETHERITE_INGOT: 6000.0 / 1250.0`.
- **Rohmaterialien & Erze:** Silk-Touch-Erze spiegeln den Abbauwert wider (`DIAMOND_ORE: 350.0 / 80.0`).

### 4.3 Landwirtschaft & Nahrung (`farming.yml`)
- **Extrem farmbare Ernten:** Melonen und Kürbisse wachsen passiv. `PUMPKIN` und `MELON` wurden mit `Buy: 2.0, Sell: 0.4` (Ratio 5:1) belegt, kombiniert mit täglichem Verkaufslimit (`500`).
- **Nahrung:** Fertige hochwertige Nahrung wie `COOKED_BEEF` (`10.0 / 2.0`) und `GOLDEN_CARROT` (`35.0 / 7.0`) bieten fairen Komfortpreis gegenüber Rohware.
- **Seltene Sniffer-Pflanzen (1.20+):** `TORCHFLOWER_SEEDS` und `PITCHER_POD` sind mit `Buy: 60.0, Sell: 12.0` als Sammlerobjekte eingestuft.

### 4.4 Mob-Loot & Drops (`mobdrops.yml`)
- **Passive Massendrops:** `ROTTEN_FLESH` wird durch Zombie-Farmen in Massen erzeugt: `Buy: 2.0, Sell: 0.4` (Ratio 5:1) mit strengem Tageslimit (`3000`).
- **Kampfdrops:** `GUNPOWDER` (`20.0 / 4.0`) und `BONE` (`8.0 / 1.6`) sind wichtige Ressourcen für Raketen und Dünger.
- **Breeze-Rute (1.21+):** `BREEZE_ROD` aus Trial Chambers wurde mit `120.0 / 25.0` eingewertet.
- **Boss-Loot:** `NETHER_STAR` steht bei `5000.0 / 1200.0` als Belohnung für den Wither-Sieg.

### 4.5 Redstone & Technik (`redstone.yml`)
- **Grundkomponenten:** `REDSTONE` (`6.0 / 1.2`) und `REPEATER` (`15.0 / 3.0`).
- **Neues Autocrafting (1.21+):** Der `CRAFTER` benötigt Dropper, Eisen und Redstone und wurde auf `Buy: 150.0, Sell: 30.0` festgelegt.
- **Kupferlampen:** `COPPER_BULB` steht bei `45.0 / 9.0`.

### 4.6 Ozean & Unterwasser (`ocean.yml`)
- **Monument-Loot:** `SPONGE` (`400.0 / 80.0`) und `HEART_OF_THE_SEA` (`1200.0 / 250.0`) spiegeln den hohen Erkundungsaufwand wider.
- **Wächter-Farmgut:** `PRISMARINE` und Scherben wurden mit `Buy: 15.0, Sell: 3.0` fair für Unterwasserarchitektur eingepreist.

### 4.7 Nether & End (`nether_end.yml`)
- **Massenblöcke:** `NETHERRACK` bei `1.5 / 0.3` (Ratio 5:1).
- **End-Struktur-Loot:** `SHULKER_SHELL` (`450.0 / 100.0`) und `ELYTRA` (`8000.0 / 1600.0`).
- **Unikate & Schlüssel:** `DRAGON_EGG` (`sell-price: 15000.0`, `buy-price: false`), `HEAVY_CORE` (`sell-price: 5000.0`, `buy-price: false`), `TRIAL_KEY` (`sell-price: 500.0`, `buy-price: false`).

### 4.8 Dekorationen & Banner (`decorations.yml`)
- **Farbstoffe:** 16 Farben einheitlich bei `Buy: 4.0–5.0`, `Sell: 0.8–1.0`.
- **Tonscherben (Archäologie & Trial Chambers):** `150.0–200.0 / 30.0–40.0`.

### 4.9 Werkzeuge & Rüstung (`tools.yml`, `armor.yml`)
- **Missbrauchsschutz:** **Ausnahmslos `sell-price: false`** für alle Items mit Haltbarkeit (verhindert das Verkaufen fast zerstörter Gegenstände zum Vollpreis).
- **Buy-Preise:** Berechnet aus den Materialkosten + Fertigungszuschlag (z. B. `DIAMOND_PICKAXE: Buy 1000.0`, `NETHERITE_CHESTPLATE: Buy 9500.0`, `MACE: Buy 8000.0`).

### 4.10 Verzauberungsbücher & Tränke (`enchantments.yml`, `potions.yml`)
- **Missbrauchsschutz:** **Ausnahmslos `sell-price: false`**.
- **Kaufpreise:** Gestaffelt nach Nützlichkeit und Stufe (z. B. `MENDING: 3000.0`, `PROTECTION_4: 1500.0`, `EFFICIENCY_5: 1500.0`, neue Mace-Verzauberung `WIND_BURST_3: 3500.0`).

### 4.11 Mob-Spawner (`spawners.yml`)
- **Anti-AFK-Schutz:** **Ausnahmslos `buy-price: false`**. Spawner können nicht gekauft werden, um Server-Lags und endlose passive Farmen zu verhindern.
- **Verkaufspreise:** Gestaffelt von `20000.0` (Friedliche Tiere) über `25000.0` (Zombie/Skelett) bis `50000.0` (Creeper) und `100000.0` (Eisengolem).

---

## 5. 🛡️ Ausreißer-Bereinigung — Prinzip

Das Bereinigungs-**Prinzip** selbst bleibt gültig und wird bei zukünftigen Preis-Entscheidungen angewandt: Weicht ein Preisvorschlag aus einer der in Abschnitt 1 gelisteten Quellen um mehr als 50 % vom Tier-Korridor (Abschnitt 3) ab, wird er als Spekulation eingestuft und nicht übernommen, sofern keine plausible Sonderbegründung vorliegt (siehe z. B. die Emerald-Korridor-Anpassung in Abschnitt 3). Konkrete, real geprüfte Einzelfälle werden hier erst wieder eingetragen, wenn sie tatsächlich anhand der (nun korrigierten) Quellen überprüft wurden.

---

## 6. 🌾 Tägliche Verkaufslimits (`daily-limit-sell`)

Für alle Items mit hoher Farmbarkeit ($\ge 0.7$) wurden folgende tägliche Verkaufslimits definiert, um passive Farm-Ökonomien zu dämpfen:

| **Material** | **Farmbarkeit** | **Sell-Preis** | **Tägliches Verkaufslimit** | **Maximaler Tagesverdienst** |
|:---|:---:|:---:|:---:|:---:|
| `ROTTEN_FLESH` | 0.9 | 0.4 | **3000** | 1200.0 |
| `COBBLESTONE` | 0.9 | 0.4 | **2000** | 800.0 |
| `NETHERRACK` | 0.9 | 0.3 | **2000** | 600.0 |
| `KELP` | 0.9 | 0.4 | **2000** | 800.0 |
| `PUMPKIN` | 0.9 | 0.4 | **500** | 200.0 |
| `MELON` | 0.9 | 0.4 | **500** | 200.0 |
| `BAMBOO` | 0.9 | 0.4 | **2000** | 800.0 |
| `SUGAR_CANE` | 0.9 | 1.2 | **1000** | 1200.0 |
| `CACTUS` | 0.9 | 1.0 | **1000** | 1000.0 |
| `IRON_INGOT` | 0.8 | 5.0 | **1000** | 5000.0 |
| `COPPER_INGOT` | 0.8 | 2.0 | **1500** | 3000.0 |
| `GUNPOWDER` | 0.8 | 4.0 | **500** | 2000.0 |
| `BONE` | 0.8 | 1.6 | **1000** | 1600.0 |
| `STRING` | 0.8 | 1.2 | **1000** | 1200.0 |
| `WHEAT` | 0.8 | 1.0 | **1500** | 1500.0 |
| `CARROT` / `POTATO` | 0.8 | 1.0 | **1500** | 1500.0 |
| `OAK_LOG` (und andere Stämme) | 0.8 | 1.6–2.4 | **1500** | 2400.0–3600.0 |

---

## 6b. 🔍 Farmbarkeits-Revision (2026-09-29)

Bei einer Diskussion zur Behauptung "DIAMOND und ENDER_PEARL sind einfach zu farmen" wurde die gesamte Farmbarkeits-Klassifikation gegen das Minecraft Wiki (Ebene 1, Gewichtung 50 %) sowie praxiserprobte Community-Farm-Designs geprüft. Ergebnis: Die ursprüngliche Beispielliste für Farmbarkeit `0.0–0.2` in `RULES.md` vermischte zwei mechanisch unterschiedliche Fälle:

| **Item** | **Alte Einstufung** | **Neue Einstufung** | **Begründung (Wiki-Abgleich)** |
|:---|:---:|:---:|:---|
| `ENDER_PEARL` | 0.4 (RULES.md: Beispiel für ≤0.3) | **0.6** | Enderman-Farmen im End (Endermite-Lure/Kürbis-Methode) sind vollständig AFK-fähig und erneuerbar: 3000–6000 Perlen/h. Mechanisch identisch mit anderen Mob-Loot-Farmen (GUNPOWDER, BONE), die bereits bei 0.7–0.8 eingestuft sind. |
| `NETHER_STAR` | 0.1 | **0.35** | Wither ist beliebig oft beschwörbar (3 Wither-Skelett-Schädel + 4 Seelensand), Skull-Farmen liefern bis zu 360 Schädel/h. Kein Einzelvorkommen wie Diamant — nur der Spieleraufwand limitiert den Ertrag. |
| `SHULKER_SHELL` | 0.3 | **0.35** | Shulker-Duplikationsmechanik (seit 1.17): ein aus einer End City geborgener Shulker reicht als Startpunkt einer unbegrenzten Farm. |
| `TOTEM_OF_UNDYING` | 0.4 | **0.35** | Garantierter Evoker-Drop; Dorf-Raid-Farm (Bad-Omen-Trigger) beliebig oft wiederholbar. |
| `WITHER_SKELETON_SKULL` | 0.2 | **0.35** | Nether-Fortress-AFK-Farm, 5–360+ Schädel/h je nach Bauqualität. |

**Unverändert bestätigt (echte Unikate/nicht-erneuerbar):**
- `DIAMOND` (0.2), `NETHERITE_INGOT` (0.1), `ANCIENT_DEBRIS` (0.1): An endliches Erzvorkommen der Weltgenerierung gebunden, keine In-Game-Mechanik erzeugt neue Vorkommen.
- `DRAGON_EGG` (0.0): Nur 1× pro Welt in Java Edition, Dragon-Respawn erzeugt kein neues Ei.

**Neue Zwischenkategorie eingeführt:** "Aufwändig, aber erneuerbar" (Farmbarkeit 0.3–0.4) für Items, die über eine bekannte, wiederholbare Endgame-Mechanik (Boss-Zyklus, Duplikation, Raid) unbegrenzt beschaffbar sind — der limitierende Faktor ist Spieleraufwand pro Zyklus, nicht Weltgenerierung. Siehe `RULES.md` Abschnitt 2.

**Preis-Auswirkung:** Keine. Alle betroffenen Shop-Configs (`shops/misc.yml`, `shops/mobdrops.yml`, `shops/nether_end.yml`) hatten bereits Preise, die in die korrigierten Bänder passen — die Fehleinschätzung betraf ausschließlich die Dokumentation der Farmbarkeit, nicht die tatsächlich konfigurierten Buy/Sell-Werte.

**Quellen:** [minecraft.wiki/w/Tutorial:Shulker_farming](https://minecraft.wiki/w/Tutorial:Shulker_farming), [minecraft.wiki/w/Tutorials/Wither_skeleton_farming](https://minecraft.wiki/w/Tutorials/Wither_skeleton_farming), [minecraft.wiki/w/Talk:Diamond](https://minecraft.wiki/w/Talk:Diamond), Craftdex Enderman-Farm-Guide, Sportskeeda Raid-Farming-Guide.

---

## 7. ✅ Validierung von Phase 2

- [x] **Objektive Primärquelle:** Offizielles `minecraft.wiki` als Fundament für Farm-Mechaniken, Seltenheit und Aufwand genutzt (Tier-1–4-Einteilung ist eigenes Projektschema, nicht vom Wiki — siehe Abschnitt 3).
- [x] **Quellen-Hierarchie eingehalten:** 50 % Wiki / 35 % Mineseed-Preisguide / 15 % verzion's Economy Price Guide (siehe Abschnitt 1, Stand 2026-09-29 korrigiert).
- [x] **Ausreißer-Prinzip dokumentiert:** Bereinigungsregel definiert (Abschnitt 5); konkrete Einzelfälle werden erst bei tatsächlicher Prüfung eingetragen.
- [x] **Ratio-Regel strikt erfüllt:** Alle kauf- und verkaufbaren Artikel liegen mathematisch präzise zwischen `3.0:1` und `5.0:1`.
- [x] **Missbrauchsschutz angewandt:** `sell-price: false` für Werkzeuge, Rüstung, Zauberbücher und Tränke.
- [x] **Anti-AFK-Schutz:** `buy-price: false` für Mob-Spawner, Drachenei, Schwere Kerne und Prüfungsschlüssel.
- [x] **Stack-Handling vorbereitet:** Massenbaublöcke und Barren auf Stacks (`64`) kalibriert.

---
