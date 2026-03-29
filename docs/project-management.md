# Project Management Schema

This document defines the shared conventions for tracking projects in the Obsidian vault. Both Claude Code CLI (working in the NanoClaw repo) and Andy (the container agent) follow these conventions.

## Vault Structure

```
Projects/
  {project-name}/
    README.md          ← Overview, goals, status
    requirements.md    ← Requirements and constraints
    design.md          ← Architecture and design decisions
    todos.md           ← Active TODOs and backlog
Daily/
  {YYYY-MM-DD}.md      ← Daily notes and captures
Reference/
  {topic}.md           ← Reference material
```

## Frontmatter Conventions

All project notes must include YAML frontmatter:

```yaml
---
project: {project-name}
type: overview | requirements | design | todos
status: active | paused | complete
updated: {YYYY-MM-DD}
tags: [project, {project-name}]
---
```

## Behaviors

- **Search before answering** — run `obsidian_global_search` (Andy) or read the vault files directly (Claude Code) before responding to questions about projects. Check for existing context first.
- **Update todos.md** when the user mentions new tasks, completed work, or changing priorities.
- **Update design.md** when architectural decisions are made.
- **Initialize a new project** by creating all four files (`README.md`, `requirements.md`, `design.md`, `todos.md`) under `Projects/{project-name}/`.
- **Capture to Daily** when something doesn't belong to a specific project yet.

## Vault Location

`/Users/bryanrobbins/andy-home/obsidian-vault-1`

## Andy's Obsidian Tools

| Tool | Use for |
|------|---------|
| `mcp__obsidian-mcp-server__obsidian_global_search` | Find notes by keyword across the vault |
| `mcp__obsidian-mcp-server__obsidian_read_note` | Read a specific note |
| `mcp__obsidian-mcp-server__obsidian_update_note` | Create or update a note (append/overwrite) |
| `mcp__obsidian-mcp-server__obsidian_list_notes` | Browse folder structure |
| `mcp__obsidian-mcp-server__obsidian_manage_frontmatter` | Update metadata without rewriting the file |
| `mcp__obsidian-mcp-server__obsidian_manage_tags` | Add/remove tags |
