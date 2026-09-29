# Game-Design-Regeln & Ökonomische Balance

**Zweck:** Diese Regeln definieren die ökonomische Balance für das GUIShop-Config-Paket. Sie müssen **jederzeit** für neue Minecraft-Versionen oder Preis-Updates angewendet werden.

---

## 📜 **Grundregeln (Immer einhalten!)**

### 1. Buy/Sell-Ratio
- **Standard:** `Buy:Sell` **muss zwischen 3:1 und 5:1 liegen**.
- **Ziel:** Spieler können durch Verkauf Geld verdienen, aber nicht den gesamten Shop aufkaufen.
- **Formel:** `Ratio = Buy / Sell` → **3 ≤ Ratio ≤ 5**
- **Ausnahme:** Items mit `buy-price: false` oder `sell-price: false` (siehe unten).

### 2. Farmbare Items (Anti-Inflations-System)
- **Extrem farmbar** (Farmbarkeit ≥ 0.7):
  - **Sell-Preis:** `0.1` bis `0.5`
  - **Tägliches Limit (Richtwert, keine Plugin-Funktion):** 1000–5000/Tag, dokumentiert als Hinweistext in `shop-lore` (GUIShop selbst erzwingt kein Limit)
  - **Beispiele:** COBBLESTONE, DIRT, SAND, PUMPKIN, MELON, IRON_INGOT, GUNPOWDER, BONE, BAMBOO
- **Nicht farmbar/Unikat** (Farmbarkeit ≤ 0.2):
  - **Hohe Verkaufspreise**, **sehr hohe Kaufpreise**
  - **Kein tägliches Limit**
  - **Beispiele:** DIAMOND, NETHERITE_INGOT, ANCIENT_DEBRIS, DRAGON_EGG
  - **Kriterium:** Ressource ist an ein endliches Weltvorkommen gebunden (Erzabbau, einmaliger Boss-Drop) — es existiert **keine** wiederholbare In-Game-Mechanik, die die Ressource neu erzeugt.
- **Aufwändig, aber erneuerbar** (Farmbarkeit 0.3–0.4):
  - Ressource ist über eine bekannte, wiederholbare Endgame-Mechanik (Boss-Zyklus, Duplikation, Raid) unbegrenzt oft beschaffbar — der limitierende Faktor ist der Spieleraufwand pro Zyklus, nicht die Weltgenerierung.
  - **Hohe Verkaufspreise**, **hohe bis sehr hohe Kaufpreise** (Aufwand rechtfertigt den Preis, nicht Nicht-Erneuerbarkeit)
  - **Kein tägliches Limit nötig** (der Aufwand pro Einheit limitiert die Menge bereits faktisch)
  - **Beispiele:**
    - `NETHER_STAR` — Wither lässt sich beliebig oft beschwören/töten (Wither-Skelett-Schädel-Farm + Wither-Kill-Setup, ~90+/h in optimierten AFK-Farmen)
    - `SHULKER_SHELL` — Duplikationsmechanik seit 1.17: ein aus einer End City geborgener Shulker reicht als Startpunkt für eine unbegrenzte Farm
    - `TOTEM_OF_UNDYING` — garantierter Evoker-Drop, über Dorf-Raid-Farmen (Bad-Omen-Trigger) beliebig oft wiederholbar
    - `WITHER_SKELETON_SKULL` — Nether-Fortress-Farm, AFK-fähig (5–360+/h je nach Bauqualität)
  - **Nicht zu verwechseln mit "Nicht farmbar/Unikat":** Diese Items sind kein Einzelvorkommen wie DIAMOND, sondern nur durch Spielaufwand (nicht durch Weltgenerierung) begrenzt.

### 3. Handlungs-Restriktionen (`false`-Regel)
| Regel               | Anwendung                                                                 | Beispiele                          |
|---------------------|---------------------------------------------------------------------------|------------------------------------|
| `buy-price: false`  | Item **kann nicht gekauft** werden (muss erspielt werden).               | DRAGON_EGG, HEAVY_CORE, SPAWNER    |
| `sell-price: false` | Item **kann nicht verkauft** werden (Missbrauchsschutz).                 | Alle verzauberten Items, Werkzeuge, Rüstungen |

### 4. Stack-Größen
GUIShop kennt kein separates `buy-stack`/`sell-stack`-Feld. Käufe/Verkäufe laufen einzeln oder über die eingebaute Mengenauswahl im Shop-GUI (Spieler wählt die Menge selbst) — es gibt dafür keine Konfiguration pro Item.

---

## 💰 **Preis-Leitfaden (Richtwerte für Minecraft 1.26.2)**

