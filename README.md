# Romania Legal Research MCP Server (`ro-legal-mcp`)

**[Română](#lang-ro) | [English Documentation](#english-documentation)**

---

<a id="lang-ro"></a>
## Server MCP de Legislație și Jurisprudență (`ro-legal-mcp`) — Română

### Despre acest depozit (Repository)

Acest depozit conține un server Model Context Protocol (MCP) care conectează aplicația dvs. AI (Claude Desktop, Cursor, Windsurf, VS Code / Copilot sau Antigravity) la Portalul Legislativ (`legislatie.just.ro`), ReJust (`rejust.ro` — toate cele 176 judecătorii, 42 tribunale și 15 curți de apel) și Înalta Curte de Casație și Justiție (`scj.ro`).

### Instalare rapidă (Selectarea aplicației AI)

1. **Descărcare:** Faceți clic pe **`<> Code` -> `Download ZIP`** și dezarhivați dosarul.
2. **Lansare:** Faceți dublu clic pe **`Click_Here_To_Install_Windows.bat`** (Windows) sau **`Click_Here_To_Install_Mac.command`** (macOS).
3. **Alegerea clientului AI:** Bifați aplicațiile AI pe care le folosiți, apăsați pe instalare și reporniți aplicația AI selectată.

**Notă de securitate:** Utilitarul funcționează exclusiv în modul citire (read-only) și nu accesează fișierele dvs. personale.

### Gradele de jurisdicție și sursele oficiale

| Grad de jurisdicție | Instanțe acoperite |
|:---|:---|
| **Fond (Judecătorii și Tribunale)** | 176 Judecătorii (Local District Courts) & 42 Tribunale (County Courts in first instance) |
| **Apel (15 Curți de Apel)** | 15 Curți de Apel (București, Cluj, Iași, Timișoara, Constanța, Brașov, Craiova, Galați, Ploiești, Pitești, Suceava, Bacău, Oradea, Alba Iulia, Târgu Mureș) & Curtea Militară de Apel |
| **ÎCCJ și Curtea Constituțională** | Înalta Curte de Casație și Justiție (ÎCCJ — scj.ro) & Curtea Constituțională a României (CCR) |

- **Portalul Legislativ (legislatie.just.ro):** [https://legislatie.just.ro](https://legislatie.just.ro) (`legislatie.just.ro`, `cdep.ro`)
- **ReJustCSM (rejust.ro — Over 35 Million Judgments from all Judecătorii, Tribunale & Curți de Apel) + ÎCCJ:** [https://www.rejust.ro](https://www.rejust.ro) (`rejust.ro`, `scj.ro`, `ccr.ro`, `portal.just.ro`)

---

<a id="english-documentation"></a>
## English Documentation

Model Context Protocol (MCP) server providing live, read-only access to **Romania (RO)** legislation, official gazettes, multi-tier judicial decisions (First Instance, Regional/Cantonal/Appellate, and Supreme/Constitutional courts, including HTML and PDF full-text extraction), and statutory citation verification across all major AI clients (**ChatGPT Desktop, OpenAI Codex CLI, Claude Desktop, Claude Code CLI, Cursor, Windsurf, VS Code / GitHub Copilot / Cline / Roo Code, Google Antigravity / Gemini CLI, Perplexity, and Continue.dev**).

---

### Interactive Desktop Setup (Select Your AI Assistant)

This package includes a graphical installer for legal practitioners and non-technical users that lets you select which AI application(s) you use:

1. **Download:** Click **`<> Code`** at the top right of this repository, select **`Download ZIP`**, and extract the folder to your computer.
2. **Run the Setup Utility:**
   - **Windows:** Double-click `Click_Here_To_Install_Windows.bat`
   - **macOS:** Double-click `Click_Here_To_Install_Mac.command`
3. **Select Your AI Client(s) & Connect:** Check the box(es) for the AI assistant(s) installed on your computer (**ChatGPT Desktop & OpenAI Codex CLI**, **Claude Desktop & Claude Code CLI**, **Cursor**, **Windsurf**, **VS Code / GitHub Copilot / Cline / Roo Code**, **Google Antigravity / Gemini CLI**, or **Perplexity / Continue.dev**), click **Install to Selected AI Clients**, and restart your selected AI application.

**System Integrity Note:** The setup utility operates strictly in read-only mode with respect to your personal files and documents. It installs an isolated Python runtime inside the extracted folder and registers the server entry only in the AI client configuration files you select.

---

### Multi-Tier Judicial Hierarchy & Live Indexed National Archives

This server performs live queries across the full judicial hierarchy and official legal archives of **Romania**, extracting full text from both HTML pages and official court/gazette PDF judgments:

| Judicial Tier | Covered Courts & Tribunals |
|:---|:---|
| **Tier 1 — First Instance** | 176 Judecătorii (Local District Courts) & 42 Tribunale (County Courts in first instance) |
| **Tier 2 — Regional / Cantonal / Appellate** | 15 Curți de Apel (București, Cluj, Iași, Timișoara, Constanța, Brașov, Craiova, Galați, Ploiești, Pitești, Suceava, Bacău, Oradea, Alba Iulia, Târgu Mureș) & Curtea Militară de Apel |
| **Tier 3 — Supreme & Constitutional** | Înalta Curte de Casație și Justiție (ÎCCJ — scj.ro) & Curtea Constituțională a României (CCR) |

#### Official Portals & Live Indexed Domains

- **National Legislation & Official Gazette:** Portalul Legislativ (legislatie.just.ro) — [https://legislatie.just.ro](https://legislatie.just.ro)
  - *Indexed Legislation Domains:* `legislatie.just.ro`, `cdep.ro`
- **Court Decisions & Jurisprudence Archives:** ReJustCSM (rejust.ro — Over 35 Million Judgments from all Judecătorii, Tribunale & Curți de Apel) + ÎCCJ — [https://www.rejust.ro](https://www.rejust.ro)
  - *Indexed Judicial & Open Case Law Domains:* `rejust.ro`, `scj.ro`, `ccr.ro`, `portal.just.ro`

---

### Available MCP Tools

| Tool | Description |
|:---|:---|
| `search_legislation` | Searches enacted statutes, codes, decrees, and official gazette publications in Romania. |
| `search_case_law` | Searches national jurisprudence and open judicial archives for Romania. |
| `search_tiered_court_decisions` | Filters case law specifically by judicial instance (`first_instance`, `appellate_regional`, `supreme_constitutional`) or specific regional/cantonal/district court. |
| `list_court_hierarchy` | Returns the complete 3-tier court structure and supported regional court filters for Romania. |
| `get_legal_document_markdown` | Retrieves full statutory or judicial texts (both HTML and official `.pdf` court judgments) and converts them into clean Markdown. |
| `verify_citation` | Validates statutory and case law citations against official registries. |

---

<details>
<summary><b>Manual Configuration for Developers (Optional)</b></summary>

```json
{
  "mcpServers": {
    "ro-legal-mcp": {
      "command": "uvx",
      "args": [
        "--from",
        "https://github.com/jurisatlas/ro-legal-mcp/archive/refs/heads/main.zip",
        "ro-legal-mcp"
      ]
    }
  }
}
```
</details>
