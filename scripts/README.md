# Scripts

Python notebooks used to prepare data for **From Pixels to Policy: An Earth Observation Hackathon**.

You do not need to run these to take part: their outputs are already in [`data/`](../data). They are here so you can see how the data were made, check them, or rebuild them.

| Script | What it does | Outputs |
|------------------------|------------------------------------|------------------------|
| `01_population_imd_north_east.ipynb` | Census 2021 population (total, age, tenure) and English Indices of Deprivation 2025 for the North East Mayoral Strategic Authority area, at LSOA level and aggregated to MSOA | `data/ne_lsoa_population_imd.csv`, `data/ne_msoa_population_imd.csv`, `data/ne_population_imd_variables.csv` |

## Running a notebook

Open the notebook in Jupyter from the repository folder and run the cells in order, in an environment with `pandas` and `requests`:

``` bash
conda activate <your-env>
jupyter lab
```

Raw downloads are cached in `data/raw/`, which is not committed to the repository.
