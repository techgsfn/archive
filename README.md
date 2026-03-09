```id="n3j0m0"
README.md
```

in the **root of the archive repository**.

This document explains **how to add new publications and maintain the system**, so the archive remains easy to manage even years later.

---

# Astitva Digital Archive

### Publication Management Guide

This repository hosts the **Astitva Digital Archive**, the publication platform of the **Global Synergetic Foundation (GSFN)**.

The archive provides:

* publication landing pages
* downloadable research PDFs
* structured metadata for scholarly indexing
* Rig Veda verse references
* concept indexing
* citation formats

The system operates entirely as a **static scholarly publishing infrastructure**.

---

# Repository Structure

```text id="x34x1u"
astitva.gsfn.in/

index.html
registry.html
rigveda-index.html
rigveda-navigation.html
concepts.html
knowledge-graph.html

catalog.json
citations.json
verse-index.json
concept-index.json
knowledge-graph.json

publications/
    publication-page.html

pdf/
    publication-file.pdf

assets/
    css/style.css
    js/
        catalog.js
        verse-index.js
        concept-index.js
        rigveda-nav.js
        knowledge-graph.js
        citations.js
```

---

# Adding a New Publication

To add a new publication, complete the following steps.

---

# Step 1 — Upload the PDF

Place the file in:

```id="ocbeid"
pdf/
```

Example:

```text id="ht3jpj"
pdf/vedic-agni.pdf
```

---

# Step 2 — Create a Publication Page

Create a landing page in:

```id="0yq86o"
publications/
```

Example:

```text id="mhw72u"
publications/vedic-agni.html
```

The page should contain:

* title
* author
* metadata
* abstract
* download link
* citation section
* full text or summary

---

# Step 3 — Update `catalog.json`

Add a record for the new publication.

Example:

```json id="mq7gdl"
{
  "id": "vedic-agni",
  "title": "Vedic Agni: The Cosmic Energy",
  "author": "Sati Shankar",
  "year": 2026,
  "series": "Astitva Research Series",
  "doi": "10.xxxx/astitva.xxxx",
  "pdf": "pdf/vedic-agni.pdf",
  "url": "publications/vedic-agni.html"
}
```

This file powers the **automatic publication index**.

---

# Step 4 — Update `citations.json`

Add citation metadata.

Example:

```json id="x2hdxq"
"vedic-agni": {
  "title": "Vedic Agni: The Cosmic Energy",
  "author": "Sati Shankar",
  "year": "2026",
  "series": "Astitva Research Series",
  "publisher": "Global Synergetic Foundation",
  "url": "https://astitva.gsfn.in/publications/vedic-agni.html"
}
```

This file generates:

* Chicago citation
* APA citation
* BibTeX
* RIS

automatically on publication pages.

---

# Step 5 — Update `verse-index.json` (If Vedic Verses Are Discussed)

Example:

```json id="yj7zxy"
"RV 1.1.1": [
  {
    "title": "Vedic Agni: The Cosmic Energy",
    "url": "publications/vedic-agni.html"
  }
]
```

This allows readers to find **all publications discussing a specific Rig Veda verse**.

---

# Step 6 — Update `concept-index.json` (If Concepts Are Discussed)

Example:

```json id="xho0kw"
"Agni": {
  "verses": [
    "RV 1.1.1",
    "RV 3.1.1"
  ],
  "publications": [
    {
      "title": "Vedic Agni: The Cosmic Energy",
      "url": "publications/vedic-agni.html"
    }
  ]
}
```

This supports navigation by **philosophical concept**.

---

# Step 7 — Update `knowledge-graph.json` (Optional but Recommended)

Add relationships between:

```text id="c8lj0d"
Concept
Verse
Publication
```

Example:

```json id="r07rdz"
{
  "source": "Agni",
  "target": "RV 1.1.1"
}
```

---

# Archive Navigation Systems

The archive provides several navigation layers.

| System              | Purpose                     |
| ------------------- | --------------------------- |
| Publication Index   | list of publications        |
| Verse Index         | Rig Veda verse references   |
| Rig Veda Navigation | Mandala → Sukta → Verse     |
| Concept Index       | philosophical themes        |
| Knowledge Graph     | relationships between ideas |

Together these form a **multi-layer research navigation system**.

---

# Manuscript Workflow

Publications are prepared using a separate **manuscript repository**.

Workflow:

```text id="g7r8n0"
Manuscript writing
      ↓
Markdown
      ↓
Pandoc export
      ↓
HTML + PDF
      ↓
Archive publication page
```

This ensures **clean scholarly formatting**.

---

# CSS Architecture

Three CSS environments are used.

| Layer           | Purpose               |
| --------------- | --------------------- |
| Manuscript CSS  | writing environment   |
| Archive CSS     | publication pages     |
| Institution CSS | institutional website |

Archive and institution share the same stylesheet for visual consistency.

---

# Metadata and Indexing

Each publication includes:

* Google Scholar metadata
* Schema.org structured data
* citation registry

This enables indexing by:

```text id="6ydchq"
Google Scholar
Semantic Scholar
OpenAlex
Library discovery systems
```

---

# Long-Term Vision

The archive is designed as a **Rig Veda research platform** linking:

```text id="4xwh1m"
Verses
Concepts
Publications
Scholarly interpretations
```

Over time it will function as a **structured digital commentary corpus**.

---

# Maintenance Summary

Whenever a new publication is added:

```text id="s63rdr"
Upload PDF
Create publication page
Update catalog.json
Update citations.json
Update verse-index.json (if needed)
Update concept-index.json (if needed)
Update knowledge-graph.json (optional)
```

---

# License

Publications are released under the licensing terms specified by the Global Synergetic Foundation.



