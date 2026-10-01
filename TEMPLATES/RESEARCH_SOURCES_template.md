# Preis-Recherche für Minecraft [Version]

**Referenzierte Minecraft-Version:** [Hier Version eintragen, z. B. 1.26.2]

---

## 📚 **Hinweise zur Nutzung dieser Vorlage**

1. **Minecraft Wiki als Primäranker (Gewichtung 50%):** Analyse von natürlicher Seltenheit, Vorkommen, Drop-Raten, Crafting-Aufwand und Progressionsstufe (Tier 1–4).
2. **Manipulationsschutz:** Keine ungeprüften Einzelbeiträge aus Foren. Ausreißer (>50% Abweichung vom Progressions-Korridor) werden verworfen.
3. **Median-Berechnung:** Aus gefilterten, stabilen Quellen.
4. **Ratio 3:1–5:1:** Für alle regulär kauf-/verkaufbaren Items zwingend einzuhalten.
5. **Vollständige Dokumentation:** Begründung aller Anpassungen und Ausreißer-Filterungen.

---

## 1. 🔗 Quellen & Validierung

| **Ebene** | **Quelle** | **URL** | **Gewichtung** | **Validierung / Schutz gegen Manipulation** |
|:---|:---|:---|:---:|:---|
| **Ebene 1** | **Minecraft Wiki (Offiziell)** | [https://minecraft.wiki/](https://minecraft.wiki/) | **0.50** | Unmanipulierbar: Spielmechaniken, Seltenheit, Progression T1–T4 |
| **Ebene 2** | **Mineseed Economy Guide** | [https://mineseed.net/economy](https://mineseed.net/economy) | **0.35** | Praxiserprobte Referenzwerte aus Langzeit-Survival-Servern |
| **Ebene 3** | **SpigotMC Aggregierte Statistiken** | [https://spigotmc.org/forums/economy](https://www.spigotmc.org/forums/economy.53/) | **0.15** | Nur aggregierte Erhebungen (keine isolierten Einzelthreads) |

---

## 2. 💰 Preis-Entscheidungen

---

### 2.1 ⚖️ Anpassungen für Buy/Sell-Ratio (3:1–5:1)

*Dokumentiere alle Anpassungen, die nötig waren, um die Ratio in den Zielbereich zu bringen.*

| **Item**          | **Median Buy** | **Median Sell** | **Angepasster Buy** | **Angepasster Sell** | **Neue Ratio** | **Begründung**                     |
|-------------------|---------------|-----------------|-------------------|----------------------|---------------|----------------------------------|
| COBBLESTONE       | 2.0           | 0.09            | 2.0               | 0.4                  | 5.0           | Ratio von 22.22 auf 5.0 gesenkt   |
| IRON_INGOT        | 30.0          | 4.0             | 25.0              | 4.0                  | 6.25 → 5.0    | Buy auf 20.0 reduziert          |
| GUNPOWDER         | 20.0          | 3.0             | 20.0              | 4.0                  | 5.0           | Sell auf 4.0 erhöht (Ratio 5.0) |

---

### 2.2 🎯 Manuelle Übersteuerungen

*Dokumentiere alle Preise, die manuell über den Median gesetzt wurden.*

| **Item**            | **Grundregel Buy** | **Grundregel Sell** | **Manuell Buy** | **Manuell Sell** | **Begründung**                     |
|---------------------|-------------------|----------------------|-----------------|------------------|---------------------------------|
| NETHERITE_INGOT     | 5000.0            | 1250.0               | 6000.0          | 1500.0           | Höhere Seltenheit auf unserem Server |
| ENDER_PEARL         | 50.0              | 10.0                 | 60.0            | 12.0             | Höhere Nachfrage                |
| DIAMOND             | 300.0            | 75.0                 | 350.0           | 80.0             | Inflation-Anpassung            |

---

### 2.3 🌾 Farmbarkeit & Tägliche Limits

*Dokumentiere die Anwendung der Farmbarkeit-Regeln aus `RULES.md`.*

| **Item**          | **Farmbarkeit** | **Sell-Preis** | **Tägliches Limit** | **Begründung**                     |
|-------------------|------------------|----------------|--------------------|----------------------------------|
| COBBLESTONE       | 0.9              | 0.4            | 2000               | Extrem farmbar (Generator)       |
| PUMPKIN           | 0.9              | 0.2            | 500                | Extrem einfache Farm            |
| IRON_INGOT        | 0.8              | 5.0            | 1000               | Iron Farm möglich                |
| GUNPOWDER         | 0.7              | 4.0            | 500                | Creepers farmbar                |
| DIAMOND           | 0.2              | 75.0           | Kein Limit         | Nicht farmbar                   |
| DRAGON_EGG        | 0.0              | 10000.0        | Kein Limit         | Einmalig (Ender Dragon)         |

---

### 2.4 🚨 Spezielle Regeln

*Dokumentiere die Anwendung der `false`-Regeln und Stack-Größen.*

| **Item**            | **Regel**               | **Buy** | **Sell** | **Stack-Größe**       | **Begründung**                     |
|---------------------|-------------------------|---------|----------|------------------------|---------------------------------|
| DIAMOND_PICKAXE     | `sell: false`           | 1000.0  | -1       | -                      | Missbrauchsschutz (Enchants)   |
| SPAWNER             | `buy: false`            | -1      | 25000.0  | -                      | Nicht kaufbar                   |
| COBBLESTONE         | Stack-Größe             | 2.0     | 0.4      | `buy-stack: 64, sell-stack: 64` | Block → Stacks erlaubt         |
| IRON_INGOT          | Stack-Größe             | 25.0    | 5.0      | `buy-stack: 64, sell-stack: 64` | Erz → Stacks erlaubt           |

---

## 3. ❌ Nicht abgedeckte Items

*Dokumentiere Items, für die keine Preise in den Quellen gefunden wurden.*

| **Item**          | **Quelle 1** | **Quelle 2** | **Quelle 3** | **Entscheidung**               | **Begründung**                     |
|-------------------|--------------|--------------|--------------|----------------------------------|---------------------------------|
| MANGROVE_LOG      | -            | -            | 8.0/1.0      | Median: 8.0/1.0 (Ratio: 8.0 → auf 4.0 angepasst) | Nur in Mineseed gefunden |
| ARMADILLO_SCUTE   | -            | 5.0/0.5      | -            | Median: 5.0/0.5 (Ratio: 10.0 → auf 5.0 angepasst) | Nur in SpigotMC gefunden |
| TRIAL_KEY         | -            | -            | -            | Manuell: false/1000.0              | Neu in 1.26.2, keine Referenzen |

---

## 4. 📊 Nicht gefundene Preise

*Dokumentiere Items, für die **gar keine Preise** in den Quellen gefunden wurden.*

| **Item**          | **Grund**          | **Entscheidung**               | **Begründung**                     |
|-------------------|--------------------|----------------------------------|---------------------------------|
| HEAVY_CORE        | Neu in 1.26.2     | buy: false, sell: 5000.0           | Extrem selten                   |
| TRIAL_SPAWNER     | Neu in 1.26.2     | buy: false, sell: 10000.0          | Extrem selten                   |

---

## 5. 🔄 Änderungen gegenüber Vorversion

*Dokumentiere alle Änderungen seit der letzten Preis-Recherche.*

- **Preis-Anpassungen:**
  - `IRON_INGOT`: Buy von 30.0 auf **25.0** reduziert (Ratio-Anpassung).
  - `DIAMOND`: Sell von 70.0 auf **75.0** erhöht (Inflation).
- **Neue Items:**
  - `TRIAL_KEY`, `HEAVY_CORE` (neu in 1.26.2).
- **Entfernte Items:**
  - Keine.

---

## ✅ Validierung

- [ ] Alle Items aus `ITEM_MAPPING.md` haben Preise.
- [ ] Buy/Sell-Ratio liegt für alle Items zwischen **3:1 und 5:1** (außer `false`-Regeln).
- [ ] Farmbarkeit-Werte sind korrekt aus `ITEM_MAPPING.md` übernommen.
- [ ] Tägliche Limits sind für alle **farmbaren Items** (Farmbarkeit ≥ 0.7) gesetzt.
- [ ] `false`-Regeln sind korrekt angewendet (z. B. `sell: false` für Enchanted Items).
- [ ] Stack-Größen sind **nur für Blöcke/Erze** gesetzt.
- [ ] Alle manuellen Anpassungen sind dokumentiert.

---

