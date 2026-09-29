# Item-Mapping für GUIShop

**Minecraft-Version:** 1.26.2
**Datum:** 2026-09-28
**Erstellt von:** Antigravity AI
**Status:** Abgeschlossen (Phase 1)

---

## 📌 **Hinweise zur Nutzung dieser Zuordnung**

1. **Eindeutigkeit:** Jedes Item ist genau einer Kategorie und einer Subgruppe zugeordnet.
2. **Farmbarkeit:** Wertebereich von `0.0` (absolut unzugänglich für automatische Farmen / Unikate) bis `1.0` (vollautomatisch mit minimalem Aufwand generierbar).
3. **Wirtschaftsregeln:**
   - Standard Buy:Sell-Ratio zwischen `3:1` und `5:1`.
   - `sell: false`: Items mit variabler Haltbarkeit/Enchantments (Missbrauchsschutz für Werkzeuge, Rüstung, Tränke, Zauberbücher).
   - `buy: false`: Extrem seltene Boss-Drops oder Spawner (können nur erspielt und verkauft werden).
   - `daily-limit-sell`: Vorgesehen für Items mit Farmbarkeit $\ge 0.7$ (Greift in Phase 3 bei der YAML-Erzeugung).
4. **Stack-Größen:** Stacks (`64`) gelten primär für Massenblöcke und Erze/Barren; Werkzeuge, Rüstungen und Spezialitems werden einzeln gehandelt.

---

## 📁 **Kategorien & Subgruppen**

### 1. blocks.yml
*Subgruppen: `stones`, `wood`, `glass`, `concrete`, `terracotta`, `wool`*

| Material | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `COBBLESTONE` | Bruchstein | stones | 0.9 | 2.0 | 0.4 | Generatorfarmbar (Ratio 5:1) |
| `MOSSY_COBBLESTONE` | Bemooster Bruchstein | stones | 0.7 | 4.0 | 0.8 | Craftbar / Dungeons |
| `STONE` | Stein | stones | 0.8 | 3.0 | 0.6 | Schmelzen / Silk Touch |
| `SMOOTH_STONE` | Glatter Stein | stones | 0.8 | 4.0 | 0.8 | Doppelter Schmelzprozess |
| `STONE_BRICKS` | Steinziegel | stones | 0.8 | 4.0 | 0.8 | Craftbar aus Stein |
| `MOSSY_STONE_BRICKS` | Bemooste Steinziegel | stones | 0.6 | 6.0 | 1.2 | Deko / Lianen-Crafting |
| `CRACKED_STONE_BRICKS` | Rissige Steinziegel | stones | 0.6 | 6.0 | 1.2 | Schmelzen von Steinziegeln |
| `CHISELED_STONE_BRICKS` | Gemeißelte Steinziegel | stones | 0.6 | 8.0 | 1.6 | Ziegel-Spezialblock |
| `GRANITE` | Granit | stones | 0.7 | 3.0 | 0.6 | Natürliches Gestein |
| `POLISHED_GRANITE` | Polierter Granit | stones | 0.7 | 4.0 | 0.8 | Polierte Variante |
| `DIORITE` | Diorit | stones | 0.7 | 3.0 | 0.6 | Natürliches Gestein |
| `POLISHED_DIORITE` | Polierter Diorit | stones | 0.7 | 4.0 | 0.8 | Polierte Variante |
| `ANDESITE` | Andesit | stones | 0.7 | 3.0 | 0.6 | Natürliches Gestein |
| `POLISHED_ANDESITE` | Polierter Andesit | stones | 0.7 | 4.0 | 0.8 | Polierte Variante |
| `DEEPSLATE` | Tiefenschiefer | stones | 0.8 | 4.0 | 0.8 | Silk Touch in der Tiefe |
| `COBBLED_DEEPSLATE` | Bruchtiefenschiefer | stones | 0.8 | 3.0 | 0.6 | Häufig beim Tiefenbau |
| `POLISHED_DEEPSLATE` | Polierter Tiefenschiefer | stones | 0.8 | 5.0 | 1.0 | Handwerksblock |
| `DEEPSLATE_BRICKS` | Tiefenschieferziegel | stones | 0.8 | 6.0 | 1.2 | Veredelter Baublock |
| `CRACKED_DEEPSLATE_BRICKS` | Rissige Tiefenschieferziegel | stones | 0.7 | 7.0 | 1.4 | Geschmolzen |
| `DEEPSLATE_TILES` | Tiefenschieferfliesen | stones | 0.8 | 6.0 | 1.2 | Deko & Architektur |
| `CRACKED_DEEPSLATE_TILES` | Rissige Fliesen | stones | 0.7 | 7.0 | 1.4 | Geschmolzen |
| `CHISELED_DEEPSLATE` | Gemeißelter Tiefenschiefer | stones | 0.7 | 8.0 | 1.6 | Zierblock |
| `TUFF` | Tuff | stones | 0.7 | 3.0 | 0.6 | Natürliches Tiefengestein |
| `POLISHED_TUFF` | Polierter Tuff | stones | 0.7 | 4.0 | 0.8 | Polierte Variante |
| `TUFF_BRICKS` | Tuffsteinziegel | stones | 0.7 | 5.0 | 1.0 | Veredelter Baublock |
| `CHISELED_TUFF_BRICKS` | Gemeißelte Tuffsteinziegel | stones | 0.6 | 7.0 | 1.4 | Deko |
| `CALCITE` | Kalzit | stones | 0.4 | 8.0 | 1.6 | Seltenere Adern |
| `DRIPSTONE_BLOCK` | Tropfsteinblock | stones | 0.6 | 6.0 | 1.2 | Höhlen / Farmbar |
| `BASALT` | Basalt | stones | 0.8 | 4.0 | 0.8 | Generatorfarmbar im Nether |
| `SMOOTH_BASALT` | Glatter Basalt | stones | 0.7 | 5.0 | 1.0 | Geoden / Schmelzen |
| `POLISHED_BASALT` | Polierter Basalt | stones | 0.7 | 5.0 | 1.0 | Zierblock |
| `SANDSTONE` | Sandstein | stones | 0.8 | 4.0 | 0.8 | Craftbar aus Sand |
| `CHISELED_SANDSTONE` | Gemeißelter Sandstein | stones | 0.7 | 6.0 | 1.2 | Deko |
| `CUT_SANDSTONE` | Geschnittener Sandstein | stones | 0.7 | 5.0 | 1.0 | Deko |
| `SMOOTH_SANDSTONE` | Glatter Sandstein | stones | 0.7 | 6.0 | 1.2 | Geschmolzener Sandstein |
| `RED_SANDSTONE` | Roter Sandstein | stones | 0.6 | 6.0 | 1.2 | Badlands-Variante |
| `CHISELED_RED_SANDSTONE` | Gemeißelter Roter Sandstein | stones | 0.5 | 8.0 | 1.6 | Zierblock |
| `CUT_RED_SANDSTONE` | Geschnittener Roter Sandstein | stones | 0.5 | 7.0 | 1.4 | Zierblock |
| `SMOOTH_RED_SANDSTONE` | Glatter Roter Sandstein | stones | 0.5 | 8.0 | 1.6 | Geschmolzen |
| `BRICKS` | Ziegel | stones | 0.7 | 6.0 | 1.2 | Gebrannter Ton |
| `MUD_BRICKS` | Schlammziegel | stones | 0.8 | 5.0 | 1.0 | Farmbar aus Schlamm |
| `PACKED_MUD` | Fester Schlamm | stones | 0.8 | 4.0 | 0.8 | Schlamm + Weizen |
| `OBSIDIAN` | Obsidian | stones | 0.6 | 40.0 | 8.0 | Lavaguss / Portale |
| `CRYING_OBSIDIAN` | Weinender Obsidian | stones | 0.4 | 80.0 | 16.0 | Tauschhandel / Ruinen |
| `OAK_LOG` | Eichenstamm | wood | 0.8 | 8.0 | 1.6 | Baumfarmbar |
| `OAK_PLANKS` | Eichenholzbretter | wood | 0.8 | 2.0 | 0.4 | Basisholz |
| `STRIPPED_OAK_LOG` | Entrindeter Eichenstamm | wood | 0.8 | 9.0 | 1.8 | Veredelt |
| `SPRUCE_LOG` | Fichtenstamm | wood | 0.8 | 8.0 | 1.6 | Beliebtes Bauholz |
| `SPRUCE_PLANKS` | Fichtenholzbretter | wood | 0.8 | 2.0 | 0.4 | Basisholz |
| `STRIPPED_SPRUCE_LOG` | Entrindeter Fichtenstamm | wood | 0.8 | 9.0 | 1.8 | Veredelt |
| `BIRCH_LOG` | Birkenstamm | wood | 0.8 | 8.0 | 1.6 | Baumfarmbar |
| `BIRCH_PLANKS` | Birkenholzbretter | wood | 0.8 | 2.0 | 0.4 | Basisholz |
| `STRIPPED_BIRCH_LOG` | Entrindeter Birkenstamm | wood | 0.8 | 9.0 | 1.8 | Veredelt |
| `JUNGLE_LOG` | Tropenholzstamm | wood | 0.7 | 9.0 | 1.8 | Urwald |
| `JUNGLE_PLANKS` | Tropenholzbretter | wood | 0.7 | 2.25 | 0.45 | Basisholz |
| `STRIPPED_JUNGLE_LOG` | Entrindeter Tropenstamm | wood | 0.7 | 10.0 | 2.0 | Veredelt |
| `ACACIA_LOG` | Akazienstamm | wood | 0.7 | 9.0 | 1.8 | Savanne |
| `ACACIA_PLANKS` | Akazienholzbretter | wood | 0.7 | 2.25 | 0.45 | Basisholz |
| `STRIPPED_ACACIA_LOG` | Entrindeter Akazienstamm | wood | 0.7 | 10.0 | 2.0 | Veredelt |
| `DARK_OAK_LOG` | Schwarzeichenstamm | wood | 0.7 | 9.0 | 1.8 | Dichter Wald |
| `DARK_OAK_PLANKS` | Schwarzeichenbretter | wood | 0.7 | 2.25 | 0.45 | Basisholz |
| `STRIPPED_DARK_OAK_LOG` | Entrindeter Schwarzeichenstamm | wood | 0.7 | 10.0 | 2.0 | Veredelt |
| `MANGROVE_LOG` | Mangrovenstamm | wood | 0.6 | 12.0 | 2.4 | Sumpf |
| `MANGROVE_PLANKS` | Mangrovenbretter | wood | 0.6 | 3.0 | 0.6 | Basisholz |
| `STRIPPED_MANGROVE_LOG` | Entrindeter Mangrovenstamm | wood | 0.6 | 13.0 | 2.6 | Veredelt |
| `CHERRY_LOG` | Kirschblütenstamm | wood | 0.6 | 12.0 | 2.4 | Kirschberghain |
| `CHERRY_PLANKS` | Kirschholzbretter | wood | 0.6 | 3.0 | 0.6 | Rosa Holz |
| `STRIPPED_CHERRY_LOG` | Entrindeter Kirschstamm | wood | 0.6 | 13.0 | 2.6 | Veredelt |
| `BAMBOO_BLOCK` | Bambusblock | wood | 0.9 | 6.0 | 1.2 | Extrem schnell farmbar |
| `BAMBOO_PLANKS` | Bambusbretter | wood | 0.9 | 3.0 | 0.6 | Bambusarchitektur |
| `STRIPPED_BAMBOO_BLOCK` | Entrindeter Bambusblock | wood | 0.9 | 7.0 | 1.4 | Veredelter Bambus |
| `GLASS` | Glas | glass | 0.7 | 4.0 | 0.8 | Gebrannter Sand |
| `TINTED_GLASS` | Getöntes Glas | glass | 0.4 | 20.0 | 4.0 | Glas + 4 Amethystscherben |
| `WHITE_STAINED_GLASS` | Weißes Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `ORANGE_STAINED_GLASS` | Orangenes Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `MAGENTA_STAINED_GLASS` | Magenta Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `LIGHT_BLUE_STAINED_GLASS` | Hellblaues Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `YELLOW_STAINED_GLASS` | Gelbes Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `LIME_STAINED_GLASS` | Hellgrünes Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `PINK_STAINED_GLASS` | Rosa Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `GRAY_STAINED_GLASS` | Graues Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `LIGHT_GRAY_STAINED_GLASS` | Hellgraues Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `CYAN_STAINED_GLASS` | Türkises Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `PURPLE_STAINED_GLASS` | Violettes Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `BLUE_STAINED_GLASS` | Blaues Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `BROWN_STAINED_GLASS` | Braunes Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `GREEN_STAINED_GLASS` | Grünes Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `RED_STAINED_GLASS` | Rotes Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `BLACK_STAINED_GLASS` | Schwarzes Glas | glass | 0.7 | 5.0 | 1.0 | Gefärbtes Glas |
| `WHITE_CONCRETE` | Weißer Beton | concrete | 0.8 | 6.0 | 1.2 | Sand + Kies + Farbstoff |
| `ORANGE_CONCRETE` | Orangener Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `MAGENTA_CONCRETE` | Magenta Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `LIGHT_BLUE_CONCRETE` | Hellblauer Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `YELLOW_CONCRETE` | Gelber Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `LIME_CONCRETE` | Hellgrüner Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `PINK_CONCRETE` | Rosa Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `GRAY_CONCRETE` | Grauer Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `LIGHT_GRAY_CONCRETE` | Hellgrauer Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `CYAN_CONCRETE` | Türkiser Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `PURPLE_CONCRETE` | Violetter Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `BLUE_CONCRETE` | Blauer Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `BROWN_CONCRETE` | Brauner Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `GREEN_CONCRETE` | Grüner Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `RED_CONCRETE` | Roter Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `BLACK_CONCRETE` | Schwarzer Beton | concrete | 0.8 | 6.0 | 1.2 | Architekturbeton |
| `WHITE_CONCRETE_POWDER` | Weißer Trockenbeton | concrete | 0.8 | 4.0 | 0.8 | Vorstufe |
| `BLACK_CONCRETE_POWDER` | Schwarzer Trockenbeton | concrete | 0.8 | 4.0 | 0.8 | Vorstufe |
| `TERRACOTTA` | Keramik | terracotta | 0.7 | 5.0 | 1.0 | Gebrannter Ton |
| `WHITE_TERRACOTTA` | Weiße Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `ORANGE_TERRACOTTA` | Orangene Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `MAGENTA_TERRACOTTA` | Magenta Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `LIGHT_BLUE_TERRACOTTA` | Hellblaue Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `YELLOW_TERRACOTTA` | Gelbe Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `LIME_TERRACOTTA` | Hellgrüne Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `PINK_TERRACOTTA` | Rosa Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `GRAY_TERRACOTTA` | Graue Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `LIGHT_GRAY_TERRACOTTA` | Hellgraue Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `CYAN_TERRACOTTA` | Türkise Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `PURPLE_TERRACOTTA` | Violette Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `BLUE_TERRACOTTA` | Blaue Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `BROWN_TERRACOTTA` | Braune Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `GREEN_TERRACOTTA` | Grüne Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `RED_TERRACOTTA` | Rote Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `BLACK_TERRACOTTA` | Schwarze Keramik | terracotta | 0.7 | 6.0 | 1.2 | Gefärbte Keramik |
| `WHITE_WOOL` | Weiße Wolle | wool | 0.8 | 6.0 | 1.2 | Schafzucht / Scheren |
| `ORANGE_WOOL` | Orangene Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `MAGENTA_WOOL` | Magenta Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `LIGHT_BLUE_WOOL` | Hellblaue Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `YELLOW_WOOL` | Gelbe Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `LIME_WOOL` | Hellgrüne Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `PINK_WOOL` | Rosa Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `GRAY_WOOL` | Graue Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `LIGHT_GRAY_WOOL` | Hellgraue Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `CYAN_WOOL` | Türkise Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `PURPLE_WOOL` | Violette Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `BLUE_WOOL` | Blaue Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `BROWN_WOOL` | Braune Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `GREEN_WOOL` | Grüne Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `RED_WOOL` | Rote Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |
| `BLACK_WOOL` | Schwarze Wolle | wool | 0.8 | 7.0 | 1.4 | Gefärbt |

