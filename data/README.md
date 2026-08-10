# Data

This directory contains the input data required to reproduce the image-processing, environmental, and statistical analyses associated with this study.

## Directory structure

```text
data/
├── era5_land/
├── hemispherical_photographs/
├── Ants_Fieldwork_Standard_Data.csv
├── FieldworkAnts2026_LocationCoordinates.csv
├── Mask_White_FishEye.jpeg
└── README.md
```

## Tabular data

### `Ants_Fieldwork_Standard_Data.csv`

Main fieldwork dataset containing the colony-level environmental, edaphic, vegetation, and mound measurements used in the statistical analyses.

### `FieldworkAnts2026_LocationCoordinates.csv`

Geographic coordinates of the sampling locations in Santander, Colombia. These coordinates are used for mapping the sampling sites and extracting or visualizing regional climatic information.

## Image-processing mask

### `Mask_White_FishEye.jpeg`

Predefined binary fisheye mask used during the processing of hemispherical photographs. The mask defines the standardized region of interest within which illuminated and shaded pixels are classified and canopy openness is calculated.

## Hemispherical photographs

### `hemispherical_photographs/`

This directory contains the original hemispherical photographs collected at the colony sampling sites and used to estimate canopy openness.

The photographs are processed by `Ants_August2026_OpenCanopyProcessing.ipynb`, which converts the images to grayscale, applies image-specific gamma correction and thresholding, restricts the analysis to the predefined fisheye mask, and calculates the percentage of illuminated pixels within the analyzed region.

Due to their file size, the original photographs are not tracked in this GitHub repository. They are archived separately in Zenodo.

**Zenodo dataset:** https://doi.org/10.5281/zenodo.20344008

After downloading the dataset, place the photographs inside:

```text
data/hemispherical_photographs/
```

## ERA5-Land climatic data

### `era5_land/`

This directory contains the ERA5-Land reanalysis data used to characterize the regional climatic conditions across the study area.

Nine GRIB files are used:

- 2 m air temperature for February 2024, 2025, and 2026.
- Total precipitation for 2024, 2025, and January–July 2026.
- Bare-soil evaporation for 2024, 2025, and January–July 2026.

The 2026 precipitation and evaporation datasets represent partial-year accumulations because the analyses were conducted while 2026 was still in progress.

Due to their file size, the GRIB files are not tracked in this GitHub repository. The exact files used in the analyses are archived separately in Zenodo.

**Zenodo dataset:** https://doi.org/10.5281/zenodo.21877589

After downloading the climatic dataset, place the GRIB files inside:

```text
data/era5_land/
```

## Data availability

Large input files are archived in Zenodo to provide permanent access to the exact datasets used in the study, while this GitHub repository contains the code and smaller input files required to reproduce the analyses.
