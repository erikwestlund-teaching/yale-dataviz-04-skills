---
name: viz-house-style
description: House style for ggplot2 figures meant for an audience (a report, slides, or a paper). Use whenever making, polishing, or describing a figure someone else will read.
---

# Figure house style

Follow these rules for any figure meant for an audience. For quick exploratory plots, skip the polish but keep the honesty rules.

## Choose the chart from the question

- Before plotting, state in one sentence the question the figure answers.
- Put the values people must compare on a **common scale** (position on the same axis). Prefer ordered bars or dot plots to pie charts and stacked bars.
- Order categories by value, not alphabetically, unless the order has meaning.
- When groups crowd one panel, use small multiples (`facet_wrap()`) with shared axes.

## Honest scales

- Bar charts start at zero. Dot plots and lines don't have to.
- Use a log scale for values that span orders of magnitude, and say so in the axis label.
- Show the data, not just a summary: add points or a distribution behind means and model lines.

## Text

- The title **states the finding** in plain words. Good: "Infant mortality falls as GDP per capita rises". Bad: "infant_mortality vs gdp".
- Axis labels name the quantity and its units, e.g. "GDP per capita (US$, log scale)".
- Label lines and groups directly on the plot instead of using a legend when there are few of them.
- Add a caption that starts with "Source: ".

## Color

- Use color only to carry meaning. Highlight what matters in one strong color and leave the rest grey.
- Use colorblind-safe palettes (`scale_color_viridis_d()` or Okabe-Ito). Never rely on red versus green alone.

## Theme

- Start from `theme_minimal(base_size = 14)`, remove minor gridlines, and put any legend at the top.

## Description

- Write two or three sentences that describe the pattern without causal language, and name one limitation of the data.

## When done

Save the figure to `outputs/figures/` with `ggsave()` at an explicit size, then list which of these rules you followed and which you couldn't.