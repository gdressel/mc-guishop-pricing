# Item-Mapping für GUIShop

**Minecraft-Version:** [Hier Version eintragen, z. B. 26.3 — Minecraft nutzt seit 2026 das Jahres-Schema `JJ.N` statt `1.x.x`, siehe [Versionshistorie](https://minecraft.wiki/w/Java_Edition_version_history)]

---

## 📌 **Hinweise zur Nutzung dieser Vorlage**

1. **Jedes Item muss genau einer Kategorie und Subgruppe zugeordnet werden.**
2. **Farmbarkeit:** 0.0 (nicht farmbar) – 1.0 (extrem farmbar).
3. **Buy/Sell:** Nur eintragen, wenn abweichend von den Standard-Regeln in `RULES.md`.
4. **Notizen:** Kurze Begründung für Besonderheiten (z. B. "Neu in 26.3").

---

## 📁 **Kategorien & Subgruppen**

### blocks.yml
*Subgruppen: stones, wood, glass, concrete, terracotta, wool*

| Material       | Anzeigename     | Subgruppe | Farmbarkeit | Buy  | Sell | Notizen          |
|----------------|-----------------|-----------|-------------|------|------|------------------|
| COBBLESTONE    | Kopfstein       | stones    | 0.9         | 2.0  | 0.4  | Extrem farmbar   |
| STONE          | Stein           | stones    | 0.8         | 4.0  | 0.8  | Farmbar          |
| OAK_LOG        | Eichenholz      | wood      | 0.7         | 8.0  | 1.0  | Holzblock        |
| SPRUCE_LOG     | Fichtenholz     | wood      | 0.7         | 8.0  | 1.0  | Holzblock        |
| GLASS          | Glas            | glass     | 0.3         | 6.0  | 1.5  | Nicht farmbar    |
| WHITE_WOOL     | Weiße Wolle     | wool      | 0.7         | 10.0 | 2.0  | Farmbar (Sheep)  |

### minerals.yml
*Subgruppen: ores, ingots, gems, raw_materials*

| Material       | Anzeigename     | Subgruppe   | Farmbarkeit | Buy   | Sell | Notizen          |
|----------------|-----------------|-------------|-------------|-------|------|------------------|
| IRON_ORE       | Eisen-Erz       | ores        | 0.6         | 15.0  | 3.0  | Bergbau          |
| IRON_INGOT     | Eisenbarren     | ingots      | 0.8         | 25.0  | 5.0  | Iron Farm       |
| GOLD_INGOT     | Goldbarren      | ingots      | 0.5         | 50.0  | 10.0 | Nicht einfach farmbar |
| DIAMOND        | Diamant         | gems        | 0.2         | 300.0 | 75.0 | Selten           |
| EMERALD        | Smaragd         | gems        | 0.3         | 200.0 | 50.0 | Nicht farmbar    |

### farming.yml
*Subgruppen: seeds, crops, food, plants, trees*

| Material       | Anzeigename     | Subgruppe | Farmbarkeit | Buy  | Sell | Notizen          |
|----------------|-----------------|-----------|-------------|------|------|------------------|
| WHEAT_SEEDS    | Weizen-Samen    | seeds     | 0.8         | 2.0  | 0.5  | Farmbar          |
| WHEAT          | Weizen          | crops     | 0.8         | 6.0  | 1.0  | Farmbar          |
| CARROT         | Karotte         | crops     | 0.8         | 6.0  | 1.0  | Farmbar          |
| PUMPKIN        | Kürbis          | crops     | 0.9         | 10.0 | 0.2  | Extrem farmbar  |
| BREAD          | Brot            | food      | 0.0         | 8.0  | 2.0  | Nicht farmbar    |

### mobdrops.yml
*Subgruppen: hostile_mobs, passive_mobs, bosses, utility*

| Material       | Anzeigename     | Subgruppe     | Farmbarkeit | Buy   | Sell | Notizen          |
|----------------|-----------------|---------------|-------------|-------|------|------------------|
| GUNPOWDER      | Schießpulver    | hostile_mobs   | 0.7         | 20.0  | 4.0  | Creepers        |
| BONE           | Knochen         | hostile_mobs   | 0.7         | 15.0  | 3.0  | Skelette        |
| STRING         | Faden           | hostile_mobs   | 0.8         | 10.0  | 2.0  | Spinnen         |
| LEATHER        | Leder           | passive_mobs   | 0.5         | 25.0  | 5.0  | Kühe            |
| DRAGON_SCALE   | Drachenschuppe  | bosses         | 0.0         | false | 5000.0 | Ender Dragon   |

### redstone.yml
*Subgruppen: components, mechanisms, rails, light_sources*

| Material       | Anzeigename     | Subgruppe    | Farmbarkeit | Buy   | Sell | Notizen          |
|----------------|-----------------|--------------|-------------|-------|------|------------------|
| REDSTONE       | Redstone        | components   | 0.5         | 10.0  | 2.0  | Bergbau          |
| LEVER          | Hebel           | mechanisms   | 0.0         | 15.0  | 3.0  | Nicht farmbar    |
| BUTTON         | Knopf           | mechanisms   | 0.0         | 10.0  | 2.0  | Nicht farmbar    |
| POWERED_RAIL   | Angetriebene Schiene | rails   | 0.0         | 30.0  | 6.0  | Nicht farmbar    |
| REDSTONE_TORCH | Redstone-Fackel | light_sources | 0.4   | 20.0  | 4.0  | Farmbar          |

### ocean.yml
*Subgruppen: sponges, corals, prismarine, sea_lanterns*

| Material       | Anzeigename     | Subgruppe    | Farmbarkeit | Buy    | Sell | Notizen          |
|----------------|-----------------|--------------|-------------|--------|------|------------------|
| SPONGE         | Schwamm         | sponges      | 0.2         | 500.0 | 100.0 | Selten          |
| TUBE_CORAL     | Röhrenkoralle   | corals       | 0.3         | 20.0  | 4.0  | Nicht einfach farmbar |
| PRISMARINE     | Prismarin       | prismarine   | 0.1         | 100.0 | 20.0 | Selten          |

### nether_end.yml
*Subgruppen: nether_blocks, nether_items, end_blocks, end_items*

| Material       | Anzeigename     | Subgruppe    | Farmbarkeit | Buy     | Sell  | Notizen          |
|----------------|-----------------|--------------|-------------|---------|-------|------------------|
| NETHERRACK     | Nether-Gestein  | nether_blocks | 0.6       | 5.0    | 1.0   | Farmbar          |
| BLAZE_ROD      | Blaze-Rute      | nether_items | 0.4       | 80.0   | 16.0  | Blaze Farm       |
| END_STONE      | End-Stein       | end_blocks   | 0.1       | 50.0   | 10.0  | Selten           |
| DRAGON_EGG     | Drachenei       | end_items    | 0.0       | false  | 10000.0 | Einmalig       |
| HEAVY_CORE     | Schwerer Kern   | end_items    | 0.0       | false  | 5000.0 | Neu in 1.21 "Tricky Trials" |
| TRIAL_KEY      | Prüfungs-Schlüssel | end_items | 0.0     | false  | 1000.0 | Neu in 1.21 "Tricky Trials" |

### decorations.yml
*Subgruppen: dyes, flowers, banners, pottery*

| Material       | Anzeigename     | Subgruppe | Farmbarkeit | Buy  | Sell | Notizen          |
|----------------|-----------------|-----------|-------------|------|------|------------------|
| RED_DYE        | Roter Farbstoff | dyes      | 0.7         | 5.0  | 1.0  | Farmbar          |
| ROSE_BUSH       | Rosenstrauch    | flowers   | 0.3         | 20.0 | 4.0  | Nicht einfach farmbar |
| WHITE_BANNER    | Weißes Banner    | banners   | 0.1         | 50.0 | 10.0 | Selten          |

### tools.yml
*Subgruppen: pickaxes, axes, swords, shovels, hoe*

| Material            | Anzeigename          | Subgruppe | Farmbarkeit | Buy    | Sell | Notizen          |
|---------------------|-----------------------|-----------|-------------|--------|------|------------------|
| WOODEN_PICKAXE      | Holz-Spitzhacke       | pickaxes  | 0.0         | 50.0   | false | sell: false (Missbrauchsschutz) |
| DIAMOND_PICKAXE     | Diamant-Spitzhacke    | pickaxes  | 0.0         | 1000.0 | false | sell: false (Missbrauchsschutz) |
| NETHERITE_SWORD     | Netherit-Schwert     | swords    | 0.0         | 5000.0 | false | sell: false (Missbrauchsschutz) |

### armor.yml
*Subgruppen: helmets, chestplates, leggings, boots*

| Material            | Anzeigename          | Subgruppe     | Farmbarkeit | Buy     | Sell | Notizen          |
|---------------------|-----------------------|---------------|-------------|---------|------|------------------|
| LEATHER_HELMET      | Leder-Helm            | helmets      | 0.0         | 80.0    | false | sell: false (Missbrauchsschutz) |
| DIAMOND_CHESTPLATE  | Diamant-Brustplatte   | chestplates  | 0.0         | 2000.0  | false | sell: false (Missbrauchsschutz) |
| NETHERITE_BOOTS     | Netherit-Stiefel      | boots        | 0.0         | 3000.0  | false | sell: false (Missbrauchsschutz) |

### enchantments.yml
*Subgruppen: weapons, armor, tools, fishing, misc*
*Hinweis: GUIShop kennt keine eigene Material-ID pro Verzauberung — `id: ENCHANTED_BOOK` + `enchantments: 'NAME:LEVEL'`.*

| Material            | Anzeigename          | Subgruppe | Farmbarkeit | Buy     | Sell | Notizen          |
|---------------------|-----------------------|-----------|-------------|---------|------|------------------|
| ENCHANTED_BOOK (`SHARPNESS:1`)     | Schärfe I            | weapons   | 0.0         | 100.0   | false | sell: false (Missbrauchsschutz) |
| ENCHANTED_BOOK (`PROTECTION:4`)    | Schutz IV             | armor     | 0.0         | 2000.0  | false | sell: false (Missbrauchsschutz) |
| ENCHANTED_BOOK (`EFFICIENCY:5`)     | Effizienz V           | tools     | 0.0         | 1500.0  | false | sell: false (Missbrauchsschutz) |

### potions.yml
*Subgruppen: regular, splash, lingering, custom*
*Hinweis: GUIShop kennt keine eigene Material-ID pro Effekt — `id: POTION`/`SPLASH_POTION`/`LINGERING_POTION` + `potion-info:`-Block (`type`, `splash`, `lingering`, `extended`, `upgraded`).*

| Material            | Anzeigename          | Subgruppe | Farmbarkeit | Buy   | Sell | Notizen          |
|---------------------|-----------------------|-----------|-------------|-------|------|------------------|
| POTION (`type: STRENGTH`)  | Trank der Stärke     | regular   | 0.0         | 50.0  | false | sell: false (Missbrauchsschutz) |
| SPLASH_POTION (`type: STRENGTH, splash: true`)      | Wurftrank der Stärke        | splash    | 0.0         | 100.0 | false | sell: false (Missbrauchsschutz) |

### spawners.yml
*Subgruppen: mob_spawners*

| Material            | Anzeigename          | Subgruppe     | Farmbarkeit | Buy  | Sell   | Notizen          |
|---------------------|-----------------------|---------------|-------------|------|--------|------------------|
| SPAWNER             | Standard-Spawner      | mob_spawners  | 0.0         | false | 25000.0 | buy: false (nicht kaufbar) |
| SPAWNER (`mob-type: CREEPER`) | Creeper-Spawner | mob_spawners | 0.0    | false | 50000.0 | buy: false (nicht kaufbar) — GUIShop kennt keine eigene `CREEPER_SPAWNER`-Material-ID, Mob-Typ wird über `mob-type:` gesetzt |

### custom_items.yml
*Subgruppen: server_specific*

| Material            | Anzeigename          | Subgruppe         | Farmbarkeit | Buy   | Sell | Notizen          |
|---------------------|-----------------------|-------------------|-------------|-------|------|------------------|
| (Leer – für Plugins wie ItemsAdder) | - | server_specific | - | - | - | - |

### misc.yml
*Subgruppen: utility, transport, miscellaneous*

| Material       | Anzeigename     | Subgruppe   | Farmbarkeit | Buy   | Sell | Notizen          |
|----------------|-----------------|-------------|-------------|-------|------|------------------|
| ENDER_PEARL    | Ender-Perle    | utility     | 0.6         | 60.0  | 12.0 | AFK-fähige Enderman-Farm (siehe `RESEARCH_SOURCES.md` Abschnitt 6b) |
| FLINT_AND_STEEL | Feuerzeug      | utility     | 0.0         | 20.0  | 4.0  | Nicht farmbar    |
| NAME_TAG       | Namensschild   | miscellaneous | 0.0     | 1000.0 | 200.0 | Selten          |

---

## 🔄 **Änderungen gegenüber Vorversion**

- **Hinzugefügt:** [Liste neuer Items, mit Quellenangabe statt Vermutung, z. B. "TRIAL_KEY, HEAVY_CORE (neu in 1.21 'Tricky Trials')"]
- **Entfernt:** [Liste entfernter Items]
- **Anpassungen:** [Liste geänderter Zuordnungen oder Farmbarkeit-Werte, z. B. "Farmbarkeit von IRON_INGOT von 0.7 auf 0.8 erhöht (neue Iron Farm-Methoden)"]

---

## ✅ **Validierung**

- [ ] Alle Vanilla-Items der Version [X.X.X] abgedeckt.
- [ ] Keine Duplikate in den Zuordnungen.
- [ ] Jedes Item hat eine **klare Kategorie/Subgruppe**.
- [ ] Farmbarkeit-Werte sind **realistisch**. 
- [ ] Alle neuen Items aus Version [X.X.X] enthalten.
- [ ] Alle `false`-Regeln (sell/buy) korrekt angewendet.