---

### 2. minerals.yml
*Subgruppen: `ores`, `raw_materials`, `ingots`, `gems`*

| Material | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `COAL_ORE` | Steinkohle-Erz | ores | 0.6 | 12.0 | 2.5 | Silk Touch Erz |
| `DEEPSLATE_COAL_ORE` | Tiefenschiefer-Kohleerz | ores | 0.4 | 20.0 | 4.0 | Selten in der Tiefe |
| `IRON_ORE` | Eisenerz | ores | 0.6 | 20.0 | 4.0 | Silk Touch Erz |
| `DEEPSLATE_IRON_ORE` | Tiefenschiefer-Eisenerz | ores | 0.5 | 25.0 | 5.0 | Tiefenvariante |
| `COPPER_ORE` | Kupfererz | ores | 0.7 | 10.0 | 2.0 | Häufiges Erz |
| `DEEPSLATE_COPPER_ORE` | Tiefenschiefer-Kupfererz | ores | 0.6 | 15.0 | 3.0 | Tiefenvariante |
| `GOLD_ORE` | Golderz | ores | 0.5 | 35.0 | 7.0 | Silk Touch Erz |
| `DEEPSLATE_GOLD_ORE` | Tiefenschiefer-Golderz | ores | 0.4 | 45.0 | 9.0 | Tiefenvariante |
| `LAPIS_ORE` | Lapislazulierz | ores | 0.4 | 40.0 | 8.0 | Zaubermaterial |
| `DEEPSLATE_LAPIS_ORE` | Tiefenschiefer-Lapiserz | ores | 0.3 | 55.0 | 11.0 | Seltene Tiefenader |
| `DIAMOND_ORE` | Diamanterz | ores | 0.2 | 350.0 | 80.0 | Hoher Sammlerwert |
| `DEEPSLATE_DIAMOND_ORE` | Tiefenschiefer-Diamanterz | ores | 0.2 | 400.0 | 90.0 | Sehr seltener Block |
| `EMERALD_ORE` | Smaragderz | ores | 0.1 | 500.0 | 100.0 | Nur in Bergen auffindbar |
| `DEEPSLATE_EMERALD_ORE` | Tiefenschiefer-Smaragderz | ores | 0.05 | 1500.0 | 300.0 | Extrem seltenes Sammlerstück |
| `ANCIENT_DEBRIS` | Antiker Schrott | ores | 0.1 | 1200.0 | 250.0 | Netherit-Grundstoff |
| `RAW_IRON` | Roheisen | raw_materials | 0.7 | 15.0 | 3.0 | Abbau mit Glück |
| `RAW_COPPER` | Rohkupfer | raw_materials | 0.8 | 6.0 | 1.2 | Hohe Dropmenge |
| `RAW_GOLD` | Rohgold | raw_materials | 0.5 | 25.0 | 5.0 | Abbau mit Glück |
| `RAW_IRON_BLOCK` | Roheisenblock | raw_materials | 0.7 | 135.0 | 27.0 | 9x Roheisen |
| `RAW_COPPER_BLOCK` | Rohkupferblock | raw_materials | 0.8 | 54.0 | 10.8 | 9x Rohkupfer |
| `RAW_GOLD_BLOCK` | Rohgoldblock | raw_materials | 0.5 | 225.0 | 45.0 | 9x Rohgold |
| `COAL` | Kohle | ingots | 0.7 | 8.0 | 1.6 | Wither-Skelett/Bergbau |
| `CHARCOAL` | Holzkohle | ingots | 0.8 | 6.0 | 1.2 | Gebranntes Holz |
| `IRON_INGOT` | Eisenbarren | ingots | 0.8 | 25.0 | 5.0 | Ratio 5:1 (Iron Golem Farm) |
| `COPPER_INGOT` | Kupferbarren | ingots | 0.8 | 10.0 | 2.0 | Massenmetall |
| `GOLD_INGOT` | Goldbarren | ingots | 0.6 | 45.0 | 9.0 | Piglin/Zombified Farm |
| `NETHERITE_SCRAP` | Netheritschrott | ingots | 0.1 | 1400.0 | 300.0 | Geschmolzener Debris |
| `NETHERITE_INGOT` | Netheritbarren | ingots | 0.1 | 6000.0 | 1250.0 | 4 Schrott + 4 Gold |
| `IRON_BLOCK` | Eisenblock | ingots | 0.8 | 225.0 | 45.0 | Kompaktblock |
| `COPPER_BLOCK` | Kupferblock | ingots | 0.8 | 90.0 | 18.0 | Kompaktblock |
| `GOLD_BLOCK` | Goldblock | ingots | 0.6 | 405.0 | 81.0 | Kompaktblock |
| `NETHERITE_BLOCK` | Netheritblock | ingots | 0.05 | 54000.0 | 11000.0 | Höchster Prestigeblock |
| `DIAMOND` | Diamant | gems | 0.2 | 300.0 | 75.0 | Ratio 4:1 (Edelstein) |
| `EMERALD` | Smaragd | gems | 0.5 | 150.0 | 30.0 | Villager-Handel |
| `LAPIS_LAZULI` | Lapislazuli | gems | 0.5 | 15.0 | 3.0 | Verzauberungswährung |
| `AMETHYST_SHARD` | Amethystscherbe | gems | 0.6 | 10.0 | 2.0 | Geodenfarmbar |
| `DIAMOND_BLOCK` | Diamantblock | gems | 0.2 | 2700.0 | 675.0 | 9x Diamant |
| `EMERALD_BLOCK` | Smaragdblock | gems | 0.5 | 1350.0 | 270.0 | 9x Smaragd |
| `LAPIS_BLOCK` | Lapisblock | gems | 0.5 | 135.0 | 27.0 | 9x Lapis |
| `AMETHYST_BLOCK` | Amethystblock | gems | 0.6 | 40.0 | 8.0 | Geodengestein |

