# Filed Under: birth timing

*Notes from the field. Charts from the wild.*

**Full post:** [filedunderpub.substack.com](https://filedunderpub.substack.com) ← update with direct post link when published

---

## The finding

Cesarean deliveries on weekdays are significantly elevated between 06:00 and 17:59
compared to the same windows on weekends. The strongest difference is in the
06:00–08:59 window: weekday median of 1,818 births per day versus 503 on weekends.
The pattern does not hold overnight.

Vaginal deliveries show no statistically significant weekday–weekend difference in
any time window after correction for multiple comparisons.

The scheduling signal in this dataset is concentrated entirely in cesarean deliveries.

---

## What's in this repo

| File | Contents |
|---|---|
| `data/time_of_birth_dataset.csv` | CDC WONDER natality data, 2022–2024, grouped by state, year, month, weekday, time of day, and delivery method |
| `analysis.Rmd` | Data loading, completeness filtering, wrangling, Wilcoxon rank-sum tests, and observations |
| `output/birth_timing.png` | The published chart |

The visual theme is proprietary and not included. Anyone running `analysis.Rmd`
can reproduce the data and statistical findings; the chart styling is not part of
this repository.

---

## Data source

Centers for Disease Control and Prevention, National Center for Health Statistics.
National Vital Statistics System, Natality on CDC WONDER Online Database. Data are
from the Natality Records 2016–2024, as compiled from data provided by the 57 vital
statistics jurisdictions through the Vital Statistics Cooperative Program.

Accessed at http://wonder.cdc.gov/natality-expanded-current.html on May 23, 2026.

Years included: 2022, 2023, 2024.
Query parameters: Delivery Method (Cesarean & Vaginal), grouped by State of
Residence, Year, Month, Weekday, Time of Day. Suppressed and zero values excluded.

---

## Methodology notes

Analysis is limited to timepoints where at least 47 of 51 reporting areas
(50 states + DC) contributed data, covering approximately 75% of raw observations.

Average births per day are computed by dividing weekday totals by 5 and weekend
totals by 2, to make the two groups directly comparable.

Wilcoxon rank-sum tests (Mann–Whitney U, two-sided) compare weekday and weekend
births per day for each of 16 groups (8 time windows × 2 delivery methods).
P-values adjusted using Benjamini–Hochberg correction.

Full code and annotated output are in `analysis.Rmd`.

---

*Filed Under. Observed in the wild.*