| **Item-Kategorie**          | **Buy** | **Sell** | **Ratio** | **Farmbarkeit** | **Tägliches Limit** | **Notizen**                     |
|----------------------------|---------|----------|-----------|-----------------|--------------------|----------------------------------|
| Gestein/Erde               | 2.0     | 0.1      | 20.0      | 0.9             | 2000               | → Sell auf **0.4** anpassen (Ratio=5.0) |
| Holzstämme                 | 8.0     | 1.0      | 8.0       | 0.8             | 1500               | ✅ OK                              |
| Eisenbarren                | 30.0    | 5.0      | 6.0       | 0.8             | 1000               | → Buy auf **25.0** reduzieren (Ratio=5.0) |
| Diamant                    | 300.0   | 75.0     | 4.0       | 0.2             | Kein Limit         | ✅ OK                              |
| Netherit-Barren            | 5000.0  | 1250.0   | 4.0       | 0.1             | Kein Limit         | ✅ OK                              |
| Essen/Ernte                | 6.0     | 1.0      | 6.0       | 0.8             | 1000               | → Buy auf **5.0** reduzieren (Ratio=5.0) |
| Mob-Loot                   | 20.0    | 4.0      | 5.0       | 0.7             | 500                | ✅ OK                              |

---

## 📊 **Farmbarkeit-Kategorien & Preis-Spannen**

| **Farmbarkeit** | **Beispiele**                          | **Sell-Preis** | **Buy-Preis** | **Ratio** | **Tägliches Limit (Lore-Hinweis)** |
|-----------------|----------------------------------------|----------------|---------------|-----------|--------------------|
| 0.9–1.0         | COBBLESTONE, DIRT, SAND, GRAVEL        | 0.1–0.5        | 2.0–4.0       | 4:1–5:1   | 1000–5000          |
| 0.7–0.8         | IRON_INGOT, GUNPOWDER, BONE, STRING    | 1.0–5.0        | 10.0–30.0     | 3:1–5:1   | 500–2000           |
| 0.3–0.6         | GOLD_INGOT, EMERALD, BLAZE_ROD, ENDER_PEARL | 5.0–20.0  | 20.0–100.0    | 3:1–5:1   | 100–500            |
| 0.3–0.4 (aufwändig, aber erneuerbar) | NETHER_STAR, SHULKER_SHELL, TOTEM_OF_UNDYING, WITHER_SKELETON_SKULL | 100.0–1250.0 | 450.0–6000.0 | 3:1–5:1 | Kein Limit (Aufwand limitiert bereits) |
| 0.0–0.2         | DIAMOND, NETHERITE_INGOT, ANCIENT_DEBRIS | 75.0–1250.0 | 300.0–6000.0  | 3:1–5:1   | Kein Limit        |
| 0.0             | DRAGON_EGG, SPAWNER, HEAVY_CORE        | 1000.0–25000.0 | false         | -         | Kein Limit        |

---

## ⚠️ **Spezielle Regeln für Item-Typen**

### Werkzeuge & Waffen (`tools.yml`)
- **Sell:** **Immer `sell-price: false`** (kein Verkauf, um Enchant-Missbrauch zu verhindern).
- **Buy:** individuell (z. B. `WOODEN_PICKAXE: 50.0`, `DIAMOND_AXE: 1000.0`).

### Rüstungen (`armor.yml`)
- **Sell:** **Immer `sell-price: false`** (kein Verkauf).
- **Buy:** individuell (z. B. `LEATHER_HELMET: 80.0`, `NETHERITE_CHESTPLATE: 8000.0`).

### Verzauberungsbücher (`enchantments.yml`)
- **Sell:** **Immer `sell-price: false`** (kein Verkauf).
- **Buy:** nach Seltenheit (z. B. `EFFICIENCY_1: 100.0`, `MENDING: 2000.0`).

### Tränke (`potions.yml`)
- **Sell:** **Immer `sell-price: false`** (kein Verkauf, außer Admin-Shop).
- **Buy:** nach Typ (z. B. `POTION_OF_STRENGTH: 50.0`, `SPLASH_POTION_OF_HARMING: 200.0`).

### Mob-Spawner (`spawners.yml`)
- **Buy:** **Immer `buy-price: false`** (kann nicht gekauft werden).
- **Sell:** hoch (z. B. `SPAWNER: 25000.0`, `CREEPER_SPAWNER: 50000.0`).

---

## 🔄 **Anpassungsregeln für neue Minecraft-Versionen**

1. **Neue Items/Blöcke:**
   - **Farmbarkeit einschätzen** (0.0–1.0).
   - **Preise aus Community-Quellen** recherchieren (Median aus ≥3 Quellen).
   - **Ratio 3:1–5:1** sicherstellen.

2. **Geänderte Farmbarkeit:**
   - Falls ein Item **einfacher farmbar** wird (z. B. neues Farm-Design):
     - **Sell-Preis senken** (z. B. von `1.0` auf `0.3`).
     - **Tägliches Limit anpassen** (z. B. von `1000` auf `500`).