---

### 3. farming.yml
*Subgruppen: `seeds`, `crops`, `food`, `plants`, `trees`*

| Material | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `WHEAT_SEEDS` | Weizensamen | seeds | 0.9 | 2.0 | 0.4 | Grasabbau / Feldwirtschaft |
| `PUMPKIN_SEEDS` | Kürbiskerne | seeds | 0.9 | 3.0 | 0.6 | Kürbiscrafting |
| `MELON_SEEDS` | Melonenkerne | seeds | 0.9 | 3.0 | 0.6 | Melonencrafting |
| `BEETROOT_SEEDS` | Rote-Bete-Samen | seeds | 0.8 | 2.0 | 0.4 | Feldwirtschaft |
| `TORCHFLOWER_SEEDS` | Fackelliliensamen | seeds | 0.3 | 60.0 | 12.0 | Sniffer-Ausgrabung |
| `PITCHER_POD` | Kannenpflanzenkapsel | seeds | 0.3 | 60.0 | 12.0 | Sniffer-Ausgrabung |
| `COCOA_BEANS` | Kakaobohnen | seeds | 0.8 | 5.0 | 1.0 | Tropenbaumfarmbar |
| `WHEAT` | Weizen | crops | 0.8 | 5.0 | 1.0 | Brot / Tierzucht |
| `CARROT` | Karotte | crops | 0.8 | 5.0 | 1.0 | Dorfbewohner / Farmbar |
| `POTATO` | Kartoffel | crops | 0.8 | 5.0 | 1.0 | Grundnahrungsmittel |
| `BEETROOT` | Rote Bete | crops | 0.8 | 4.0 | 0.8 | Rote Bete Suppe |
| `PUMPKIN` | Kürbis | crops | 0.9 | 2.0 | 0.4 | Extrem farmbar (Limit 500, Ratio 5:1) |
| `MELON` | Melone | crops | 0.9 | 2.0 | 0.4 | Blockvariante (Ratio 5:1) |
| `MELON_SLICE` | Melonenscheibe | crops | 0.9 | 0.5 | 0.1 | Bruchfrucht (Ratio 5:1) |
| `SUGAR_CANE` | Zuckerrohr | crops | 0.9 | 6.0 | 1.2 | Automatisierbar mit Piston |
| `CACTUS` | Kaktus | crops | 0.9 | 5.0 | 1.0 | Vollautomatisch farmbar |
| `BAMBOO` | Bambus | crops | 0.9 | 2.0 | 0.4 | Extrem hohe Wachstumsrate |
| `KELP` | Seetang | crops | 0.9 | 2.0 | 0.4 | Meerespflanze |
| `SWEET_BERRIES` | Süßbeeren | crops | 0.8 | 4.0 | 0.8 | Taiga-Busch |
| `GLOW_BERRIES` | Leuchtbeeren | crops | 0.7 | 8.0 | 1.6 | Üppige Höhlen |
| `APPLE` | Apfel | food | 0.6 | 8.0 | 1.6 | Laubdrop |
| `GOLDEN_APPLE` | Goldener Apfel | food | 0.3 | 120.0 | 25.0 | 8 Goldbarren + Apfel |
| `ENCHANTED_GOLDEN_APPLE` | Verzauberter Goldapfel | food | 0.0 | 10000.0 | 2000.0 | Nur Dungeon-Loot (Rare) |
| `BREAD` | Brot | food | 0.7 | 8.0 | 1.6 | 3x Weizen |
| `BEEF` | Rohes Rindfleisch | food | 0.7 | 6.0 | 1.2 | Tierzucht |
| `COOKED_BEEF` | Gebratenes Rindfleisch | food | 0.7 | 10.0 | 2.0 | Ausgezeichnete Sättigung |
| `PORKCHOP` | Rohes Schweinefleisch | food | 0.7 | 6.0 | 1.2 | Tierzucht |
| `COOKED_PORKCHOP` | Gebratenes Schweinefleisch | food | 0.7 | 10.0 | 2.0 | Ausgezeichnete Sättigung |
| `MUTTON` | Rohes Hammelfleisch | food | 0.7 | 5.0 | 1.0 | Schafzucht |
| `COOKED_MUTTON` | Gebratenes Hammelfleisch | food | 0.7 | 8.0 | 1.6 | Sättigung |
| `CHICKEN` | Rohes Hühnchen | food | 0.8 | 4.0 | 0.8 | Automatische Hühnerfarm |
| `COOKED_CHICKEN` | Gebratenes Hühnchen | food | 0.8 | 7.0 | 1.4 | Vollautomatisch erzeugbar |
| `COOKED_COD` | Gebratener Kabeljau | food | 0.7 | 6.0 | 1.2 | Meeresfisch |
| `COOKED_SALMON` | Gebratener Lachs | food | 0.7 | 8.0 | 1.6 | Meeresfisch |
| `GOLDEN_CARROT` | Goldene Karotte | food | 0.4 | 35.0 | 7.0 | Höchste Sättigung |
| `BAKED_POTATO` | Ofenkartoffel | food | 0.8 | 6.0 | 1.2 | Gute Survival-Nahrung |
| `HONEY_BOTTLE` | Honigflasche | food | 0.6 | 15.0 | 3.0 | Bienenstock |
| `CAKE` | Kuchen | food | 0.4 | 40.0 | 8.0 | Aufwendiges Crafting |
| `PUMPKIN_PIE` | Kürbiskuchen | food | 0.6 | 20.0 | 4.0 | Kürbis + Zucker + Ei |
| `BROWN_MUSHROOM` | Brauner Pilz | plants | 0.7 | 6.0 | 1.2 | Pilzzucht im Dunkeln |
| `RED_MUSHROOM` | Roter Pilz | plants | 0.7 | 6.0 | 1.2 | Pilzzucht im Dunkeln |
| `LILY_PAD` | Seerosenblatt | plants | 0.4 | 12.0 | 2.4 | Sumpf / Fischen |
| `OAK_SAPLING` | Eichensetzling | trees | 0.8 | 5.0 | 1.0 | Wiederaufforstung |
| `SPRUCE_SAPLING` | Fichtensetzling | trees | 0.8 | 5.0 | 1.0 | Schneller Großbaum |
| `BIRCH_SAPLING` | Birkensetzling | trees | 0.8 | 5.0 | 1.0 | Wiederaufforstung |
| `JUNGLE_SAPLING` | Tropensetzling | trees | 0.7 | 8.0 | 1.6 | 2x2 Baumzucht |
| `ACACIA_SAPLING` | Akaziensetzling | trees | 0.7 | 8.0 | 1.6 | Savanne |
| `DARK_OAK_SAPLING` | Schwarzeichensetzling | trees | 0.7 | 8.0 | 1.6 | 2x2 Baumzucht |
| `CHERRY_SAPLING` | Kirschblütensetzling | trees | 0.6 | 12.0 | 2.4 | Kirschblüten |
| `MANGROVE_PROPAGULE` | Mangrovenkeimling | trees | 0.6 | 15.0 | 3.0 | Mangrovensumpf |
| `AZALEA` | Azalee | trees | 0.6 | 10.0 | 2.0 | Üppige Höhlen |
| `FLOWERING_AZALEA` | Blühende Azalee | trees | 0.5 | 15.0 | 3.0 | Deko-Baum |

---

### 4. mobdrops.yml
*Subgruppen: `hostile_mobs`, `passive_mobs`, `bosses`, `utility`*

