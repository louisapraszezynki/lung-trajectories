# Childhood lung function trajectories
## Objective

Modelling, phenotyping and validation of FEV1 growth in a pediatric cohort, to prepare to apply for the PhD position at the Basel University.

## Data

**Source:** Source: Data courtesy of Dr. Doug Dockery. Six Cities Study of Air Pollution and Health, lung growth subsample
(Topeka, Kansas).

The raw data file is not included in this
repository; download `fev1.dta` from the book's website and place it in `data/`.

**Population:** Subsample (N=300) of data on FEV1 and height for girls living in
Topeka from the Six Cities Study of Air Pollution and Health

**Format:** one row per child per visit

### Data dictionary

| Variable | Type | Unit | Description |
|---|---|---|---|
| `id` | integer | – | Unique child identifier |
| `height` | float | metres | Height at the visit (`ht` in the raw file) |
| `age` | float | years | Age at the visit |
| `init_height` | float | metres | Height at the child's first visit (`baseht`); constant within child |
| `init_age` | float | years | Age at the child's first visit (`baseage`); constant within child |
| `log_fev1` | float | log(litres) | Natural log of FEV1 (`logfev1`) |
| `fev1` | float | litres | **Derived:** `exp(log_fev1)` |

*FEV1 (forced expiratory volume in 1 second) is the volume of air a person can
forcefully exhale in the first second, and is the main measure of lung function
in spirometry.*

### Notes
- The raw file has no variable labels; meanings were inferred from the values and
  the dataset documentation.
- The data contain no empty cells, but visits are irregular: some children have long
  gaps between measurements (e.g. child 2 has no visits between ages 7.6 and 12.7).
  Missing visits are analysed in `notebooks/01_exploration.ipynb`.
- The sample includes girls only and was collected in the 1970s–80s, so results may
  not generalise to boys, to current populations, or to preterm-born children.