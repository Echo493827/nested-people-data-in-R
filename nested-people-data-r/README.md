# Nested people data in R: teams, climate, and change over time

Employee survey data is almost never independent. People sit inside teams, and the same people answer survey after survey. This project works through what that means for analysis, in R, using two classic I-O psychology datasets:

1. **Why nesting matters.** How much of a variable lives at the team level (ICC), how ignoring teams shrinks standard errors, how many respondents a team score needs (ICC(2)), and why shrunken team scores beat raw averages for small teams.
2. **Within-team vs. between-team effects.** Centering, contextual effects, random slopes, and a cross-level interaction (does leadership matter more in teams that work longer hours?).
3. **Change over time.** Growth models for repeated survey waves, within-person vs. between-person effects, regression to the mean, missing waves, and when a level has too few groups to model as random.

```
nested-people-data-r/
├── 01_why_nesting_matters.ipynb          ICC(1), design effect, OLS vs. multilevel, ICC(2) by team size, shrinkage
├── 02_team_climate_within_between.ipynb  centering, contextual effects, random slopes, cross-level interaction
├── 03_change_over_time.ipynb             wide/long, growth models, within-person effects, regression to the mean
└── README.md
```

## How to run

**Google Colab (easiest):** go to colab.research.google.com, choose File → Upload notebook, and pick a notebook. It should open with the R runtime. If it opens as Python, choose Runtime → Change runtime type → R. The first code cell installs the `multilevel` package, which takes about a minute.

**Locally:** R 4.x, then `install.packages(c("multilevel", "ggplot2"))`. Run the notebooks in Jupyter with the IRkernel, or paste the code cells into an R script in RStudio.

Every notebook runs top to bottom on its own. The models use `nlme`, which ships with R and loads with `multilevel`.

## How to work through it

- **Predict first** prompts: write a guess before running the next cell.
- **Your turn** cells: replace each `NULL` with your own code. The `check()` line underneath prints `[todo]`, `[ok]`, or `[not yet]`.
- **Your interpretation / Your answers** cells: write in your own words. These are the interview answers.

Plan on 1–2 hours per notebook. Do them in order. Notebook 02 builds on 01, and 03 deliberately contrasts with 01.

## Data

Both datasets ship with Paul Bliese's `multilevel` R package (version 2.7 used here).

- `bh1996`: 7,382 U.S. Army soldiers in 99 companies; well-being, leadership climate, work hours, cohesion. Bliese, P. D., & Halverson, R. R. (1996). Individual and nomothetic models of job stress: An examination of work hours, cohesion, and well-being. *Journal of Applied Social Psychology, 26*, 1171–1189.
- `univbct`: 495 soldiers in 8 companies measured at three time points; job satisfaction, commitment, readiness. Bliese, P. D., & Ployhart, R. E. (2002). Growth modeling using random coefficient models: Model building, testing, and illustrations. *Organizational Research Methods, 5*, 362–387.

## Findings

*(Write this section yourself after finishing the notebooks: three to five bullets, plain language, one number each.)*

-
-
-

## Before publishing (delete this section afterward)

- [ ] Every `NULL` replaced and every check shows `[ok]`
- [ ] Every interpretation and answer cell written in your own words
- [ ] Run all cells top to bottom so the saved notebooks show outputs on GitHub
- [ ] Findings section above filled in
- [ ] You can explain, without notes: ICC(1) vs. ICC(2), the design effect, within vs. between vs. contextual effects, why centering matters for random slopes, why the time standard error went *down* in notebook 03, regression to the mean, and fixed vs. random effects for 8 groups
- [ ] Optional: the soccer extension in notebook 03, Part I
- [ ] Only then add it to the resume and link it from GitHub