| Material | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `ROTTEN_FLESH` | Verrottetes Fleisch | hostile_mobs | 0.9 | 2.0 | 0.4 | Zombie-Massenloot (Limit 3000, Ratio 5:1) |
| `BONE` | Knochen | hostile_mobs | 0.8 | 8.0 | 1.6 | Skelettfarm / Knochenmehl |
| `STRING` | Faden | hostile_mobs | 0.8 | 6.0 | 1.2 | Spinnenfarm |
| `SPIDER_EYE` | Spinnenauge | hostile_mobs | 0.7 | 10.0 | 2.0 | Brauzutat |
| `GUNPOWDER` | Schwarzpulver | hostile_mobs | 0.8 | 20.0 | 4.0 | Creeperfarm (Ratio 5:1) |
| `SLIME_BALL` | Schleimball | hostile_mobs | 0.7 | 25.0 | 5.0 | Schleim-Chunks |
| `PHANTOM_MEMBRANE` | Phantomhaut | hostile_mobs | 0.4 | 50.0 | 10.0 | Elytren-Reparatur |
| `BREEZE_ROD` | Breeze-Rute | hostile_mobs | 0.3 | 120.0 | 25.0 | Neu in 1.21+ Trial Chambers |
| `FEATHER` | Feder | passive_mobs | 0.8 | 4.0 | 0.8 | Hühnerzucht / Pfeilbau |
| `LEATHER` | Leder | passive_mobs | 0.7 | 15.0 | 3.0 | Rinderzucht / Bücher |
| `EGG` | Ei | passive_mobs | 0.9 | 2.0 | 0.4 | Vollautomatisch farmbar (Ratio 5:1) |
| `INK_SAC` | Tintenbeutel | passive_mobs | 0.7 | 8.0 | 1.6 | Tintenfische |
| `GLOW_INK_SAC` | Leuchttintenbeutel | passive_mobs | 0.6 | 15.0 | 3.0 | Leuchttintenfische |
| `RABBIT_FOOT` | Hasenpfote | passive_mobs | 0.3 | 80.0 | 16.0 | Seltener Drop (Sprungkraft) |
| `RABBIT_HIDE` | Kaninchenfell | passive_mobs | 0.5 | 10.0 | 2.0 | Kaninchenzucht |
| `HONEYCOMB` | Honigwabe | passive_mobs | 0.7 | 12.0 | 2.4 | Bienenstock mit Schere |
| `TURTLE_SCUTE` | Schildkröten-Hornschild | passive_mobs | 0.3 | 60.0 | 12.0 | Auswachsen junger Schildkröten |
| `ARMADILLO_SCUTE` | Gürteltier-Hornschild | passive_mobs | 0.4 | 40.0 | 8.0 | Wolfsrüstungsbau |
| `NETHER_STAR` | Netherstern | bosses | 0.35 | 5000.0 | 1200.0 | Wither beliebig oft beschwörbar (Skelett-Schädel-Farm), aufwändig aber erneuerbar |
| `DRAGON_BREATH` | Drachenatem | bosses | 0.1 | 300.0 | 60.0 | Flasche im Enderdrachen-Kampf |
| `DRAGON_HEAD` | Drachenkopf | bosses | 0.05 | 4000.0 | 800.0 | Endschiffe |
| `TOTEM_OF_UNDYING` | Totem der Unsterblichkeit | utility | 0.35 | 1500.0 | 300.0 | Garantierter Evoker-Drop, Dorf-Raid-Farm beliebig wiederholbar, aufwändig aber erneuerbar |
| `SADDLE` | Sattel | utility | 0.3 | 250.0 | 50.0 | Dungeons / Raids / Angeln |
| `LEAD` | Leine | utility | 0.6 | 15.0 | 3.0 | Schleimball + 4 Fäden |
| `NAME_TAG` | Namensschild | utility | 0.3 | 400.0 | 80.0 | Dungeons / Angeln / Villager |

---

### 5. redstone.yml
*Subgruppen: `components`, `mechanisms`, `rails`, `light_sources`*

| Material | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `REDSTONE` | Redstone-Staub | components | 0.7 | 6.0 | 1.2 | Bergbau / Hexenfarm |
| `REDSTONE_BLOCK` | Redstone-Block | components | 0.7 | 54.0 | 10.8 | 9x Redstone |
| `REDSTONE_ORE` | Redstone-Erz | components | 0.4 | 40.0 | 8.0 | Silk Touch (Hauptquelle Redstone) |
| `DEEPSLATE_REDSTONE_ORE` | Tiefenschiefer-Redstone-Erz | components | 0.3 | 50.0 | 10.0 | Tiefenvariante |
| `REDSTONE_TORCH` | Redstone-Fackel | components | 0.7 | 5.0 | 1.0 | Signalgeber |
| `REPEATER` | Redstone-Verstärker | components | 0.6 | 15.0 | 3.0 | Verzögerung / Signalstärkung |
| `COMPARATOR` | Redstone-Komparator | components | 0.5 | 25.0 | 5.0 | Enthält Netherquarz |
| `TARGET` | Zielblock | components | 0.6 | 20.0 | 4.0 | Heuballen + Redstone |
| `OBSERVER` | Beobachter | components | 0.6 | 30.0 | 6.0 | Block-Update-Sensor |
| `CRAFTER` | Crafter | components | 0.4 | 150.0 | 30.0 | Autocrafting-Block (1.21+) |
| `COPPER_BULB` | Kupferlampe | components | 0.6 | 45.0 | 9.0 | T-Flip-Flop Lampe |
| `DAYLIGHT_DETECTOR` | Tageslichtsensor | components | 0.6 | 35.0 | 7.0 | Lichtsensor |
| `SCULK_SENSOR` | Sculk-Sensor | components | 0.3 | 120.0 | 25.0 | Akustischer Sensor |
| `CALIBRATED_SCULK_SENSOR` | Kalibrierter Sculk-Sensor | components | 0.3 | 180.0 | 36.0 | Frequenzfilterung |
| `LIGHTNING_ROD` | Blitzableiter | components | 0.7 | 25.0 | 5.0 | 3x Kupfer |
| `PISTON` | Kolben | mechanisms | 0.6 | 30.0 | 6.0 | Holz + Stein + Eisen + Redstone |
| `STICKY_PISTON` | Klebriger Kolben | mechanisms | 0.6 | 50.0 | 10.0 | Kolben + Schleimball |
| `DISPENSER` | Werfer | mechanisms | 0.6 | 35.0 | 7.0 | Bogen + Redstone + Pflasterstein |
| `DROPPER` | Spender | mechanisms | 0.7 | 20.0 | 4.0 | Item-Auswurf |
| `HOPPER` | Trichter | mechanisms | 0.6 | 120.0 | 25.0 | 5 Eisen + Kiste |
| `LEVER` | Hebel | mechanisms | 0.8 | 3.0 | 0.6 | Manueller Schalter |
| `STONE_BUTTON` | Steinknopf | mechanisms | 0.8 | 3.0 | 0.6 | Kurzer Impuls |
| `OAK_BUTTON` | Eichenholzknopf | mechanisms | 0.8 | 2.0 | 0.4 | Impulsgeber |
| `TRIPWIRE_HOOK` | Haken | mechanisms | 0.7 | 15.0 | 3.0 | Stolperdraht-Sensor |
| `TRAPPED_CHEST` | Redstone-Truhe | mechanisms | 0.6 | 30.0 | 6.0 | Truhe + Haken |
| `NOTE_BLOCK` | Notenblock | mechanisms | 0.7 | 20.0 | 4.0 | Akustik |
| `JUKEBOX` | Plattenspieler | mechanisms | 0.3 | 350.0 | 70.0 | Benötigt 1 Diamant |
| `TNT` | TNT | mechanisms | 0.7 | 80.0 | 16.0 | 5 Pulver + 4 Sand |
| `IRON_DOOR` | Eisentür | mechanisms | 0.7 | 50.0 | 10.0 | Sicherungstür |
| `IRON_TRAPDOOR` | Eisenfalltür | mechanisms | 0.7 | 80.0 | 16.0 | Falltür |
| `RAIL` | Schiene | rails | 0.7 | 12.0 | 2.4 | Eisen + Stock (16 Stück pro Craft) |
| `POWERED_RAIL` | Antriebsschiene | rails | 0.6 | 40.0 | 8.0 | Gold + Redstone |
| `DETECTOR_RAIL` | Sensorschiene | rails | 0.6 | 25.0 | 5.0 | Druckauslöser |
| `ACTIVATOR_RAIL` | Aktivierungsschiene | rails | 0.6 | 25.0 | 5.0 | Rauswurf / TNT-Zündung |
| `MINECART` | Lore | rails | 0.7 | 100.0 | 20.0 | 5 Eisenbarren |
| `CHEST_MINECART` | Güterlore | rails | 0.6 | 120.0 | 24.0 | Lore + Truhe |
| `HOPPER_MINECART` | Trichterlore | rails | 0.6 | 220.0 | 44.0 | Lore + Trichter |
| `TNT_MINECART` | TNT-Lore | rails | 0.6 | 180.0 | 36.0 | Lore + TNT |
| `REDSTONE_LAMP` | Redstone-Lampe | light_sources | 0.6 | 45.0 | 9.0 | Glowstone + 4 Redstone |
| `LANTERN` | Laterne | light_sources | 0.7 | 20.0 | 4.0 | Fackel + 8 Eisennuggets |
| `SOUL_LANTERN` | Seelenlaterne | light_sources | 0.6 | 25.0 | 5.0 | Seelenfeuer-Deko |

---

### 6. ocean.yml
*Subgruppen: `sponges`, `corals`, `prismarine`, `sea_lanterns`*

| Material | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `SPONGE` | Schwamm | sponges | 0.2 | 400.0 | 80.0 | Ozeanmonument-Trocknung |
| `WET_SPONGE` | Nasser Schwamm | sponges | 0.2 | 350.0 | 70.0 | Monument-Loot |
| `TUBE_CORAL_BLOCK` | Röhrenkorallenblock | corals | 0.3 | 30.0 | 6.0 | Warmwasser-Ozean |
| `BRAIN_CORAL_BLOCK` | Hirnkorallenblock | corals | 0.3 | 30.0 | 6.0 | Warmwasser-Ozean |
| `BUBBLE_CORAL_BLOCK` | Blasenkorallenblock | corals | 0.3 | 30.0 | 6.0 | Warmwasser-Ozean |
| `FIRE_CORAL_BLOCK` | Feuerkorallenblock | corals | 0.3 | 30.0 | 6.0 | Warmwasser-Ozean |
| `HORN_CORAL_BLOCK` | Geweihkorallenblock | corals | 0.3 | 30.0 | 6.0 | Warmwasser-Ozean |
| `TUBE_CORAL` | Röhrenkoralle | corals | 0.3 | 15.0 | 3.0 | Korallenpflanze |
| `BRAIN_CORAL` | Hirnkoralle | corals | 0.3 | 15.0 | 3.0 | Korallenpflanze |
| `BUBBLE_CORAL` | Blasenkoralle | corals | 0.3 | 15.0 | 3.0 | Korallenpflanze |
| `FIRE_CORAL` | Feuerkoralle | corals | 0.3 | 15.0 | 3.0 | Korallenpflanze |
| `HORN_CORAL` | Geweihkoralle | corals | 0.3 | 15.0 | 3.0 | Korallenpflanze |
| `PRISMARINE` | Prismarin | prismarine | 0.6 | 15.0 | 3.0 | Wächterfarmbar |
| `PRISMARINE_BRICKS` | Prismarinziegel | prismarine | 0.6 | 25.0 | 5.0 | 9x Prismarinscherben |
| `DARK_PRISMARINE` | Dunkler Prismarin | prismarine | 0.6 | 30.0 | 6.0 | Prismarin + Tintenbeutel |
| `PRISMARINE_SHARD` | Prismarinscherbe | prismarine | 0.7 | 4.0 | 0.8 | Wächter-Drop |
| `PRISMARINE_CRYSTALS` | Prismarinkristalle | prismarine | 0.6 | 8.0 | 1.6 | Wächter-Drop (Lichtblock) |
| `SEA_LANTERN` | Seelaterne | sea_lanterns | 0.6 | 60.0 | 12.0 | Monument-Lichtblock |
| `CONDUIT` | Aquisator | sea_lanterns | 0.2 | 1500.0 | 300.0 | Herz des Meeres + Schalen |
| `HEART_OF_THE_SEA` | Herz des Meeres | sea_lanterns | 0.1 | 1200.0 | 250.0 | Vergrabene Schatztruhe |
| `NAUTILUS_SHELL` | Nautilus-Schale | sea_lanterns | 0.4 | 150.0 | 30.0 | Ertrunkene / Angeln |
| `TURTLE_EGG` | Schildkrötenei | sea_lanterns | 0.3 | 100.0 | 20.0 | Silk Touch auf Strand |

