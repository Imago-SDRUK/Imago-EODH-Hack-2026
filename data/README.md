# Data

Ready-to-use tables for **From Pixels to Policy: An Earth Observation Hackathon**. They cover the seven local authorities of the North East Mayoral Strategic Authority (Newcastle upon Tyne, Gateshead, North Tyneside, South Tyneside, Sunderland, County Durham and Northumberland) on 2021 boundaries.

| File | Rows | Contents |
|------------------------|-----------|------------------------------------|
| `ne_lsoa_population_imd.csv` | 1,257 LSOAs | Census 2021 population, age and tenure; IMD 2025 score, rank and decile; selected domain scores and deciles |
| `ne_msoa_population_imd.csv` | 253 MSOAs | The same, aggregated from LSOAs: population counts and shares, population-weighted IMD and domain scores, share of residents in England's most deprived 20% of LSOAs |
| `ne_population_imd_variables.csv` | | Description of every column (machine-readable) |

Full column definitions and guidance on reading the deprivation variables are in [`VARIABLES.md`](VARIABLES.md).

Join to boundaries and to the Imago products with `lsoa21cd` or `msoa21cd`.

**Boundaries.** `ne_lsoa_2021_boundaries.gpkg` holds the 1,257 North East LSOAs (British National Grid, EPSG:27700; key `LSOA21CD`). It is cut from [LSOA boundaries for the United Kingdom (2021)](https://data.imago.ac.uk/datasets/lsoa-boundaries-for-the-united-kingdom-2021) in the Imago Data Catalogue. To rebuild it, download that file as `data/uk_datazones_2021.gpkg` (not committed: too large) and run section 9.4 of the notebook.

**Notes**

-   IMD ranks and deciles are national (England) and only meaningful at LSOA level. For MSOAs, use the population-weighted scores.
-   Percentages are of usual residents (age) or of households (tenure).

**Sources** (Open Government Licence v3.0): ONS Census 2021 tables TS001, TS007A and TS054 via Nomis; MHCLG English Indices of Deprivation 2025, File 7. Built by the notebook [`scripts/01_population_imd_north_east.ipynb`](../scripts/01_population_imd_north_east.ipynb).
