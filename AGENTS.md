# Yale Data Viz 04: Skills

This file provides guidance to AI assistants working with this Framework project.
It is the canonical context file; detailed workflow instructions live in the
skills listed below. Edit the sections without regeneration markers freely -
they won't be overwritten.


## Skills

Detailed instructions live in skill files, loaded on demand. Claude Code discovers
them automatically; other agents should read the relevant SKILL.md before working
on a matching task.

| Skill | Covers | Path |
|-------|--------|------|
| `viz-house-style` | House style for ggplot2 figures meant for an audience (a report, slides, or a paper). Use whenever making, polishing, or describing a figure someone else will read. | `.claude/skills/viz-house-style/SKILL.md` |

## Framework Environment <!-- @framework:regenerate -->

This project uses Framework for reproducible data analysis. **Every notebook and script
MUST begin with `scaffold()`** which initializes the environment.

### What scaffold() Does

When you call `scaffold()`, it automatically:

1. **Sets the working directory** to the project root (handles nested notebook execution)
2. **Loads environment variables** from `.env` (database credentials, API keys)
3. **Installs missing packages** listed in settings.yml
4. **Attaches packages** marked with `auto_attach: true` (see Packages section below)
5. **Sources all functions** from `functions/` directory - they are globally available
6. **Sets random seed to 123** for reproducibility

### CRITICAL RULES

**DO NOT** call `library()` for packages listed in the auto-attach section below.
They are already loaded by scaffold(). Calling library() again wastes time and clutters output.

**DO NOT** call `set.seed()` after scaffold(). The seed is already set to 123.
If you need a different seed for a specific operation, document why.

**DO NOT** use `source()` to load functions from the functions/ directory.
They are auto-loaded by scaffold(). Just call them directly.


## Installed Packages <!-- @framework:regenerate -->

**Auto-attached** (loaded by scaffold): dplyr, ggplot2, tidyr, stringr, purrr, tibble, forcats, lubridate
**Installed** (call library() when needed): readr, glue, here, lme4, haven, readxl, scales, janitor, patchwork

Add packages with `package_add("name")` or `package_add("name", auto_attach = TRUE)`.

## Data Management <!-- @framework:regenerate -->

**All data I/O MUST use `data_read()` and `data_save()`** - see the
`framework-data` skill for the full rules. This project's data directories:

| Purpose | Directory |
|---------|-----------|
| Raw data (immutable) | `inputs/raw/` |
| Intermediate/cleaned data | `inputs/intermediate/` |
| Analysis-ready data | `inputs/final/` |
| Output tables | `outputs/tables/` |
| Output figures | `outputs/figures/` |
| Saved models | `outputs/models/` |
| Reports | `outputs/reports/` |


## Workflow Guidelines

Follow the standard Framework workflow (see the `framework-workflow` skill):
import with `data_read()`, clean and save with `data_save()`, analyze from
final datasets, export with `save_table()`, `save_figure()`, or `save_model()`.


## Project Notes

*Add your project-specific notes, conventions, and documentation here.*
*This section is never modified by `ai_regenerate_context()`.*

