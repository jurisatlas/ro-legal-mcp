---
name: ro-legal-mcp-skill
description: Official Romania (RO) legislation, multi-tier court precedent research, and citation verification skill.
version: 2.0.0
author: JurisAtlas
license: MIT
---

# Romania Legal Research & Multi-Tier Case Law Skill (`ro-legal-mcp`)

Use this skill whenever the user asks a legal question, drafts a pleading or contract, or researches case law across any judicial instance in **Romania (RO)**.

## Verification & Research Rules

1. **Citation Verification:** Never fabricate a statutory provision or case citation. Query `search_legislation`, `search_case_law`, `search_tiered_court_decisions`, or `verify_citation` before citing any authority (e.g., `ECLI:RO:ICCJ:2024:001 or Legea nr. 287/2009`).
2. **Multi-Tier Judicial Coverage:**
   - **First Instance (Trial / Municipal / District):** 176 Judecătorii (Local District Courts) & 42 Tribunale (County Courts in first instance)
   - **Second Instance (Cantonal / Regional / Appellate):** 15 Curți de Apel (București, Cluj, Iași, Timișoara, Constanța, Brașov, Craiova, Galați, Ploiești, Pitești, Suceava, Bacău, Oradea, Alba Iulia, Târgu Mureș) & Curtea Militară de Apel
   - **Supreme & Constitutional Instance:** Înalta Curte de Casație și Justiție (ÎCCJ — scj.ro) & Curtea Constituțională a României (CCR)
   - **Primary Tiered Database:** ReJustCSM (rejust.ro — Over 35 Million Judgments from all Judecătorii, Tribunale & Curți de Apel) + ÎCCJ (`https://www.rejust.ro`)
