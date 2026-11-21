---

"Project 4T8G":
  template/:
    characters_template/:
      - "Characters_Template_Header.md"
      - "Characters_Template_Main.md"
      - "Characters_Template_Source.md"
    "Template_Schema.md": null
    "LICENSE.md": "MIT License"

---

> *Prose, structured. Lore, intact.*

* "4taegeuk8gua":
  - cross: "☯"
  - trinity: "☰"
  - ichthus: "☱"
  - fire: "☲"
  - swastika: "☳"
  - typhoon: "☴"
  - water: "☵"
  - bolt: "☶"
  - hexagram: "☷"

---

## philosophy

* **Preventing Lore Inconsistency at Scale**
  - As creative projects expand over time, unorganized prose inevitably leads to contradictions and broken continuity.
  - **Project `4T8G`** solves this by providing a simple yet strict structural schema that keeps large-scale worldbuilding consistent without sacrificing readability.

* **Separation of Schema and Prose**
  - **System & Mechanics (`*_Source.md`):** Written in pure `YAML` frontmatter, enforcing strict data types, stats, and logic rules.
  - **Interface & Metadata (`*_Header.md`):** Exposes public structural specifications and entity metadata using structured Markdown headers (designed for `Markdoc` validation).
  - **Narrative & Lore (`*_Main.md`):** Written in clean `Markdown`, allowing writers to focus on storytelling with high readability while referencing exact definitions via relative anchor links (`#`).

* **Ecosystem Synergy**
  - **Project `4T8G`:** Provides the foundational tripartite schema (`Source` / `Header` / `Main`).
  - **`Markdoc`:** Validates structural integrity and tag rules within header interfaces.
  - **`Obsidian`:** Connects entities, timelines, and lore through bidirectional relative links and graph visualization.

---

## template-directory-structure

* **`Template_Schema.md` (Root Schema Specification)**
  - Defines the system-wide `UDOC/1` schema specifications, including numeric `limits`, stat `schema`, and validation rules for `payload`, `actions`, and `sequences`.
* **`characters_template/` (Tripartite Entity Pattern: `*_Header`, `*_Main`, `*_Source`)**
  - Every entity inside `characters_template/` is strictly divided into three files to decouple data logic from narrative prose.
  - `Characters_Template_Source.md`: Implements concrete entity stats, actions, and sequences conforming to the schema defined in `Template_Schema.md`.
  - `Characters_Template_Header.md`: Holds character-specific YAML metadata and public `actions` / `sequences` interfaces.
  - `Characters_Template_Main.md`:
    + Organizes character appearances and timelines (`prequel`, `spin-off`, `sequel`) with dialogue references.
    + Contains narrative details (`concept`, `world-building`) linked via relative anchor paths (`#`).

---

## getting-started

* **1. Initialize Your Workspace**
  - Copy the `template/` directory into your project root and rename `characters_template/` (and its files) to match your entity names.
* **2. Author in Schema & Tripartite Structure**
  - **`Template_Schema.md`:** Define or review core system rules, stat schemas, and validation constraints.
  - **`*_Source.md`:** Populate entity stats, `actions`, and `sequences` in `characters_template/` using `YAML`.
  - **`*_Header.md`:** Fill in entity metadata and public section headers (`##`) to establish linkable anchor targets.
  - **`*_Main.md`:** Write lore, dialogue, and timelines in `Markdown`, connecting definitions across files with relative paths (e.g., `./Entity_Header.md#section`).
* **3. Explore & Validate**
  - Open the project folder as an **`Obsidian`** vault to navigate bidirectional links, inspect the graph view, and verify that no links are broken.
  - Run **`Markdoc`** validation against your `*_Header.md` files to enforce structural schema rules as your project scales.
