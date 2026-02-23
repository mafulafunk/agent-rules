# Analyse: steipete's Agent-Tooling Evolution (Feb 2026)

Erkenntnisse aus dem Vergleich von `steipete/agent-rules` (archiviert) und `steipete/agent-scripts` sowie seinen aktuellen Projekten.

## Trajectory

```
Mid 2025: agent-rules (.mdc Sammlung, generisch, community-tauglich)
    ↓
Ende 2025: agent-scripts (persoenliches Toolkit, Skills, Pointer-Pattern)
    ↓
Anfang 2026: Standalone CLI Tools (CodexBar, oracle, wacli, imsg)
```

**Erkenntnis:** Generische Rules veralten schnell. Der Trend geht zu konkreten Tools die etwas *tun*, statt Anweisungen die erklären *wie* man etwas tun soll.

## agent-rules → agent-scripts

Peters letzter Commit in agent-rules: 31.12.2025. README ersetzt durch:
> "AI moves fast. This was old stuff I used mid 2025 when I was still using Cursor."

agent-scripts (Dez 2025 - Feb 2026) brachte:
- **16 Claude Code Skills** (frontend-design, swift-concurrency-expert, swiftui-liquid-glass etc.)
- **Pointer-Pattern**: Ein zentrales AGENTS.MD, alle Repos verweisen nur darauf
- **Utility Scripts**: committer, browser-tools, docs-list, trash
- Aktivitaet stark abnehmend: 59 Commits (Dez) → 11 (Jan) → 2 (Feb)

## Aktuelle Projekte (Stand Feb 2026)

| Projekt | Beschreibung | Stack | Stars | Aktivitaet |
|---------|-------------|-------|-------|------------|
| **CodexBar** | macOS Menubar: AI-Tool Limits (Claude, Codex, Cursor, 15+ Provider) | Swift, SPM | 6.306 | Sehr aktiv (heute) |
| **oracle** | CLI: Prompts an beliebige LLMs senden, Browser-Automatisierung, MCP-Server | TypeScript, Node.js | 1.514 | Aktiv |
| **wacli** | WhatsApp CLI: Sync, Suche, Senden via whatsmeow | Go, SQLite | 521 | Aktiv |
| **imsg** | iMessage CLI: AI-Agents koennen iMessage/SMS nutzen | Swift, SPM | 747 | Aktiv |
| **macos-automator-mcp** | MCP-Server: AppleScript/JXA via AI ausfuehren, 200+ Rezepte | TypeScript, MCP | 674 | Wartungsmodus |

### CodexBar
- `brew install --cask steipete/tap/codexbar`
- Zeigt Session- und Wochen-Limits aller AI-Tools in der Menueleiste
- 15+ Provider, konfigurierbarer Refresh, lokaler Kosten-Scan

### oracle
- `npx @steipete/oracle --help`
- "Zweitmeinung" von GPT, Gemini, Claude etc. per CLI
- Browser-Automatisierung (ChatGPT/Gemini fernsteuern ohne API-Key)
- MCP-Server-Modus fuer Integration in Cursor/Claude Code

### macos-automator-mcp
- MCP-Server der AppleScript/JXA ausfuehrt
- 200+ vorgefertigte Automatisierungs-Skripte (System, Browser, Xcode, Netzwerk...)
- Einbindbar in Claude Code MCP-Config

## Relevanz fuer eigenes Setup

### Empfohlen
- **CodexBar** — Zero-Effort Monitoring der AI-Tool-Limits
- **macos-automator-mcp** — Claude Code kann macOS direkt steuern
- **oracle** — Schnelle Zweitmeinung von anderen Models

### Nicht relevant
- **wacli/imsg** — Messaging-Automatisierung, sehr spezifischer Use-Case
- **Pointer-Pattern** (AGENTS.MD) — Projekt-spezifische CLAUDE.md Files sind flexibler
- **"telegraph; min tokens"** Stil — Geschmackssache, erschwert Lesbarkeit

## Lessons Learned

1. **Rules haben ein Verfallsdatum** — Models werden besser, brauchen weniger Handholding
2. **Skills > Rules** — Ausfuehrbare Skills (aktiv aufgerufen) schlagen passive .mdc-Dateien
3. **Tools > Anweisungen** — Ein CLI das etwas tut ist robuster als eine Rule die erklaert wie
4. **Spezialisierung gewinnt** — Statt einem grossen Rules-Repo: viele kleine, fokussierte Tools
5. **Community-Star-Counts** — CodexBar (6.3k), oracle (1.5k), imsg (747) zeigen: konkrete Tools bekommen mehr Traktion als generische Rule-Sammlungen
