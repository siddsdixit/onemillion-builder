# OneMillion Builder System

This directory contains the OneMillion agent system. When Claude Code runs in any project, these agents are available via the `tools/agents/` directory.

## How It Works

Type what you want to build. The Orchestrator detects intent and routes to the right agent.

**Examples:**
- `"I want to build a recipe app"` → Full build flow (18 steps)
- `"Add a search feature"` → Feature flow
- `"Fix this error: TypeError..."` → Bugfix flow
- `"Run security audit"` → Guard flow
- `"I have a question about..."` → Ask mode

## Agents Available

| Mode | What It Does |
|------|--------------|
| `orchestrator` | Outer loop — routes between all other agents |
| `idea` | Captures vision, generates PRD |
| `spec` | Transforms PRD into engineering requirements |
| `validate-spec` | Quality gates the spec before design |
| `design` | UX/UI specs, design system, seed data |
| `plan` | Architecture doc + sprint briefs |
| `validate-plan` | Quality gates the architecture |
| `build` | Executes one sprint at a time |
| `review` | Checks built code against spec |
| `test` | Backend tests, E2E, accessibility |
| `guard` | Security audit (OWASP, SAST, secrets) |
| `ship` | Deploy to production with verification |
| `sell` | Marketing strategy, copy, SEO |
| `ask` | Technical advisor — read-only |
| `debug` | Reproduce, diagnose, fix bugs |
| `refactor` | Safe incremental refactoring |
| `revise` | Traces requirement changes across artifacts |

## Skills Available

Skills are reference documents agents read to get consistent, authoritative answers:

- `tech_stack` — locked stack rules (must-read for plan, build agents)
- `checklist_security` — security audit checklist
- `checklist_ship` — deployment guide and verification steps
- `material3` — Material Design 3 component and token reference
- `mermaid` — diagram syntax and generation
- `pdf` — PDF generation with reportlab
- `prd_web_app` / `prd_agent` / `prd_hybrid` — PRD templates by product type
- `testing` — test plan templates and test patterns
- `seo_audit` — SEO audit methodology

## Project State

Every project using this system stores state in `.onemillion/`:

```
your-project/
└── .onemillion/
    ├── state.json          ← Current flow phase and status
    ├── prd.md              ← Product Requirements Document
    ├── refined-prd.md      ← Engineering Requirements
    ├── design-spec.md      ← Design specification
    ├── architecture.md     ← System architecture
    ├── sprints/            ← Sprint briefs (S0, S1, S2...)
    ├── assets/             ← PDFs, reports
    └── todo.md             ← Living progress tracker
```

## Installation

```bash
# Copy agents to Claude's global config
cp -r tools/agents/* ~/.claude/agents/
cp -r tools/skills/* ~/.claude/skills/

# Or use symlinks to get updates automatically
ln -s $(pwd)/tools/agents/* ~/.claude/agents/
ln -s $(pwd)/tools/skills/* ~/.claude/skills/
```

## Getting Started

Follow the [18-day course](./course/README.md) or jump straight in:

```bash
mkdir my-product && cd my-product
claude
# Then type: "I want to build [your idea]"
```
