# Kernprozess A: Items bestimmen & gruppieren

**Zweck:** Vollständige Liste aller relevanten Vanilla-Items für die aktuelle Minecraft-Version erstellen und in die **15 Shop-Kategorien + Subgruppen** einteilen.
**Wiederholbar:** Dieser Prozess muss **bei jedem Minecraft-Update** oder bei manueller Überprüfung durchlaufen werden.

---

## 📋 **Schritt-für-Schritt-Anleitung**

---

### **Schritt 1: Minecraft-Version festlegen**
**Aktion:**
- Lege die **Zielversion** fest (z. B. `26.3`).
- Dokumentiere die Version in **`ITEM_MAPPING.md`** (Header).
- **Hinweis zum Versionsschema:** Seit 2026 verwendet Minecraft Java Edition kein `1.x.x`-Schema mehr; die letzte `1.x`-Version war `1.21`. Aktuelle Versionen folgen dem Jahres-Schema `JJ.N` (z. B. `26.1`, `26.2`, `26.3`). Prüfe vor der Dokumentation immer die [offizielle Versionshistorie](https://minecraft.wiki/w/Java_Edition_version_history), statt eine Version zu vermuten.

**Beispiel:**
```markdown
# Item-Mapping für GUIShop
**Minecraft-Version:** 26.3
```

---

### **Schritt 2: Vollständige Item-Liste erstellen**
**Ziel:** Alle **Vanilla-Items/Blöcke** der Zielversion in einer Tabelle erfassen.

**Quellen:**
1. [Minecraft Wiki – Liste aller Blöcke](https://minecraft.wiki/w/Block)
2. [Minecraft Wiki – Liste aller Items](https://minecraft.wiki/w/Item)
3. [Spigot/Paper `Material`-Enum (Javadocs)](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html) (für die technischen Bukkit-API-Namen, die `id:` in den Shop-Configs erwartet — **nicht** die Minecraft-Wiki-"Data Values"-Seiten, die vanilla Identifier/Legacy-Zahlen-IDs dokumentieren, keine Bukkit-Materialnamen)

**Methode:**
1. Gehe durch die **offiziellen Listen** und notiere **jeden relevanten Eintrag**.
2. **Filtere irrelevante Items** heraus:
   - Entwickler-Items (z. B. `DEBUG_STICK`, `BARRIER`)
   - Unbrauchbare Items (z. B. `AIR`, `STRUCTURE_VOID`)
   -Technische Items (z. B. `COMMAND_BLOCK`, `CHAIN_COMMAND_BLOCK`)
3. **Erfasse für jedes Item die folgenden Daten:**

| **Feld**          | **Beispiel**       | **Beschreibung**                          | **Quelle**                     |
|------------------|-------------------|------------------------------------------|--------------------------------|
| Material-Name    | `COBBLESTONE`     | Offizieller Spigot/Paper-Materialname.   | Spigot/Paper `Material`-Enum   |
| Anzeigename      | `Kopfstein`       | Deutsch/Englisch (je nach Server).        | Minecraft Wiki                 |
| Typ              | `Block`           | Block/Item/Tool/Armor/Enchanted/Other.     | Eigenes Urteil                |
| Farmbarkeit      | `0.9`             | 0.0 (nicht farmbar) – 1.0 (extrem farmbar). | Eigenes Urteil + Community-Diskussionen |
| Vanilla          | `true`            | Ob Item aus Vanilla-Minecraft stammt.     | Immer `true` für Vanilla-Items |

**Beispiel-Tabelle (Ausschnitt):**

| Material-Name    | Anzeigename       | Typ    | Farmbarkeit | Vanilla |
|------------------|-------------------|--------|-------------|---------|
| COBBLESTONE      | Kopfstein         | Block  | 0.9         | true    |
| STONE            | Stein             | Block  | 0.8         | true    |
| OAK_LOG          | Eichenholzstamm   | Block  | 0.7         | true    |
| IRON_INGOT       | Eisenbarren       | Item   | 0.8         | true    |
| DIAMOND          | Diamant           | Item   | 0.2         | true    |
| DIAMOND_PICKAXE  | Diamant-Spitzhacke| Tool   | 0.0         | true    |
| DRAGON_EGG       | Drachenei         | Item   | 0.0         | true    |
| SPAWNER          | Mob-Spawner       | Block  | 0.0         | true    |

---

### **Schritt 3: Kategorien & Subgruppen definieren**
**Feste Struktur:** Nutze die **15 Shop-Kategorien** aus dem Hauptplan.

**Subgruppen pro Kategorie:**

| **Kategorie**       | **Subgruppen**                                                                 | **Beispiele**                          |
|----------------------|------------------------------------------------------------------------------|----------------------------------------|
| `blocks.yml`         | `stones`, `wood`, `glass`, `concrete`, `terracotta`, `wool`                 | COBBLESTONE, OAK_LOG, GLASS            |
| `minerals.yml`       | `ores`, `ingots`, `gems`, `raw_materials`                                    | IRON_ORE, GOLD_INGOT, DIAMOND          |
| `farming.yml`        | `seeds`, `crops`, `food`, `plants`, `trees`                                 | WHEAT_SEEDS, PUMPKIN, BREAD            |
| `mobdrops.yml`       | `hostile_mobs`, `passive_mobs`, `bosses`, `utility`                         | GUNPOWDER, BONE, DRAGON_SCALE          |
| `redstone.yml`       | `components`, `mechanisms`, `rails`, `light_sources`                        | REDSTONE, LEVER, POWERED_RAIL          |
| `ocean.yml`          | `sponges`, `corals`, `prismarine`, `sea_lanterns`                            | SPONGE, TUBE_CORAL, PRISMARINE         |
| `nether_end.yml`     | `nether_blocks`, `nether_items`, `end_blocks`, `end_items`                 | NETHERRACK, BLAZE_ROD, END_STONE        |
| `decorations.yml`    | `dyes`, `flowers`, `banners`, `pottery`                                     | RED_DYE, ROSE_BUSH, WHITE_BANNER      |
| `tools.yml`          | `pickaxes`, `axes`, `swords`, `shovels`, `hoe`                               | WOODEN_PICKAXE, DIAMOND_AXE           |
| `armor.yml`          | `helmets`, `chestplates`, `leggings`, `boots`                               | LEATHER_HELMET, NETHERITE_BOOTS       |
| `enchantments.yml`  | `weapons`, `armor`, `tools`, `fishing`, `misc`                              | SHARPNESS_1_BOOK, PROTECTION_4_BOOK   |
| `potions.yml`        | `regular`, `splash`, `lingering`, `custom`                                  | POTION_OF_STRENGTH, SPLASH_POTION     |
| `spawners.yml`       | `mob_spawners`                                                                 | SPAWNER, CREEPER_SPAWNER               |
| `custom_items.yml`   | `server_specific`                                                             | (Leer – für Plugins wie ItemsAdder)   |
| `misc.yml`           | `utility`, `transport`, `miscellaneous`                                       | ENDER_PEARL, FLINT_AND_STEEL, NAME_TAG |

---

### **Schritt 4: Items den Subgruppen zuweisen**
**Regeln für die Zuordnung:**

1. **Primäre Verwendung:**
   - **Beispiel:** `REDSTONE_ORE` → **`redstone.yml`** (Subgruppe: `ores`) **und nicht** `minerals.yml`.
   - **Begründung:** Der **Hauptzweck** des Items entscheidet über die Kategorie.
   - **Ausnahme:** Falls ein Item **gleichwertig** in zwei Kategorien passt, entscheide nach **häufigster Nutzung** (z. B. `REDSTONE_TORCH` → `redstone.yml`).

2. **Sonderfälle:**
   - **Server-spezifische Items** (z. B. aus Plugins wie ItemsAdder) → **`custom_items.yml`**.
   - **Items ohne klare Kategorie** → **`misc.yml`**.

3. **Validierung:**
   - **Jedes Item darf nur in einer Subgruppe** vorkommen.
   - **Keine Duplikate** in der finalen Liste.

**Beispiel-Zuordnung:**

| Material-Name    | Kategorie       | Subgruppe     | Farmbarkeit | Begründung                     |
|------------------|-----------------|---------------|-------------|----------------------------------|
| COBBLESTONE      | blocks          | stones        | 0.9         | Extrem farmbar (Generator)       |
| OAK_LOG          | blocks          | wood          | 0.7         | Holzblock                       |
| IRON_INGOT       | minerals        | ingots        | 0.8         | Metallbarren                    |
| DIAMOND          | minerals        | gems          | 0.2         | Edelstein                       |
| REDSTONE_ORE     | redstone        | ores          | 0.5         | Redstone-Quelle                 |
| LEVER            | redstone        | mechanisms    | 0.0         | Redstone-Mechanismus            |
| GUNPOWDER        | mobdrops        | hostile_mobs   | 0.7         | Creepers droppt es              |
| DRAGON_EGG       | nether_end      | end_items     | 0.0         | End-Drop                        |
| DIAMOND_PICKAXE  | tools           | pickaxes      | 0.0         | Werkzeug                       |
| ENDER_PEARL      | misc            | utility       | 0.6         | AFK-fähige Enderman-Farm (siehe `RESEARCH_SOURCES.md` Abschnitt 6b) |

---

### **Schritt 5: Vollständige Dokumentation in `ITEM_MAPPING.md`**
**Pflicht:** Erstelle eine **`ITEM_MAPPING.md`** mit der vollständigen Zuordnung.

**Format:**
```markdown
# Item-Mapping für GUIShop
**Minecraft-Version:** 26.3

---

## 📌 Kategorien & Subgruppen

### blocks.yml
| Material       | Anzeigename     | Subgruppe | Farmbarkeit | Buy  | Sell | Notizen          |
|----------------|-----------------|-----------|-------------|------|------|------------------|
| COBBLESTONE    | Kopfstein       | stones    | 0.9         | 2.0  | 0.4  | Extrem farmbar   |
| STONE          | Stein           | stones    | 0.8         | 4.0  | 0.8  | Farmbar          |
| OAK_LOG        | Eichenholz      | wood      | 0.7         | 8.0  | 1.0  | Holzblock        |

### minerals.yml
| Material       | Anzeigename     | Subgruppe | Farmbarkeit | Buy   | Sell | Notizen     |
|----------------|-----------------|-----------|-------------|-------|------|--------------|
| IRON_INGOT     | Eisenbarren     | ingots    | 0.8         | 30.0  | 5.0  | Farmbar      |
| DIAMOND        | Diamant         | gems      | 0.2         | 300.0 | 75.0 | Selten       |

### [Weitere Kategorien...]

---

## 📝 Änderungen gegenüber Vorversion
- **Hinzugefügt:** [Neue Items der Zielversion, mit Quellenangabe statt Vermutung, z. B. "TRIAL_KEY, HEAVY_CORE (neu in 1.21 'Tricky Trials')"]
- **Entfernt:** - 
- **Anpassungen:** Farmbarkeit von IRON_INGOT von 0.7 auf 0.8 erhöht (neue Iron Farm-Methoden).
```

**Hinweis:** Autor und Datum der Änderung werden **nicht** im Dokument selbst geführt, sondern über die Git-Commit-Historie abgedeckt (siehe `ec84c1f`).

---

## 🔄 Validierung
- [ ] Alle Vanilla-Items abgedeckt.
- [ ] Keine Duplikate in den Zuordnungen.
- [ ] Jedes Item hat eine **klare Kategorie/Subgruppe**.
- [ ] Farmbarkeit-Werte sind **realistisch**. 
- [ ] Alle neuen Items der Zielversion enthalten.

---
**Hinweis:** Diese Datei ist die **einzige Quelle der Wahrheit** für die Item-Zuordnung. Jede Änderung muss hier dokumentiert werden.

---

## 📌 **Wiederholung bei Minecraft-Updates**

1. **Neue Version identifizieren** (gemäß aktuellem Schema, z. B. `26.4` — siehe Hinweis in Schritt 1).
2. **Neue Items/Blöcke** aus den offiziellen Quellen extrahieren.
3. **Farmbarkeit einschätzen** (Community-Diskussionen, Wiki-Recherche).
4. **Items den bestehenden Kategorien/Subgruppen zuweisen** (oder neue Subgruppen erstellen).
5. **`ITEM_MAPPING.md` aktualisieren** und Änderungen dokumentieren.
6. **Validierung durchführen** (siehe Checkliste oben).