---

### 7. nether_end.yml
*Subgruppen: `nether_blocks`, `nether_items`, `end_blocks`, `end_items`*

| Material | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `NETHERRACK` | Netherstein | nether_blocks | 0.9 | 1.5 | 0.3 | Extrem häufiger Netherblock |
| `NETHER_BRICKS` | Netherziegel | nether_blocks | 0.8 | 6.0 | 1.2 | Gebrannter Netherstein |
| `RED_NETHER_BRICKS` | Rote Netherziegel | nether_blocks | 0.7 | 8.0 | 1.6 | Netherziegel + Netherwarzen |
| `CRACKED_NETHER_BRICKS` | Rissige Netherziegel | nether_blocks | 0.6 | 10.0 | 2.0 | Gebrannt |
| `CHISELED_NETHER_BRICKS` | Gemeißelte Netherziegel | nether_blocks | 0.6 | 12.0 | 2.4 | Zierblock |
| `SOUL_SAND` | Seelensand | nether_blocks | 0.7 | 6.0 | 1.2 | Wasseraufzug / Witherbau |
| `SOUL_SOIL` | Seelenerde | nether_blocks | 0.7 | 6.0 | 1.2 | Seelenfeuergrundlage |
| `GLOWSTONE` | Glowstone | nether_blocks | 0.6 | 20.0 | 4.0 | 4x Glowstone-Staub |
| `GLOWSTONE_DUST` | Glowstone-Staub | nether_blocks | 0.7 | 5.0 | 1.0 | Hexenfarm / Nether |
| `BLACKSTONE` | Schwarzstein | nether_blocks | 0.8 | 3.0 | 0.6 | Ersatz für Bruchstein |
| `POLISHED_BLACKSTONE` | Polierter Schwarzstein | nether_blocks | 0.8 | 4.0 | 0.8 | Baublock |
| `POLISHED_BLACKSTONE_BRICKS` | Polierte Schwarzsteinziegel | nether_blocks | 0.7 | 5.0 | 1.0 | Architektur |
| `GILDED_BLACKSTONE` | Golddurchwirkter Schwarzstein | nether_blocks | 0.3 | 60.0 | 12.0 | Bastions-Rest |
| `CRIMSON_STEM` | Karmesinstamm | nether_blocks | 0.7 | 9.0 | 1.8 | Karmesin-Pilzholz |
| `CRIMSON_PLANKS` | Karmesinbretter | nether_blocks | 0.7 | 2.25 | 0.45 | Feuerfestes Holz |
| `WARPED_STEM` | Wirrstamm | nether_blocks | 0.7 | 9.0 | 1.8 | Wirr-Pilzholz |
| `WARPED_PLANKS` | Wirrbretter | nether_blocks | 0.7 | 2.25 | 0.45 | Türkises Netherholz |
| `CRIMSON_NYLIUM` | Karmesin-Nezel | nether_blocks | 0.6 | 12.0 | 2.4 | Silk Touch auf Netherstein |
| `WARPED_NYLIUM` | Wirr-Nezel | nether_blocks | 0.6 | 12.0 | 2.4 | Silk Touch auf Netherstein |
| `SHROOMLIGHT` | Zwielichtpilz | nether_blocks | 0.6 | 25.0 | 5.0 | Riesige Netherpilze |
| `MAGMA_BLOCK` | Magmablock | nether_blocks | 0.7 | 8.0 | 1.6 | Strömungsfalle / Schadeffekt |
| `NETHER_WART` | Netherwarze | nether_items | 0.7 | 6.0 | 1.2 | Grundstoff für Tränke |
| `BLAZE_ROD` | Lohenrute | nether_items | 0.6 | 40.0 | 8.0 | Lohenfarm / Brauzutat |
| `BLAZE_POWDER` | Lohenstaub | nether_items | 0.6 | 20.0 | 4.0 | Braustoff / Enderaugen |
| `GHAST_TEAR` | Ghast-Träne | nether_items | 0.4 | 120.0 | 25.0 | Regenerations-Tränke |
| `MAGMA_CREAM` | Magmacreme | nether_items | 0.7 | 15.0 | 3.0 | Feuerresistenz-Tränke |
| `WITHER_SKELETON_SKULL` | Witherskelettschädel | nether_items | 0.35 | 800.0 | 180.0 | Fortress-AFK-Farm möglich (Plünderung III erhöht Dropchance), aufwändig aber erneuerbar |
| `END_STONE` | Endstein | end_blocks | 0.7 | 4.0 | 0.8 | Abbau in den End-Inseln |
| `END_STONE_BRICKS` | Endsteinziegel | end_blocks | 0.7 | 5.0 | 1.0 | Ziegelvariante |
| `PURPUR_BLOCK` | Purpurblock | end_blocks | 0.7 | 8.0 | 1.6 | Geplatzte Chorusfrucht |
| `PURPUR_PILLAR` | Purpursäule | end_blocks | 0.7 | 10.0 | 2.0 | Ziersäule |
| `END_ROD` | Endstab | end_blocks | 0.6 | 25.0 | 5.0 | Lichtquelle |
| `CHORUS_FRUIT` | Chorusfrucht | end_items | 0.7 | 5.0 | 1.0 | Teleportationsnahrung |
| `POPPED_CHORUS_FRUIT` | Geplatzte Chorusfrucht | end_items | 0.7 | 6.0 | 1.2 | Gebrannt |
| `SHULKER_SHELL` | Shulker-Schale | end_items | 0.35 | 450.0 | 100.0 | Duplikationsmechanik seit 1.17: aus einem geborgenen Shulker unbegrenzt farmbar, aufwändig aber erneuerbar (nicht mit DIAMOND-Klasse verwechseln) |
| `ELYTRA` | Elytren | end_items | 0.05 | 8000.0 | 1600.0 | Seltenes Endschiff-Fluggerät |
| `DRAGON_EGG` | Drachenei | end_items | 0.0 | false | 15000.0 | buy: false (Unikat, nur erspielbar) |
| `HEAVY_CORE` | Schwerer Kern | end_items | 0.05 | false | 5000.0 | buy: false (Mace-Kern, Trial Chamber) |
| `TRIAL_KEY` | Prüfungsschlüssel | end_items | 0.2 | false | 500.0 | buy: false (Belohnungsauslöser) |
| `OMINOUS_TRIAL_KEY` | Unheilvoller Prüfungsschlüssel | end_items | 0.1 | false | 1200.0 | buy: false (High-Tier Belohnung) |

---

### 8. decorations.yml
*Subgruppen: `dyes`, `flowers`, `banners`, `pottery`*

