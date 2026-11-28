
# Hackathon Tutorials

Example Python notebooks for accessing and exploring datasets provided for the IMAGO EODH Hackathon 2026.

Each notebook follows four main sections: Load, Explore, Analyse and Visualise.

## Available notebooks

| Notebook | Dataset | Status |
|---|---|---|
| [01_air_temp.ipynb](01_air_temp.ipynb) | IMAGO Air Temperature (MSOA) | Available |
| [02_rgb.ipynb](02_rgb.ipynb) | RGB Greenspace (LSOA) | Available |
| [03_lst_sentinel3.ipynb](03_lst_sentinel3.ipynb) | Sentinel-3 LST, ~1 km (MSOA) | Available |
| 04_lst_nceo.ipynb | NCEO LST, ~100 m (LSOA) | In preparation |
| [05_eodh_data_access.ipynb](05_eodh_data_access.ipynb) | Accessing Sentinel-2 ARD and Landsat LST through EODH | Available |

The remaining notebooks will be uploaded once the corresponding datasets are ready.

## Data location and paths

The notebooks currently use relative data paths based on the following folder structure used for development and testing:

```text
IMAGO_Hackathon/
├── data/
│   ├── air_temperature/
│   ├── rgb/
│   ├── lst_sentinel3/
│   └── lst_nceo/
└── notebooks/
```

The data paths will be reviewed and updated as needed once the datasets and notebooks are transferred to the allocated team EODH workspaces.

The EODH data access notebook retrieves Sentinel-2 ARD and Landsat LST directly from the online catalogue.

## Purpose

These notebooks provide a starting point for participants to access, understand and visualise the available datasets. Further analysis and exploration will be carried out by participants according to their selected hackathon challenges.

