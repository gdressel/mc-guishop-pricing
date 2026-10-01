# Kernprozess B: Preise finden & festlegen

**Zweck:** Für jedes Item **realistische Buy/Sell-Preise** ermitteln, die den **Game-Design-Regeln** (siehe `RULES.md`) entsprechen.
**Wiederholbar:** Dieser Prozess muss **jederzeit** (z. B. jährlich oder bei neuen Community-Trends) durchlaufen werden können.

---

## 📋 **Schritt-für-Schritt-Anleitung**

---

### **Schritt 1: Quellenarchitektur & Manipulationsschutz**

Um **Einflussnahme durch Meinungsmache, gezielte Forenbeiträge ("Astroturfing") oder Spammer auszuschließen**, ist die Recherche hierarchisch aufgebaut. Das Fundament bilden die objektiv gepflegten Daten des offiziellen Minecraft Wikis.

#### **Quellen-Hierarchie & Gewichtung:**

| **Ebene** | **Quelle** | **Typ / URL** | **Gewichtung** | **Aufgabe & Manipulationsschutz** |
|:---|:---|:---|:---:|:---|
| **Ebene 1: Objektives Fundament** | **Minecraft Wiki (Offiziell)** | [minecraft.wiki](https://minecraft.wiki/) | **0.50** | **Unmanipulierbare Basis:** Bestimmt Seltenheit, Drop-Chancen, Spawn-Raten, Vorkommen, Crafting-Tiefe und die benötigte Progressionsstufe des Spielers. |
| **Ebene 2: Server-Preis-Floor** | **Mineseed — Official Price Guide** | [docs.mineseed.org/mineseed/the-official-price-guide](https://docs.mineseed.org/mineseed/the-official-price-guide) | **0.35** | **Realitäts-Anker:** Mindestpreis-*Floor*-System eines Survival-Servers, nur als unterer Anker, kein Buy/Sell-Ratio-Vorbild. |
| **Ebene 3: Community-Preisdatenbank** | **verzion's Economy Price Guide** | [minecraft-economy-price-guide.net](https://minecraft-economy-price-guide.net/) | **0.15** | **Nur grobe Plausibilitätsprüfung:** Community-gepflegte Datenbank, keine belastbare Einzelwert-Quelle. |

---

#### **Schutzregeln gegen Manipulation & Spamming:**

1. **Ausschluss von Einzelstimmen (Anti-Spam):**
   - Einzelne Forenbeiträge, isolierte Meinungen oder Diskussionsthreads einzelner Interessengruppen werden **niemals** direkt als Preisgrundlage übernommen.
   - Quellen aus Foren werden nur gewertet, wenn sie einen verifizierten Querschnitt aus vielen Servern abbilden.
2. **Ausreißer-Filter (Statistical Trimming):**
   - Weicht ein externer Preisvorschlag um mehr als **50% vom Median der Ebenen 1 und 2** ab, wird dieser Wert als spekulative Verzerrung/Spam automatisch gestrichen.
3. **Objektives Progressions-Korsett (Wiki-Schutzanker):**
   - Jedes Item wird anhand der Daten des Minecraft Wikis einer **Progressionsstufe (Spielerniveau)** und einem **Seltenheitsindex** zugeordnet (siehe Schritt 1.1).
   - Kein externer Preis kann den für die jeweilige Stufe definierten Preiskorridor nach oben oder unten durchbrechen.

---

### **Schritt 1.1: Progressions- & Spielerniveau-Matrix (Minecraft Wiki Analyse)**

Bevor externe Preise geprüft werden, bestimmt das **Minecraft Wiki** den Basis-Korridor anhand von:
- **Spieler-Niveau (Progression):** Wann und wie kann ein Spieler das Item überhaupt erreichen?
- **Aufwand / Werkzeuge:** Werden Spezialwerkzeuge (z. B. Silk Touch, Netherit-Ausrüstung, Tränke) benötigt?
- **Fundort / Restriktionen:** Ist das Item biom-spezifisch, struktur-spezifisch oder dimensions-gebunden?

| **Stufe** | **Spielerniveau / Anforderung** | **Typische Items** | **Intrinsischer Buy-Bereich** | **Intrinsischer Sell-Bereich** |
|:---|:---|:---|:---:|:---:|
| **Tier 1 (Early Game)** | Startphase, Erdoberfläche, Grundwerkzeuge (Holz/Stein), ohne Gefahr | Cobblestone, Eichenholz, Weizen, Wolle, Erde, Sand | `1.0` – `8.0` | `0.2` – `1.6` |
| **Tier 2 (Mid Game)** | Bergbau, Höhlen, Werkzeuge Stufe Eisen/Diamant, Dorfbewohner-Handel | Eisen, Gold, Lapis, Diamanten, Schleim, Redstone | `10.0` – `350.0` | `2.0` – `75.0` |
| **Tier 3 (Late Game)** | Nether-Festungen, Bastionen, Braustand, gefährliche Monsterfarmen | Lohenruten, Netherit, Ghast-Tränen, Wither-Schädel, Tränke | `40.0` – `6000.0` | `8.0` – `1250.0` |
| **Tier 4 (End Game)** | Drachenkampf, End-Inseln, Ominous Trial Chambers, Unikate | Elytren, Drachenei, Schwerer Kern, Shulker-Schalen, Totems | `400.0` – `15000.0` (oder `buy: false`) | `80.0` – `5000.0` |

---

### **Schritt 3: Median berechnen**
**Regel:** Berechne den **Median** (nicht Durchschnitt!) aus den gesammelten Buy- und Sell-Preisen.

**Beispiel (COBBLESTONE Buy-Preis):**
- Sortierte Buy-Preise: **1.8, 2.0, 2.2, 2.5**
- Median = **Mittelwert der beiden mittleren Werte** = `(2.0 + 2.2) / 2 = 2.1`

**Beispiel (COBBLESTONE Sell-Preis):**
- Sortierte Sell-Preise: **0.05, 0.08, 0.1, 0.12**
- Median = `(0.08 + 0.1) / 2 = 0.09`

**Ergebnis:**
- **Median Buy:** 2.1
- **Median Sell:** 0.09
- **Ratio:** 2.1 / 0.09 = **23.33** (❌ **Zu hoch!**)

---

### **Schritt 4: Buy/Sell-Ratio anpassen (3:1–5:1)**
**Regel:** Die Ratio **muss zwischen 3:1 und 5:1 liegen**.
**Formel:** `Ratio = Buy / Sell`

**Anpassungsstrategien:**
1. **Ratio zu hoch (z. B. 23.33):**
   - **Sell-Preis erhöhen** (z. B. von `0.09` auf `0.4` → Ratio = 2.1 / 0.4 = **5.25** → **auf 0.42 anpassen** → Ratio = **5.0**).
   - **Buy-Preis senken** (z. B. von `2.1` auf `1.68` → Ratio = 1.68 / 0.09 = **18.67** → **weiter anpassen**).
   - **Empfehlung:** **Sell-Preis erhöhen**, da farmbare Items ohnehin niedrige Sell-Preise haben sollen.

2. **Ratio zu niedrig (z. B. 2.5):**
   - **Buy-Preis erhöhen** oder **Sell-Preis senken**.

**Beispiel (COBBLESTONE – Final):**
- **Median Buy:** 2.0
- **Median Sell:** 0.4
- **Ratio:** 5.0 (✅ **Im Zielbereich!**)

---

### **Schritt 5: Farmbarkeit & Seltenheit anwenden**
Nutze die **Farmbarkeit-Werte** aus `ITEM_MAPPING.md` und passe die Preise an die **Regeln aus `RULES.md`** an.

**Regeln aus `RULES.md`:**

| **Farmbarkeit** | **Sell-Preis** | **Buy-Preis** | **Ratio** | **Tägliches Limit** | **Beispiel**          |
|-----------------|----------------|---------------|-----------|--------------------|------------------------|
| 0.9–1.0         | 0.1–0.5        | 2.0–4.0       | 4:1–5:1   | 1000–5000          | COBBLESTONE           |
| 0.7–0.8         | 1.0–5.0        | 10.0–30.0     | 3:1–5:1   | 500–2000           | IRON_INGOT            |
| 0.3–0.6         | 5.0–20.0       | 20.0–100.0    | 3:1–5:1   | 100–500            | GOLD_INGOT            |
| 0.0–0.2         | 50.0–200.0     | 300.0–1000.0  | 3:1–5:1   | Kein Limit        | DIAMOND                |
| 0.0             | 1000.0–25000.0 | false         | -         | Kein Limit        | DRAGON_EGG            |

**Anwendung:**
1. Prüfe die **Farmbarkeit** des Items aus `ITEM_MAPPING.md`.
2. Passe **Buy- und Sell-Preis** so an, dass:
   - Sie in der **preislichen Spanne** für die Farmbarkeit liegen.
   - Die **Ratio 3:1–5:1** eingehalten wird.

**Beispiel (IRON_INGOT):**
- Farmbarkeit: **0.8** → Sell-Preis sollte **1.0–5.0** sein.
- Median Sell: **4.0** (✅ im Bereich)
- Median Buy: **30.0**
- Ratio: 30.0 / 4.0 = **7.5** (❌ **Zu hoch!**)
- **Lösung:** Buy auf **20.0** senken → Ratio = 5.0 (✅).

---

### **Schritt 6: Spezielle Regeln anwenden**

| **Regel**               | **Anwendung**                                                                 | **Beispiel**                     |
|-------------------------|-------------------------------------------------------------------------------|----------------------------------|
| `buy: false`            | Item **kann nicht gekauft** werden (muss erspielt werden).               | DRAGON_EGG, HEAVY_CORE, SPAWNER |
| `sell: false`           | Item **kann nicht verkauft** werden (Missbrauchsschutz).                 | DIAMOND_PICKAXE, NETHERITE_SWORD |
| **Stack-Größen**        | `buy-stack: 64`, `sell-stack: 64` **nur für Blöcke/Erze**.                     | COBBLESTONE, IRON_INGOT          |
| **Enchanted Items**     | **Immer `sell: false`** (unabhängig von Farmbarkeit).                          | EFFICIENCY_5_BOOK                |

---

### **Schritt 7: Tägliche Limits für farmbare Items festlegen**
**Regel:** Extrem farmbare Items (`Farmbarkeit ≥ 0.7`) erhalten ein **tägliches Verkaufslimit**.

| **Item**         | **Farmbarkeit** | **Tägliches Limit** | **Begründung**               |
|------------------|-----------------|--------------------|----------------------------------|
| COBBLESTONE      | 0.9             | 2000               | Cobblestone Generator            |
| PUMPKIN          | 0.9             | 500                | Extrem einfache Farm            |
| IRON_INGOT       | 0.8             | 1000               | Iron Farm möglich                |
| GUNPOWDER        | 0.7             | 500                | Creepers farmbar                |
| BONE             | 0.7             | 1000               | Skeleton Farm                   |

---

### **Schritt 8: Dokumentation in `RESEARCH_SOURCES.md`**
**Pflicht:** Erstelle oder aktualisiere **`RESEARCH_SOURCES.md`** mit allen Quellen und Entscheidungen.

**Format:**
```markdown
# Preis-Recherche für Minecraft 26.3

**Hinweis zum Versionsschema:** Seit 2026 verwendet Minecraft Java Edition kein `1.x.x`-Schema mehr; die letzte `1.x`-Version war `1.21`. Aktuelle Versionen folgen dem Jahres-Schema `JJ.N` (z. B. `26.1`, `26.2`, `26.3`).

---

## 1. Quellen
| Quelle                          | URL                                                                 | Gewichtung | Notizen                     |
|---------------------------------|---------------------------------------------------------------------|------------|-----------------------------|
| Minecraft Wiki (Offiziell)      | [minecraft.wiki](https://minecraft.wiki/)                          | 0.50       | Seltenheit, Progression T1–T4 |
| Mineseed — Official Price Guide | [Link](https://docs.mineseed.org/mineseed/the-official-price-guide) | 0.35       | Mindestpreis-Floor, nur Anker |
| verzion's Economy Price Guide   | [Link](https://minecraft-economy-price-guide.net/)                 | 0.15       | Grobe Plausibilitätsprüfung |

---

## 2. Preis-Entscheidungen

### 2.1 Anpassungen für Ratio 3:1–5:1
| Item          | Median Buy | Median Sell | Neue Sell | Neue Ratio | Begründung                     |
|---------------|------------|-------------|-----------|------------|----------------------------------|
| COBBLESTONE   | 2.0        | 0.09        | 0.4       | 5.0        | Ratio von 23.33 auf 5.0 gesenkt   |
| IRON_INGOT    | 30.0       | 4.0         | 4.0       | 7.5 → 5.0  | Buy auf 20.0 reduziert          |
| DIAMOND       | 300.0      | 75.0        | 75.0      | 4.0        | ✅ Keine Anpassung nötig       |

### 2.2 Manuelle Übersteuerungen
| Item               | Grundregel Buy | Grundregel Sell | Manuell Buy | Manuell Sell | Begründung                     |
|--------------------|----------------|-----------------|-------------|--------------|---------------------------------|
| NETHERITE_INGOT    | 5000.0         | 1250.0          | 6000.0      | 1500.0       | Höhere Seltenheit auf unserem Server |
| ENDER_PEARL        | 50.0           | 10.0            | 60.0        | 12.0         | Höhere Nachfrage                |

### 2.3 Farmbarkeit & Limits
| Item          | Farmbarkeit | Sell-Preis | Tägliches Limit | Begründung                     |
|---------------|--------------|------------|------------------|----------------------------------|
| PUMPKIN       | 0.9          | 0.2        | 500              | Extrem einfach farmbar          |
| IRON_INGOT    | 0.8          | 5.0        | 1000             | Iron Farm möglich                |
| COBBLESTONE   | 0.9          | 0.4        | 2000             | Cobblestone Generator            |

### 2.4 Nicht abgedeckte Items
| Item          | Grund          | Vorgehen                     |
|---------------|----------------|------------------------------|
| TRIAL_KEY     | Neu in 1.21 "Tricky Trials" | Preis manuell auf 1000.0/200.0 gesetzt |
| HEAVY_CORE    | Neu in 1.21 "Tricky Trials" | buy: false, sell: 5000.0     |

---

## 3. Nicht gefundene Preise
| Item          | Quelle 1 | Quelle 2 | Quelle 3 | Entscheidung               |
|---------------|----------|----------|----------|-----------------------------|
| MANGROVE_LOG  | -        | -        | 8.0/1.0  | Median aus Mineseed Price Guide (8.0/1.0) |
| ARMADILLO_SCUTE | -      | 5.0/0.5  | -        | Median aus verzion's Price Guide (5.0/0.5) |
```

---

## 🔄 **Wiederholung des Prozesses**

### **Wann muss der Prozess wiederholt werden?**
| **Auslöser**               | **Aktion**                                                                 |
|---------------------------|-----------------------------------------------------------------------------|
| **Neue Minecraft-Version** | Preise für neue Items recherchieren + bestehede Preise anpassen.          |
| **Jährlicher Check**       | Alle Preise neu recherchieren (Inflation anpassen).                      |
| **Community-Trends**       | Preise für Items mit neuer Farm-Methode anpassen (z. B. neues Iron Farm). |
| **Server-spezifische Änd.**| Preise an eigene Regeln anpassen (z. B. höhere Seltenheit für Diamanten).  |

### **Schritt-für-Schritt für Wiederholung:**
1. **Quellen aktualisieren** (neue Threads/Guides suchen).
2. **Preise für alle Items neu sammeln** (oder nur für geänderte Items).
3. **Median neu berechnen** und Ratio prüfen.
4. **Farmbarkeit & Spezialregeln anwenden** (ggf. anpassen).
5. **`RESEARCH_SOURCES.md` aktualisieren** mit neuen Daten.
6. **Shops neu generieren** (manuell oder per Skript).
