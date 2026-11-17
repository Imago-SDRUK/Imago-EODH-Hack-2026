# Variables: population and deprivation tables

Column definitions for the two tables in this folder, which cover the seven local authorities of the North East Mayoral Strategic Authority on 2021 boundaries.

| File | One row per | Rows |
|---|---|---|
| `ne_lsoa_population_imd.csv` | 2021 LSOA | 1,257 |
| `ne_msoa_population_imd.csv` | 2021 MSOA | 253 |

The same descriptions are in `ne_population_imd_variables.csv`, for reading into code.

## Identifiers

| Variable | Description | LSOA | MSOA |
|---|---|:-:|:-:|
| `lsoa21cd` | 2021 LSOA code | ✓ |  |
| `lsoa21nm` | 2021 LSOA name | ✓ |  |
| `msoa21cd` | 2021 MSOA code | ✓ | ✓ |
| `msoa21nm` | 2021 MSOA name | ✓ | ✓ |
| `lad_code` | Local authority district code | ✓ | ✓ |
| `lad_name` | Local authority district name | ✓ | ✓ |
| `n_lsoas` | Number of LSOAs in the MSOA |  | ✓ |

## Population and age (Census 2021, TS001 and TS007A)

| Variable | Description | LSOA | MSOA |
|---|---|:-:|:-:|
| `pop_total` | Usual residents, Census 2021 (TS001) | ✓ | ✓ |
| `pop_age_0_4` | Residents aged 0-4, Census 2021 (TS007A) | ✓ | ✓ |
| `pop_age_65plus` | Residents aged 65 and over, Census 2021 (TS007A) | ✓ | ✓ |
| `pop_age_75plus` | Residents aged 75 and over, Census 2021 (TS007A) | ✓ | ✓ |
| `pct_age_0_4` | % of residents aged 0-4 | ✓ | ✓ |
| `pct_age_65plus` | % of residents aged 65 and over | ✓ | ✓ |
| `pct_age_75plus` | % of residents aged 75 and over | ✓ | ✓ |

## Housing tenure (Census 2021, TS054)

| Variable | Description | LSOA | MSOA |
|---|---|:-:|:-:|
| `hh_total` | Households, Census 2021 (TS054) | ✓ | ✓ |
| `hh_owned` | Owner-occupied households (outright, mortgage or shared ownership) | ✓ | ✓ |
| `hh_social_rented` | Social rented households | ✓ | ✓ |
| `hh_private_rented` | Private rented households (incl. rent free) | ✓ | ✓ |
| `pct_hh_social_rented` | % of households in social rented housing | ✓ | ✓ |
| `pct_hh_private_rented` | % of households in private rented housing | ✓ | ✓ |

## Deprivation, LSOA level (English Indices of Deprivation 2025)

| Variable | Description | LSOA | MSOA |
|---|---|:-:|:-:|
| `imd_score` | IMD 2025 score (higher = more deprived) | ✓ |  |
| `imd_rank` | IMD 2025 rank in England, 1 = most deprived of 33,755 LSOAs | ✓ |  |
| `imd_decile` | IMD 2025 decile in England, 1 = most deprived 10% | ✓ |  |
| `income_score` | IoD 2025 Income domain score (share of people income deprived) | ✓ |  |
| `income_decile` | IoD 2025 Income domain decile, 1 = most deprived | ✓ |  |
| `health_score` | IoD 2025 Health Deprivation and Disability domain score | ✓ |  |
| `health_decile` | IoD 2025 Health Deprivation and Disability decile, 1 = most deprived | ✓ |  |
| `living_env_score` | IoD 2025 Living Environment domain score | ✓ |  |
| `living_env_decile` | IoD 2025 Living Environment decile, 1 = most deprived | ✓ |  |
| `idaopi_score` | IoD 2025 Income Deprivation Affecting Older People score | ✓ |  |
| `idaopi_decile` | IoD 2025 Income Deprivation Affecting Older People decile, 1 = most deprived | ✓ |  |

## Deprivation, MSOA level (aggregated from LSOAs)

| Variable | Description | LSOA | MSOA |
|---|---|:-:|:-:|
| `imd_score_popw` | Population-weighted mean IMD 2025 score of the MSOA's LSOAs |  | ✓ |
| `income_score_popw` | Population-weighted mean Income domain score |  | ✓ |
| `health_score_popw` | Population-weighted mean Health domain score |  | ✓ |
| `living_env_score_popw` | Population-weighted mean Living Environment domain score |  | ✓ |
| `idaopi_score_popw` | Population-weighted mean IDAOPI score |  | ✓ |
| `pct_pop_imd_most_deprived_20` | % of residents in LSOAs among England's most deprived 20% (IMD deciles 1-2) |  | ✓ |
| `imd_score_popw_rank_ne` | Rank of imd_score_popw among North East MSOAs, 1 = most deprived |  | ✓ |

## How to read the deprivation variables

- **Scores**: higher means more deprived. The Income and IDAOPI scores are proportions (0–1) of people who are income deprived; other scores are on their own scale and are best compared, not read on their own.
- **Ranks and deciles** are national: rank 1 and decile 1 are the most deprived in England (out of 33,755 LSOAs). They only apply to LSOAs.
- **MSOA values** are population-weighted means of the scores of the MSOA's LSOAs, the standard way to summarise the indices above LSOA level. Don't average ranks or deciles.
- `pct_pop_imd_most_deprived_20` is the share of an MSOA's residents who live in LSOAs in England's most deprived 20% (IMD deciles 1–2).

## Percentages

- Age percentages are shares of **usual residents** (`pop_total`).
- Tenure percentages are shares of **households** (`hh_total`). Owned includes shared ownership; private rented includes living rent free.

## Joining

Join on `lsoa21cd` or `msoa21cd`. Other files may spell these `LSOA21CD` and `MSOA21CD`: the codes are the same. The LSOA table also gives each LSOA's `msoa21cd`, so it can be used as an LSOA-to-MSOA lookup. Worked examples are in section 10 of [`scripts/01_population_imd_north_east.ipynb`](../scripts/01_population_imd_north_east.ipynb).

## Sources and licence

- Office for National Statistics, Census 2021: TS001 Number of usual residents, TS007A Age by five-year age bands, TS054 Tenure. Via Nomis.
- Ministry of Housing, Communities and Local Government, English Indices of Deprivation 2025, File 7.

Both under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/). Please credit both sources in any outputs.