| Material | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `WHITE_DYE` | Weißer Farbstoff | dyes | 0.8 | 4.0 | 0.8 | Knochenmehl / Maiglöckchen |
| `ORANGE_DYE` | Orangener Farbstoff | dyes | 0.7 | 4.0 | 0.8 | Aus Blumen / Mischung |
| `MAGENTA_DYE` | Magenta Farbstoff | dyes | 0.7 | 4.0 | 0.8 | Aus Blumen / Allium |
| `LIGHT_BLUE_DYE` | Hellblauer Farbstoff | dyes | 0.7 | 4.0 | 0.8 | Blausternchen |
| `YELLOW_DYE` | Gelber Farbstoff | dyes | 0.8 | 4.0 | 0.8 | Löwenzahn / Sonnenblumen |
| `LIME_DYE` | Hellgrüner Farbstoff | dyes | 0.8 | 5.0 | 1.0 | Seetang / Kaktus gebrannt |
| `PINK_DYE` | Rosa Farbstoff | dyes | 0.7 | 4.0 | 0.8 | Pfingstrose / Tulpe |
| `GRAY_DYE` | Grauer Farbstoff | dyes | 0.7 | 4.0 | 0.8 | Schwarz + Weiß |
| `LIGHT_GRAY_DYE` | Hellgrauer Farbstoff | dyes | 0.7 | 4.0 | 0.8 | Margerite |
| `CYAN_DYE` | Türkiser Farbstoff | dyes | 0.7 | 4.0 | 0.8 | Blau + Grün |
| `PURPLE_DYE` | Violetter Farbstoff | dyes | 0.7 | 4.0 | 0.8 | Rot + Blau |
| `BLUE_DYE` | Blauer Farbstoff | dyes | 0.7 | 4.0 | 0.8 | Kornblume / Lapis |
| `BROWN_DYE` | Brauner Farbstoff | dyes | 0.7 | 4.0 | 0.8 | Kakaobohnen |
| `GREEN_DYE` | Grüner Farbstoff | dyes | 0.8 | 5.0 | 1.0 | Gebrannter Kaktus |
| `RED_DYE` | Roter Farbstoff | dyes | 0.8 | 4.0 | 0.8 | Mohn / Rote Bete |
| `BLACK_DYE` | Schwarzer Farbstoff | dyes | 0.7 | 4.0 | 0.8 | Tintenbeutel / Witherrose |
| `DANDELION` | Löwenzahn | flowers | 0.7 | 8.0 | 1.6 | Wiesenblume |
| `POPPY` | Mohn | flowers | 0.8 | 6.0 | 1.2 | Eisengolem-Nebenprodukt |
| `BLUE_ORCHID` | Blaue Orchidee | flowers | 0.4 | 15.0 | 3.0 | Sumpfblume |
| `ALLIUM` | Sternlauch | flowers | 0.4 | 15.0 | 3.0 | Blumenwald |
| `AZURE_BLUET` | Porzellansternchen | flowers | 0.5 | 10.0 | 2.0 | Wiesenblume |
| `RED_TULIP` | Rote Tulpe | flowers | 0.5 | 12.0 | 2.4 | Blumenwald / Ebene |
| `ORANGE_TULIP` | Orangene Tulpe | flowers | 0.5 | 12.0 | 2.4 | Blumenwald |
| `WHITE_TULIP` | Weiße Tulpe | flowers | 0.5 | 12.0 | 2.4 | Blumenwald |
| `PINK_TULIP` | Rosa Tulpe | flowers | 0.5 | 12.0 | 2.4 | Blumenwald |
| `OXEYE_DAISY` | Margerite | flowers | 0.5 | 10.0 | 2.0 | Wiesenblume |
| `CORNFLOWER` | Kornblume | flowers | 0.6 | 8.0 | 1.6 | Wiesenblume |
| `LILY_OF_THE_VALLEY` | Maiglöckchen | flowers | 0.4 | 15.0 | 3.0 | Waldblume |
| `WITHER_ROSE` | Wither-Rose | flowers | 0.3 | 80.0 | 16.0 | Wither-Tötung von Mobs |
| `TORCHFLOWER` | Fackellilie | flowers | 0.3 | 80.0 | 16.0 | Sniffer-Aufzucht |
| `PITCHER_PLANT` | Kannenpflanze | flowers | 0.3 | 80.0 | 16.0 | Sniffer-Aufzucht |
| `SUNFLOWER` | Sonnenblume | flowers | 0.6 | 15.0 | 3.0 | Hohe Blume |
| `LILAC` | Flieder | flowers | 0.6 | 15.0 | 3.0 | Hohe Blume |
| `ROSE_BUSH` | Rosenstrauch | flowers | 0.6 | 15.0 | 3.0 | Hohe Blume |
| `PEONY` | Pfingstrose | flowers | 0.6 | 15.0 | 3.0 | Hohe Blume |
| `WHITE_BANNER` | Weißes Banner | banners | 0.6 | 30.0 | 6.0 | Wolle + Stock |
| `BLACK_BANNER` | Schwarzes Banner | banners | 0.6 | 35.0 | 7.0 | Wolle + Stock |
| `RED_BANNER` | Rotes Banner | banners | 0.6 | 35.0 | 7.0 | Wolle + Stock |
| `BLUE_BANNER` | Blaues Banner | banners | 0.6 | 35.0 | 7.0 | Wolle + Stock |
| `FLOWER_POT` | Blumentopf | pottery | 0.7 | 10.0 | 2.0 | 3 gebrannte Ziegel |
| `DECORATED_POT` | Verzierter Krug | pottery | 0.4 | 50.0 | 10.0 | 4x Tonscherben oder Ziegel |
| `ANGLER_POTTERY_SHERD` | Angler-Tonscherbe | pottery | 0.2 | 150.0 | 30.0 | Archäologie-Fund |
| `ARCHER_POTTERY_SHERD` | Bogenschützen-Scherbe | pottery | 0.2 | 150.0 | 30.0 | Archäologie-Fund |
| `MINER_POTTERY_SHERD` | Minenarbeiter-Scherbe | pottery | 0.2 | 150.0 | 30.0 | Archäologie-Fund |
| `SKULL_POTTERY_SHERD` | Totenkopf-Scherbe | pottery | 0.2 | 150.0 | 30.0 | Archäologie-Fund |
| `FLOW_POTTERY_SHERD` | Wind-Tonscherbe | pottery | 0.2 | 200.0 | 40.0 | Trial Chamber Fund |
| `GUSTER_POTTERY_SHERD` | Wirbel-Tonscherbe | pottery | 0.2 | 200.0 | 40.0 | Trial Chamber Fund |

---

### 9. tools.yml
*Subgruppen: `pickaxes`, `axes`, `swords`, `shovels`, `hoe`*
*Regel: Alle Werkzeuge besitzen `sell: false` zum Schutz vor Haltbarkeits- & Verzauberungsmissbrauch.*

| Material | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `WOODEN_PICKAXE` | Holzspitzhacke | pickaxes | 0.0 | 20.0 | false | sell: false |
| `STONE_PICKAXE` | Steinspitzhacke | pickaxes | 0.0 | 40.0 | false | sell: false |
| `IRON_PICKAXE` | Eisenspitzhacke | pickaxes | 0.0 | 150.0 | false | sell: false |
| `GOLDEN_PICKAXE` | Goldspitzhacke | pickaxes | 0.0 | 200.0 | false | sell: false |
| `DIAMOND_PICKAXE` | Diamantspitzhacke | pickaxes | 0.0 | 1000.0 | false | sell: false |
| `NETHERITE_PICKAXE` | Netheritspitzhacke | pickaxes | 0.0 | 7500.0 | false | sell: false |
| `WOODEN_AXE` | Holzaxt | axes | 0.0 | 20.0 | false | sell: false |
| `STONE_AXE` | Steinaxt | axes | 0.0 | 40.0 | false | sell: false |
| `IRON_AXE` | Eisenaxt | axes | 0.0 | 150.0 | false | sell: false |
| `GOLDEN_AXE` | Goldaxt | axes | 0.0 | 200.0 | false | sell: false |
| `DIAMOND_AXE` | Diamantaxt | axes | 0.0 | 1000.0 | false | sell: false |
| `NETHERITE_AXE` | Netheritaxt | axes | 0.0 | 7500.0 | false | sell: false |
| `WOODEN_SWORD` | Holzschwert | swords | 0.0 | 15.0 | false | sell: false |
| `STONE_SWORD` | Steinschwert | swords | 0.0 | 30.0 | false | sell: false |
| `IRON_SWORD` | Eisenschwert | swords | 0.0 | 100.0 | false | sell: false |
| `GOLDEN_SWORD` | Goldschwert | swords | 0.0 | 150.0 | false | sell: false |
| `DIAMOND_SWORD` | Diamantschwert | swords | 0.0 | 700.0 | false | sell: false |
| `NETHERITE_SWORD` | Netheritschwert | swords | 0.0 | 7000.0 | false | sell: false |
| `MACE` | Streitkolben | swords | 0.0 | 8000.0 | false | Schwerer Kern + Breeze-Rute |
| `TRIDENT` | Dreizack | swords | 0.0 | 2500.0 | false | Ertrunkenen-Drop |
| `WOODEN_SHOVEL` | Holzschaufel | shovels | 0.0 | 10.0 | false | sell: false |
| `STONE_SHOVEL` | Steinschaufel | shovels | 0.0 | 20.0 | false | sell: false |
| `IRON_SHOVEL` | Eisenschaufel | shovels | 0.0 | 60.0 | false | sell: false |
| `GOLDEN_SHOVEL` | Goldschaufel | shovels | 0.0 | 80.0 | false | sell: false |
| `DIAMOND_SHOVEL` | Diamantschaufel | shovels | 0.0 | 350.0 | false | sell: false |
| `NETHERITE_SHOVEL` | Netheritschaufel | shovels | 0.0 | 6500.0 | false | sell: false |
| `WOODEN_HOE` | Holzhacke | hoe | 0.0 | 15.0 | false | sell: false |
| `STONE_HOE` | Steinhacke | hoe | 0.0 | 30.0 | false | sell: false |
| `IRON_HOE` | Eisenhacke | hoe | 0.0 | 100.0 | false | sell: false |
| `GOLDEN_HOE` | Goldhacke | hoe | 0.0 | 150.0 | false | sell: false |
| `DIAMOND_HOE` | Diamanthacke | hoe | 0.0 | 700.0 | false | sell: false |
| `NETHERITE_HOE` | Netherithacke | hoe | 0.0 | 7000.0 | false | sell: false |
| `BOW` | Bogen | swords | 0.0 | 80.0 | false | Fernkampfwaffe |
| `CROSSBOW` | Armbrust | swords | 0.0 | 150.0 | false | Fernkampfwaffe |
| `FISHING_ROD` | Angel | hoe | 0.0 | 40.0 | false | Werkzeug |
| `SHEARS` | Schere | hoe | 0.0 | 50.0 | false | 2 Eisenbarren |
| `FLINT_AND_STEEL` | Feuerzeug | hoe | 0.0 | 40.0 | false | Eisen + Feuerstein |
| `BRUSH` | Pinsel | hoe | 0.0 | 60.0 | false | Archäologie-Pinsel |

---

### 10. armor.yml
*Subgruppen: `helmets`, `chestplates`, `leggings`, `boots`*
*Regel: Alle Rüstungsteile besitzen `sell: false`.*

| Material | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `LEATHER_HELMET` | Lederkappe | helmets | 0.0 | 80.0 | false | sell: false |
| `CHAINMAIL_HELMET` | Kettenhaube | helmets | 0.0 | 300.0 | false | Nicht craftbar |
| `IRON_HELMET` | Eisenhelm | helmets | 0.0 | 250.0 | false | sell: false |
| `GOLDEN_HELMET` | Goldhelm | helmets | 0.0 | 350.0 | false | Piglin-Neutralität |
| `DIAMOND_HELMET` | Diamanthelm | helmets | 0.0 | 1500.0 | false | sell: false |
| `NETHERITE_HELMET` | Netherithelm | helmets | 0.0 | 8000.0 | false | Höchster Schutz |
| `TURTLE_HELMET` | Schildkrötenpanzer | helmets | 0.0 | 600.0 | false | Wasseratmungs-Bonus |
| `LEATHER_CHESTPLATE` | Lederharnisch | chestplates | 0.0 | 120.0 | false | sell: false |
| `CHAINMAIL_CHESTPLATE` | Kettenhemd | chestplates | 0.0 | 500.0 | false | Nicht craftbar |
| `IRON_CHESTPLATE` | Eisenbrustplatte | chestplates | 0.0 | 400.0 | false | sell: false |
| `GOLDEN_CHESTPLATE` | Goldbrustplatte | chestplates | 0.0 | 500.0 | false | sell: false |
| `DIAMOND_CHESTPLATE` | Diamantbrustplatte | chestplates | 0.0 | 2400.0 | false | sell: false |
| `NETHERITE_CHESTPLATE` | Netheritbrustplatte | chestplates | 0.0 | 9500.0 | false | Höchster Schutz |
| `LEATHER_LEGGINGS` | Lederhose | leggings | 0.0 | 100.0 | false | sell: false |
| `CHAINMAIL_LEGGINGS` | Kettenbeinschutz | leggings | 0.0 | 400.0 | false | Nicht craftbar |
| `IRON_LEGGINGS` | Eisenbeinschutz | leggings | 0.0 | 350.0 | false | sell: false |
| `GOLDEN_LEGGINGS` | Goldbeinschutz | leggings | 0.0 | 450.0 | false | sell: false |
| `DIAMOND_LEGGINGS` | Diamantbeinschutz | leggings | 0.0 | 2100.0 | false | sell: false |
| `NETHERITE_LEGGINGS` | Netheritbeinschutz | leggings | 0.0 | 9000.0 | false | Höchster Schutz |
| `LEATHER_BOOTS` | Lederstiefel | boots | 0.0 | 70.0 | false | Pulverschnee-Schutz |
| `CHAINMAIL_BOOTS` | Kettenstiefel | boots | 0.0 | 250.0 | false | Nicht craftbar |
| `IRON_BOOTS` | Eisenstiefel | boots | 0.0 | 200.0 | false | sell: false |
| `GOLDEN_BOOTS` | Goldstiefel | boots | 0.0 | 300.0 | false | sell: false |
| `DIAMOND_BOOTS` | Diamantstiefel | boots | 0.0 | 1200.0 | false | sell: false |
| `NETHERITE_BOOTS` | Netheritstiefel | boots | 0.0 | 7500.0 | false | Höchster Schutz |
| `SHIELD` | Schild | boots | 0.0 | 80.0 | false | Blockiert Angriffe |
| `WOLF_ARMOR` | Wolfsrüstung | chestplates | 0.0 | 300.0 | false | Aus Gürteltier-Schuppen |

