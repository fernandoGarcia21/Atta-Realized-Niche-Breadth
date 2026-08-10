# Realized niche breadth of *Atta* leaf-cutting ants in human-modified landscapes

This repository contains the data-processing and statistical analysis workflows associated with a study comparing the realized niche breadth of two leaf-cutting ant species, *Atta cephalotes* and *Atta laevigata*, across environmental gradients in Santander, Colombia.

The repository provides the Python notebooks and supporting input files required to reproduce the image-processing workflow, environmental analyses, statistical analyses, and figures presented in the manuscript.

## Study overview

The study evaluates whether differences in realized niche breadth are associated with the contrasting occurrence of *A. cephalotes* and *A. laevigata* across human-modified landscapes.

Field surveys were conducted across sampling locations in Santander, Colombia. Colony-level measurements characterized local environmental and structural conditions, including canopy openness, vegetation structure, soil pH, temperature, and mound architecture.

Regional climatic conditions were additionally characterized using ERA5-Land reanalysis data, including:

- 2 m air temperature for February 2024, 2025, and 2026;
- total precipitation for 2024, 2025, and January–July 2026; and
- bare-soil evaporation for 2024, 2025, and January–July 2026.

## Repository structure

```text
.
├── README.md
├── requirements.txt
├── LICENSE
├── CITATION.cff
├── .gitignore
│
├── notebooks/
│   ├── README.md
│   ├── Ants_August2026_OpenCanopyProcessing.ipynb
│   └── Ants_August2026_DownstreamStats.ipynb
│
└── data/
    ├── README.md
    ├── Ants_Fieldwork_Standard_Data.csv
    ├── FieldworkAnts2026_LocationCoordinates.csv
    ├── Mask_White_FishEye.jpeg
    │
    ├── era5_land/
    │   └── .gitkeep
    │
    └── hemispherical_photographs/
        └── .gitkeep
```

## Analysis workflow

The analyses are organized into two main Jupyter notebooks.

### 1. Canopy-openness image processing

`notebooks/Ants_August2026_OpenCanopyProcessing.ipynb`

This notebook processes the hemispherical photographs collected during fieldwork to estimate canopy openness. The workflow includes grayscale conversion, gamma correction, application of a standardized fisheye mask, image thresholding, and estimation of the percentage of illuminated pixels within the analyzed area.

### 2. Downstream statistical analyses

`notebooks/Ants_August2026_DownstreamStats.ipynb`

This notebook contains the downstream data processing, statistical analyses, ERA5-Land climatic data downloading and processing, and generation of figures associated with the study.

The notebook integrates the field measurements, canopy-openness estimates, geographic coordinates, and regional climatic information.

## Data

Small input files required by the analyses are included directly in the `data/` directory.

These include:

- `Ants_Fieldwork_Standard_Data.csv` — main colony-level fieldwork dataset.
- `FieldworkAnts2026_LocationCoordinates.csv` — geographic coordinates of the sampling locations.
- `Mask_White_FishEye.jpeg` — standardized mask used for hemispherical-image processing.

Additional information about these files is provided in `data/README.md`.

## Large datasets

Large input datasets are not tracked directly in this GitHub repository.

### Hemispherical photographs

The original hemispherical photographs used to estimate canopy openness are archived in Zenodo.

**Zenodo:** https://doi.org/10.5281/zenodo.20344008

After downloading the photographs, place them in:

```text
data/hemispherical_photographs/
```

### ERA5-Land data

The nine ERA5-Land GRIB files used for the regional climatic characterization are also archived in Zenodo.

They comprise:

- February 2 m air temperature for 2024, 2025, and 2026;
- total precipitation for 2024, 2025, and January–July 2026; and
- bare-soil evaporation for 2024, 2025, and January–July 2026.

**Zenodo:** https://doi.org/10.5281/zenodo.21877589

After downloading the files, place them in:

```text
data/era5_land/
```

The 2026 precipitation and evaporation datasets represent partial-year accumulations because the analyses were conducted while 2026 was still in progress.

## Installation

The analyses were performed using Python 3.12.3.

To reproduce the computational environment, clone the repository and install the required Python packages:

```bash
git clone https://github.com/fernandoGarcia21/Atta-Realized-Niche-Breadth.git
cd Atta-Realized-Niche-Breadth

python -m venv .venv
source .venv/bin/activate

pip install -r requirements.txt
```

## Reproducing the analyses

After installing the dependencies and downloading the externally archived datasets, run the notebooks in the following order:

1. `notebooks/Ants_August2026_OpenCanopyProcessing.ipynb`
2. `notebooks/Ants_August2026_DownstreamStats.ipynb`

See `notebooks/README.md` for additional information about the purpose of each notebook.

## Data availability

The code and smaller input datasets required to reproduce the analyses are provided in this repository.

Large datasets, including the original hemispherical photographs and ERA5-Land GRIB files used in the analyses, are permanently archived in Zenodo on the links provided above.

## Citation

If you use the data or analysis workflow provided in this repository, please cite the associated publication:

> [Full manuscript citation to be added after publication]

A machine-readable citation will also be provided in `CITATION.cff`.

## License

The source code in this repository is licensed under the MIT License. 
Data originating from external providers, including ERA5-Land reanalysis data and OpenStreetMap map layers used in figure generation, remain subject to their respective licenses and terms of use.

## Contact

For questions regarding the data or analyses, please contact:

**Diego Fernando García Castillo**  
Alumni, Institute of Science and Technology Austria (ISTA) 
diegos99@gmail.com
