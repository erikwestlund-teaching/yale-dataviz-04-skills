# Exercise 4: Teaching Your Assistant Your Style

Part of the workshop **Data Visualization With AI**. Prompts are on the workshop page.

This project has a **skill**, `viz-house-style`: house rules for figures meant for an audience. It's in `.agents/skills/` (read by Posit Assistant and Codex) and `.claude/skills/` (read by Claude Code). In RStudio, use **More → Show Hidden Files** to see them.

## Open the project

- **RStudio:** open the `.Rproj` file.
- **Positron or VS Code:** open this folder.
- **Claude Code or Codex:** start the tool from a terminal in this folder.

You need R with **tidyverse**, **here**, and **rmarkdown**, and Quarto (bundled with RStudio).

## Steps

1. In Exercise 1, which has no skill, give your assistant this prompt and keep the figure:

   ```text
   Complete the task in notebooks/style-task.qmd and render it.
   ```

2. Give the **same prompt** here. Don't mention the skill.
3. Compare the two figures against the rules in `SKILL.md`. Which did it follow? Which did it skip?
4. Change one rule to match your own style and run it again.

A skill makes your style more likely. It doesn't guarantee it.

## About the folders

This project was created from a [Framework](https://framework.pub) blueprint, so it has the layout of a real analysis project: data in `inputs/raw/` (codebooks in `inputs/raw/codebooks/`), your notebooks in `notebooks/`, and results in `outputs/`. `docs/reference/` holds worked reference notebooks from Erik's data visualization course; compare them with what your assistant produces. You don't need the framework R package.
