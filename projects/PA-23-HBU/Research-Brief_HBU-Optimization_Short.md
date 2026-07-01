---
title: "Computing Highest and Best Use"
lang: en
toc: true
toc-depth: 2
format:
  html:
    css: ../../styles.css
---

```{=html}
<div class="cp-header">
  <div class="cp-tag">Research Brief · Urban Planning, Land Economics &amp; Computational Decision Support · 2021</div>
  <h1 class="cp-title">Computing Highest and Best Use</h1>
  <div class="cp-subtitle">An Integer-Programming Approach to Business-Park Product Mix</div>
  <div class="cp-meta">
    <span class="cp-author">Shuai Ma</span>
  </div>
</div>
```

## Abstract

Highest and Best Use (HBU) is a foundational idea in land economics, yet in practice it is usually determined through expert judgment rather than explicit optimization. This study reframes a business-park product-mix decision as a constrained optimization problem and shows that the concept can be made explicit enough to solve: an integer linear program recovers an economically sensible optimum in seconds, using open-source tools, and makes visible the trade-off between value maximization and market absorption that professional intuition tends to obscure.

## What the study does

The analysis translates a real product-positioning problem, for an industrial and R&D parcel of roughly 39,000 square meters in Nanhai District, Foshan, into an integer linear program (ILP). The four classical HBU tests supply the structure: legal permissibility and physical possibility enter as constraints, while the maximally productive use is approximated by maximizing Gross Development Value (GDV). Drawing on a survey of eleven competing campuses, the model chooses integer quantities of sixteen design-ready building products across three typologies, multi-floor manufacturing, detached warehouses, and independent offices, subject to the binding floor area ratio (FAR) and plot-coverage limits of the site. Because the decision variables are whole buildings, integer rather than continuous programming is the appropriate tool.

## Methods and tools

The model was built in Python and solved as a pure integer linear program with PuLP and the open-source COIN-OR CBC branch-and-bound solver, returning a certified optimum in seconds and enabling rapid scenario analysis across regulatory and market inputs. Supporting work included a field survey of comparable campuses, product catalog definition, and a sensitivity analysis of the value-absorption trade-off. The optimization code is available at [github.com/shuaima-research/HBU](https://github.com/shuaima-research/HBU).

## What it finds

The value-maximizing program combines multi-floor manufacturing buildings with independent offices and contains no detached warehouses, reaching a FAR of 3.4 and plot coverage of 38.9 percent, just inside the regulatory envelope. The result is driven by the price structure: manufacturing space earns a high ground-floor premium, offices sustain a uniform premium across floors, and warehouses sell at a comparatively modest whole-building rate, so warehouses cannot compete on value.

![Composition of the highest-GDV product combination by typology.](figures/fig2_optimal.png)

Yet warehouses, precisely because they are scarce, sell quickly. The study therefore reintroduces them deliberately and measures the cost: the GDV index falls monotonically from 1.00 to 0.91 as warehouses are added, with the penalty steepening beyond two. The final recommendation keeps manufacturing dominant at 80 to 82 percent of floor area, offices at 10 to 18 percent, and a small warehouse component up to about 9 percent to support early sales velocity without materially eroding value.

## Why it matters

The exercise shows that **a concept usually treated as seasoned judgment can be stated precisely enough to compute**, which exposes its assumptions to scrutiny in a way tacit expertise does not. It also reframes zoning: the FAR and coverage limits are not background conditions but the active constraints that shape the optimum, so the model doubles as a tool for examining how regulatory choices translate into built form. Finally, the value-versus-absorption tension marks the limit of single-objective optimization, since the program that maximizes headline value alone may be unattractive once liquidity and cash-flow risk are considered. The GDV objective captures revenue but not construction cost, financing, or discounting, so it operationalizes the structure of HBU rather than delivering a full financial-feasibility appraisal.

*This is a condensed brief. The full paper develops the formulation, the complete results, and the planning interpretation in detail.*