3. **Neue Kategorien/Subgruppen:**
   - Falls neue Item-Typen hinzukommen (z. B. neue Blöcke aus einem Update):
     - **In bestehende Kategorie einordnen** (z. B. `TRIAL_KEY` → `nether_end.yml`).
     - **Oder neue Subgruppe erstellen** (z. B. `trial_chamber_items` in `nether_end.yml`).

---

## 🛡️ **Quellenvalidierung & Manipulationsschutz (Anti-Astroturfing)**

Um die Ökonomie vor gezielter Meinungsmache, Spam oder Preisabsprachen in Foren zu schützen, gelten folgende unverletzliche Grundsätze:

1. **Minecraft Wiki als unmanipulierbare Primärbasis (Gewichtung 50%):**
   - Jede Preisentscheidung basiert primär auf den verifizierten Spieldaten des Minecraft Wikis:
     - **Natürliche Seltenheit & Drop-Wahrscheinlichkeit**
     - **Farm-Mechaniken & Erneuerbarkeit** (siehe Farmbarkeits-Kriterien oben)
     - **Ressourcenaufwand im Crafting-Baum**
     - **Gefahrenpotenzial bei der Beschaffung** (z. B. Overworld Oberfläche vs. Netherfestung / Ancient City).
   - **Hinweis:** Die "Progression Tier 1–4"-Einteilung (siehe `RESEARCH_SOURCES.md` Abschnitt 3) ist ein **eigenes Projektschema**, keine offizielle Wiki-Klassifikation — das Wiki selbst kennt nur ein rein kosmetisches Seltenheitssystem (Common/Uncommon/Rare/Epic) ohne Preisbezug.
2. **Ausschluss von Einzelmeinungen:**
   - Beiträge einzelner Nutzer oder kleiner Interessengruppen in Foren werden **nicht** isoliert als Recherchewert gewertet.
   - Nur belastbare, real verifizierte Quellen finden Eingang (siehe `RESEARCH_SOURCES.md` Abschnitt 1 für die aktuelle, geprüfte Quellenliste inkl. Mineseed Official Price Guide).
3. **Ausreißer-Bereinigung:**
   - Weicht ein externer Preisvorschlag um mehr als 50% vom Wiki-basierten Progressionskorridor ab, wird er automatisch als Spekulation/Spam verworfen.
4. **Schutzmauer durch Buy:Sell-Ratio:**
   - Das feste Ratio-Korsett ($3:1$ bis $5:1$) verhindert künstlich aufgeblasene An- oder Verkäufe.

---

## 📝 **Dokumentationspflicht**

Jede Anpassung oder Entscheidung **muss** in einer der folgenden Dateien dokumentiert werden:
- **`RESEARCH_SOURCES.md`:** Quellen für Preis-Recherche inkl. Ausreißer-Dokumentation.
- **`CHANGELOG.md`:** Änderungen an Preisen, Kategorien oder Regeln.
- **`ITEM_MAPPING.md`:** Zuordnung von Items zu Kategorien/Subgruppen.

### ⚠️ Pflicht für jeden Agenten/Bearbeiter: CHANGELOG.md pflegen

**Jede** Änderung an diesem Config-Paket (neue Items, geänderte Preise, neue/geänderte Kategorien, Bugfixes an bestehenden Shop-Dateien, Regeländerungen) **muss** als Eintrag in **[`CHANGELOG.md`](./CHANGELOG.md)** dokumentiert werden — unabhängig davon, ob ein Mensch oder ein KI-Agent die Änderung vornimmt.

- **Format:** [Keep a Changelog](https://keepachangelog.com/de/1.0.0/) (Abschnitte `Added`, `Changed`, `Fixed`, `Removed`).
- **Wann ein neuer Versionsblock nötig ist:** Bei jeder abgeschlossenen, in sich sinnvollen Änderung (z. B. "fehlende Items ergänzt", "Preise für Kategorie X neu kalibriert"). Kleine Zwischenschritte innerhalb einer Session können unter `[Unreleased]` gesammelt werden, bevor sie zu einem Versionsblock zusammengefasst werden.
- **Was rein muss:** Was sich geändert hat (konkrete Items/Dateien nennen), warum (z. B. Vollständigkeits-Check gegen `ITEM_MAPPING.md`, Preis-Update, neue Minecraft-Version), und das Ergebnis in Zahlen wo sinnvoll (z. B. "140/140 Items abgedeckt").
- **Was nicht reicht:** Eine Änderung ohne Changelog-Eintrag gilt als **nicht abgeschlossen**. Vor dem Beenden einer Aufgabe immer prüfen: "Ist mein Changelog-Eintrag geschrieben?"

---

*Letzte Aktualisierung: 2026-09-29*