---

### 11. enchantments.yml
*Subgruppen: `weapons`, `armor`, `tools`, `fishing`, `misc`*
*Regel: Alle Verzauberungsbücher besitzen `sell: false`.*

| Material / Buch-Kennung | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `SHARPNESS_5_BOOK` | Buch: Schärfe V | weapons | 0.0 | 1200.0 | false | Nahkampfschaden |
| `SMITE_5_BOOK` | Buch: Bann V | weapons | 0.0 | 800.0 | false | Untotenschaden |
| `BANE_OF_ARTHROPODS_5_BOOK` | Buch: Nemesis der Gliederfüßer V | weapons | 0.0 | 500.0 | false | Spinnenschaden |
| `KNOCKBACK_2_BOOK` | Buch: Rückstoß II | weapons | 0.0 | 600.0 | false | Zurückstoßen |
| `FIRE_ASPECT_2_BOOK` | Buch: Verbrennung II | weapons | 0.0 | 1000.0 | false | Feuerschaden |
| `LOOTING_3_BOOK` | Buch: Plünderung III | weapons | 0.0 | 1800.0 | false | Mehr Mob-Drops |
| `SWEEPING_EDGE_3_BOOK` | Buch: Schwungkraft III | weapons | 0.0 | 1000.0 | false | Flächenschaden |
| `POWER_5_BOOK` | Buch: Stärke V | weapons | 0.0 | 1200.0 | false | Bogenschaden |
| `PUNCH_2_BOOK` | Buch: Schlag II | weapons | 0.0 | 600.0 | false | Bogen-Rückstoß |
| `FLAME_BOOK` | Buch: Flamme | weapons | 0.0 | 800.0 | false | Feuerpfeile |
| `INFINITY_BOOK` | Buch: Unendlichkeit | weapons | 0.0 | 1500.0 | false | Unendliche Pfeile |
| `MULTISHOT_BOOK` | Buch: Dreifachschuss | weapons | 0.0 | 800.0 | false | Armbrust |
| `QUICK_CHARGE_3_BOOK` | Buch: Schnelles Laden III | weapons | 0.0 | 1000.0 | false | Armbrust |
| `PIERCING_4_BOOK` | Buch: Durchschuss IV | weapons | 0.0 | 1000.0 | false | Armbrust |
| `IMPALING_5_BOOK` | Buch: Harpune V | weapons | 0.0 | 1000.0 | false | Dreizack |
| `RIPTIDE_3_BOOK` | Buch: Sog III | weapons | 0.0 | 1500.0 | false | Dreizack-Flug im Regen |
| `LOYALTY_3_BOOK` | Buch: Treue III | weapons | 0.0 | 1200.0 | false | Rückkehrender Dreizack |
| `CHANNELING_BOOK` | Buch: Entladung | weapons | 0.0 | 1000.0 | false | Blitzeinschlag bei Gewitter |
| `DENSITY_5_BOOK` | Buch: Dichte V | weapons | 0.0 | 2000.0 | false | Mace-Verzauberung (1.21+) |
| `BREACH_4_BOOK` | Buch: Rüstungsbruch IV | weapons | 0.0 | 2000.0 | false | Mace-Verzauberung (1.21+) |
| `WIND_BURST_3_BOOK` | Buch: Windstoß III | weapons | 0.0 | 3500.0 | false | Mace-Ominous Belohnung |
| `PROTECTION_4_BOOK` | Buch: Schutz IV | armor | 0.0 | 1500.0 | false | Universeller Rüstungsschutz |
| `FIRE_PROTECTION_4_BOOK` | Buch: Feuerschutz IV | armor | 0.0 | 800.0 | false | Hitzeschutz |
| `FEATHER_FALLING_4_BOOK` | Buch: Federfall IV | armor | 0.0 | 1200.0 | false | Fallschadensreduktion |
| `BLAST_PROTECTION_4_BOOK` | Buch: Explosionsschutz IV | armor | 0.0 | 800.0 | false | Explosionsabwehr |
| `PROJECTILE_PROTECTION_4_BOOK` | Buch: Schuss-Sicherheit IV | armor | 0.0 | 800.0 | false | Projektilschutz |
| `RESPIRATION_3_BOOK` | Buch: Atmung III | armor | 0.0 | 1000.0 | false | Verlängerte Unterwasseratmung |
| `AQUA_AFFINITY_BOOK` | Buch: Wasseraffinität | armor | 0.0 | 800.0 | false | Normales Abbauen im Wasser |
| `THORNS_3_BOOK` | Buch: Dornen III | armor | 0.0 | 1200.0 | false | Gegenangriff auf Angreifer |
| `DEPTH_STRIDER_3_BOOK` | Buch: Wasserläufer III | armor | 0.0 | 1200.0 | false | Schnelles Schwimmen |
| `FROST_WALKER_2_BOOK` | Buch: Eisläufer II | armor | 0.0 | 1000.0 | false | Eisbildung auf Wasser |
| `SOUL_SPEED_3_BOOK` | Buch: Seelentempo III | armor | 0.0 | 1500.0 | false | Schnelligkeit auf Seelensand |
| `SWIFT_SNEAK_3_BOOK` | Buch: Huschen III | armor | 0.0 | 2500.0 | false | Ancient City Exklusiv |
| `EFFICIENCY_5_BOOK` | Buch: Effizienz V | tools | 0.0 | 1500.0 | false | Schnelleres Abbauen |
| `SILK_TOUCH_BOOK` | Buch: Behutsamkeit | tools | 0.0 | 2000.0 | false | Erhält Originalblock |
| `FORTUNE_3_BOOK` | Buch: Glück III | tools | 0.0 | 2000.0 | false | Höhere Dropmengen |
| `LUCK_OF_THE_SEA_3_BOOK` | Buch: Glück des Meeres III | fishing | 0.0 | 800.0 | false | Bessere Angelbeute |
| `LURE_3_BOOK` | Buch: Köder III | fishing | 0.0 | 800.0 | false | Schnellere Bisse |
| `UNBREAKING_3_BOOK` | Buch: Haltbarkeit III | misc | 0.0 | 1500.0 | false | Längere Lebensdauer |
| `MENDING_BOOK` | Buch: Reparatur | misc | 0.0 | 3000.0 | false | Beliebteste Verzauberung |

---

### 12. potions.yml
*Subgruppen: `regular`, `splash`, `lingering`, `custom`*
*Regel: Alle Tränke besitzen `sell: false`.*

| Material / Kennung | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `POTION_NIGHT_VISION` | Trank der Nachtsicht (8:00) | regular | 0.0 | 60.0 | false | sell: false |
| `POTION_INVISIBILITY` | Trank der Unsichtbarkeit (8:00) | regular | 0.0 | 80.0 | false | sell: false |
| `POTION_LEAPING` | Trank der Sprungkraft II | regular | 0.0 | 70.0 | false | sell: false |
| `POTION_FIRE_RESISTANCE` | Trank der Feuerresistenz (8:00) | regular | 0.0 | 70.0 | false | sell: false |
| `POTION_SWIFTNESS` | Trank der Schnelligkeit II | regular | 0.0 | 60.0 | false | sell: false |
| `POTION_SLOWNESS` | Trank der Verlangsamung | regular | 0.0 | 50.0 | false | sell: false |
| `POTION_WATER_BREATHING` | Trank der Unterwasseratmung (8:00) | regular | 0.0 | 60.0 | false | sell: false |
| `POTION_HEALING` | Trank der Heilung II | regular | 0.0 | 70.0 | false | sell: false |
| `POTION_HARMING` | Trank des Schadens II | regular | 0.0 | 70.0 | false | sell: false |
| `POTION_POISON` | Trank des Giftes | regular | 0.0 | 60.0 | false | sell: false |
| `POTION_REGENERATION` | Trank der Regeneration II | regular | 0.0 | 100.0 | false | sell: false |
| `POTION_STRENGTH` | Trank der Stärke II | regular | 0.0 | 100.0 | false | sell: false |
| `POTION_WEAKNESS` | Trank der Schwäche (4:00) | regular | 0.0 | 50.0 | false | Zombie-Villager Heilung |
| `POTION_SLOW_FALLING` | Trank des Sanften Falls (4:00) | regular | 0.0 | 80.0 | false | sell: false |
| `POTION_TURTLE_MASTER` | Trank des Schildkrötenmeisters | regular | 0.0 | 120.0 | false | sell: false |
| `POTION_WIND_CHARGED` | Windgeladener Trank | regular | 0.0 | 120.0 | false | 1.21+ Effekt |
| `POTION_WEAVING` | Webender Trank | regular | 0.0 | 120.0 | false | 1.21+ Effekt |
| `POTION_OOZING` | Schleimender Trank | regular | 0.0 | 120.0 | false | 1.21+ Effekt |
| `POTION_INFESTED` | Befallener Trank | regular | 0.0 | 120.0 | false | 1.21+ Effekt |
| `SPLASH_POTION_HEALING` | Wurftrank der Heilung II | splash | 0.0 | 90.0 | false | Schnelle Heilung im Kampf |
| `SPLASH_POTION_HARMING` | Wurftrank des Schadens II | splash | 0.0 | 90.0 | false | PvP / Mobkampf |
| `SPLASH_POTION_REGENERATION` | Wurftrank der Regeneration II | splash | 0.0 | 120.0 | false | Team-Heilung |
| `SPLASH_POTION_FIRE_RESISTANCE` | Wurftrank der Feuerresistenz | splash | 0.0 | 90.0 | false | Schnelle Rettung in Lava |
| `SPLASH_POTION_WEAKNESS` | Wurftrank der Schwäche | splash | 0.0 | 70.0 | false | Zombiedorfbewohner-Heilung |
| `SPLASH_POTION_STRENGTH` | Wurftrank der Stärke II | splash | 0.0 | 120.0 | false | Kampf-Buff |
| `LINGERING_POTION_HEALING` | Verweiltrank der Heilung II | lingering | 0.0 | 140.0 | false | Verweilende Heilzone |
| `LINGERING_POTION_HARMING` | Verweiltrank des Schadens II | lingering | 0.0 | 140.0 | false | Verweilende Schadenszone |
| `LINGERING_POTION_POISON` | Verweiltrank des Giftes | lingering | 0.0 | 120.0 | false | Verweilendes Gift |
| `EXPERIENCE_BOTTLE` | Erfahrungsfläschchen | custom | 0.4 | 50.0 | false | Schnelle XP-Quelle |

