# Difference-in-Differences: Parallel Trends, Staggered Adoption and the Forbidden Comparison

## Objective
I explored how difference-in-differences (DiD) estimates can be misleading when parallel trends fail, treatment timing differs across groups, or standard errors ignore correlated shocks.

## Methodology
- Reproduced Card and Krueger's (1994) minimum-wage DiD estimate using David Card's original data files.
- Applied DiD to a panel with different group trends and ran a pre-trend test to check the parallel trends assumption.
- Used two-way fixed effects (TWFE) on a staggered-adoption panel and broke the estimate into two two-by-two comparisons.
- Compared iid and clustered standard errors in a panel with persistent state-level shocks.
- Asked AI to write a Goodman-Bacon decomposition function, checked its results against my own calculations, and revised my prompt once to handle missing outcomes.

## Key Findings
- **Replication:** I estimated an increase of 2.75 full-time-equivalent employees, close to the published estimate of 2.76.
- **Parallel trends:** DiD produced a statistically significant estimate even though the true treatment effect was zero. The problem came from different trends across groups.
- **Staggered adoption:** TWFE estimated −0.99 when the true mean treatment effect was 6.71. I found that 66.67% of the weight came from a comparison using already-treated units as controls.
- **Standard errors:** I found that iid standard errors were 8.6 times too small when state-level shocks persisted over time.
- **AI decomposition:** After revising my prompt, the Goodman-Bacon decomposition returned a weighted sum of 2.6735 on the panel with missing outcomes.

Overall, I learned that DiD estimates depend on the parallel trends assumption, the choice of comparison groups, and how standard errors are calculated. I also saw why it is important to check AI-generated code against my own results rather than assuming it is correct.
