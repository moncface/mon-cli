# CLAUDE.md — Mon CLI

## Project Overview

Mon CLI is the CLI version of mon-tab. npm package name: `mon-tab`

## .lndf Commands

### Project-local (single project distillation)

```
mon ld  — Distill project state from git + package.json (no LLM required)
mon lv  — Display current distillation
mon lc  — Distill + copy to clipboard
```

File structure:
```
{project-root}/.lndf/
  ├── current.lndf
  └── history/YYYY-MM-DDTHHMMSS.lndf
```

### Cross-project (aggregation)

```
mon lp create <name>     — Create project in ~/.mon/projects/
mon lp add <name> <path> — Add source to project
mon lp view <name>       — List sources in project
mon lp dump <name>       — Concatenate all sources to stdout
mon lp list              — List all projects
```

File structure:
```
~/.mon/
  ├── source/      ← individual distillations / notes
  └── projects/    ← project files (source path lists)
```

### SKILL.md

Bundled in npm package at skills/lndf/SKILL.md.
Teaches AI tools how to interpret .lndf files.

## Technical Constraints

- Node.js runtime
- Minimal external dependencies
- No LLM API calls (ld/lv/lc/lp are all local operations)
- lp.js is a single file with subcommand branching
- ~/.mon/ is auto-created if absent
- Project files are plain Markdown
- Source paths stored as absolute paths