---

### 13. spawners.yml
*Subgruppen: `mob_spawners`*
*Regel: Alle Spawner besitzen `buy: false` (können nicht gekauft werden, um unendliche AFK-Wirtschaft zu verhindern; nur Verkauf belohnt den Spieler).*

| Material / Typ | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `SPAWNER` | Standard Spawner | mob_spawners | 0.0 | false | 25000.0 | buy: false |
| `ZOMBIE_SPAWNER` | Zombie-Spawner | mob_spawners | 0.0 | false | 25000.0 | Dungeon-Fund |
| `SKELETON_SPAWNER` | Skelett-Spawner | mob_spawners | 0.0 | false | 30000.0 | Knochen-/Pfeilquelle |
| `SPIDER_SPAWNER` | Spinnen-Spawner | mob_spawners | 0.0 | false | 25000.0 | Fadenquelle |
| `CAVE_SPIDER_SPAWNER` | Höhlenspinnen-Spawner | mob_spawners | 0.0 | false | 28000.0 | Minenschacht-Fund |
| `CREEPER_SPAWNER` | Creeper-Spawner | mob_spawners | 0.0 | false | 50000.0 | Sehr wertvoll |
| `BLAZE_SPAWNER` | Lohen-Spawner | mob_spawners | 0.0 | false | 40000.0 | Netherfestung |
| `SILVERFISH_SPAWNER` | Silberfisch-Spawner | mob_spawners | 0.0 | false | 15000.0 | Festung / Endportal |
| `MAGMA_CUBE_SPAWNER` | Magmawürfel-Spawner | mob_spawners | 0.0 | false | 35000.0 | Bastions-Fund |
| `PIG_SPAWNER` | Schweine-Spawner | mob_spawners | 0.0 | false | 20000.0 | Friedlicher Spawner |
| `COW_SPAWNER` | Kuh-Spawner | mob_spawners | 0.0 | false | 25000.0 | Leder & Fleisch |
| `SHEEP_SPAWNER` | Schaf-Spawner | mob_spawners | 0.0 | false | 20000.0 | Wollquelle |
| `CHICKEN_SPAWNER` | Hühner-Spawner | mob_spawners | 0.0 | false | 18000.0 | Geflügelquelle |
| `IRON_GOLEM_SPAWNER` | Eisengolem-Spawner | mob_spawners | 0.0 | false | 100000.0 | Höchste Stufe |

---

### 14. custom_items.yml
*Subgruppen: `server_specific`*

| Material / Kennung | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `SERVER_TOKEN` | Server-Münze / Token | server_specific | 0.0 | 500.0 | 100.0 | Event-Währung / Questbelohnung |
| `VOTE_CRATE_KEY` | Vote-Kisten-Schlüssel | server_specific | 0.0 | 250.0 | false | Nur Kaufen oder durch Voting |
| `COMMUNITY_BADGE` | Community-Abzeichen | server_specific | 0.0 | 1000.0 | 200.0 | Kosmetisches Rang-Item |

---

### 15. misc.yml
*Subgruppen: `utility`, `transport`, `miscellaneous`*

| Material | Anzeigename | Subgruppe | Farmbarkeit | Buy | Sell | Notizen |
|:---|:---|:---|:---:|:---:|:---:|:---|
| `ENDER_PEARL` | Enderperle | utility | 0.6 | 50.0 | 10.0 | Enderman-Farm im End (AFK-fähig, 3000-6000/h) — deutlich besser farmbar als bisher eingestuft (Ratio 5:1) |
| `EYE_OF_ENDER` | Enderauge | utility | 0.3 | 80.0 | 16.0 | Festungsfinder |
| `COMPASS` | Kompass | utility | 0.5 | 40.0 | 8.0 | Orientierung |
| `RECOVERY_COMPASS` | Bergungskompass | utility | 0.1 | 500.0 | 100.0 | Zeigt letzten Todespunkt |
| `CLOCK` | Uhr | utility | 0.5 | 40.0 | 8.0 | 4 Gold + Redstone |
| `SPYGLASS` | Fernrohr | utility | 0.4 | 50.0 | 10.0 | Amethyst + Kupfer |
| `FIREWORK_ROCKET` | Feuerwerksrakete | utility | 0.7 | 15.0 | 3.0 | Flugantrieb für Elytren |
| `FIREWORK_STAR` | Feuerwerksstern | utility | 0.6 | 15.0 | 3.0 | Farbeffekt |
| `BUNDLE` | Beutel | utility | 0.5 | 60.0 | 12.0 | Inventar-Kompaktierung |
| `CARROT_ON_A_STICK` | Karottenrute | transport | 0.6 | 25.0 | 5.0 | Schweinereiten |
| `WARPED_FUNGUS_ON_A_STICK` | Wirrpilzrute | transport | 0.6 | 30.0 | 6.0 | Ausschreiter-Reiten |
| `OAK_BOAT` | Eichenholzboot | transport | 0.7 | 15.0 | 3.0 | Wasserfahrzeug |
| `SPRUCE_BOAT` | Fichtenholzboot | transport | 0.7 | 15.0 | 3.0 | Wasserfahrzeug |
| `BIRCH_BOAT` | Birkenholzboot | transport | 0.7 | 15.0 | 3.0 | Wasserfahrzeug |
| `JUNGLE_BOAT` | Tropenholzboot | transport | 0.7 | 15.0 | 3.0 | Wasserfahrzeug |
| `ACACIA_BOAT` | Akazienholzboot | transport | 0.7 | 15.0 | 3.0 | Wasserfahrzeug |
| `DARK_OAK_BOAT` | Schwarzeichenboot | transport | 0.7 | 15.0 | 3.0 | Wasserfahrzeug |
| `MANGROVE_BOAT` | Mangrovenboot | transport | 0.6 | 20.0 | 4.0 | Wasserfahrzeug |
| `CHERRY_BOAT` | Kirschblütenboot | transport | 0.6 | 20.0 | 4.0 | Wasserfahrzeug |
| `BAMBOO_RAFT` | Bambusfloß | transport | 0.8 | 15.0 | 3.0 | Floß |
| `BELL` | Glocke | miscellaneous | 0.2 | 600.0 | 120.0 | Dorfgong (Nicht craftbar) |
| `BOOK_AND_QUILL` | Buch und Feder | miscellaneous | 0.6 | 30.0 | 6.0 | Beschreibbares Buch |
| `OMINOUS_BOTTLE` | Unheilvolle Flasche | miscellaneous | 0.3 | 250.0 | 50.0 | Raid-Auslöser (1.21+) |

---

## 🔄 **Änderungen gegenüber Vorversion**

- **Hinzugefügt (Neue moderne Minecraft-Features):**
  - Waffen & Tools: `MACE`, `WIND_BURST_3`, `DENSITY_5`, `BREACH_4`, `BRUSH`.
  - Blöcke: `TUFF_BRICKS`, `CHISELED_TUFF_BRICKS`, `TUFF_TILES`, `POLISHED_TUFF`, `COPPER_BULB`, `CRAFTER`.
  - Trial Chambers & Ominous Loot: `TRIAL_KEY`, `OMINOUS_TRIAL_KEY`, `HEAVY_CORE`, `BREEZE_ROD`, `OMINOUS_BOTTLE`, neue Tonscherben (`FLOW`, `GUSTER`).
  - Tränke: `POTION_WIND_CHARGED`, `POTION_WEAVING`, `POTION_OOZING`, `POTION_INFESTED`.
  - Schutz & Begleiter: `WOLF_ARMOR`, `ARMADILLO_SCUTE`.
- **Regel-Harmonisierung:**
  - Konsequente Anwendung von `sell: false` bei allen verzauberbaren/nutzbaren Ausrüstungsgegenständen, Tränken und Zauberbüchern.
  - Buy:Sell-Ratios strikt zwischen `3.0` und `5.0` kalibriert.
  - Extrem farmbare Güter (z. B. Kürbisse, Melonen, Bruchstein, Zombiefleisch) mit geringen Ankaufspreisen versehen, vorbereitet für tägliche Verkaufslimits in Phase 3.

---

## ✅ **Validierung**

- [x] Alle 15 Ziel-Kategorien vollständig mit Subgruppen und Items ausgestattet.
- [x] Keine Duplikate über die verschiedenen Shop-Kategorien hinweg.
- [x] Eindeutige Zuweisung nach Hauptverwendungszweck gemäß `PROCESSES/ITEM_SELECTION.md`.
- [x] Realistische Farmbarkeitswerte von `0.0` bis `1.0`.
- [x] Alle Spezialregeln (`buy: false` für Unikate/Spawner, `sell: false` für Tools/Armor/Potions/Books) strikt eingehalten.
- [x] Ratios liegen durchgängig im erlaubten Fenster von 3:1 bis 5:1 (sofern beide Preise aktiv).

---

*Letzte Aktualisierung: 2026-09-28*
