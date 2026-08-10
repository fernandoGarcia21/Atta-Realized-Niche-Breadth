# Analysis notebooks

This directory contains the Python notebooks used to process the field data
and reproduce the analyses presented in the associated manuscript.

## Notebooks

### `Ants_August2026_OpenCanopyProcessing.ipynb`

Processes the original hemispherical photographs collected at the sampling
sites and estimates canopy openness.

The workflow includes image conversion to grayscale, gamma correction,
application of the predefined fisheye mask, classification of illuminated
and shaded pixels, and calculation of the percentage of illuminated pixels
within the analyzed area.

### `Ants_August2026_DownstreamStats.ipynb`

Contains the downstream data processing, statistical analyses, climatic data downloading from ERA5-Land, climatic
data processing, and figure generation used in the manuscript.

This notebook integrates the field measurements, canopy-openness estimates,
sampling coordinates, and ERA5-Land climatic data.

## Recommended execution order

Run the notebooks in the following order:

1. `Ants_August2026_OpenCanopyProcessing.ipynb`
2. `Ants_August2026_DownstreamStats.ipynb`

The required input files and instructions for obtaining the larger external
datasets are described in `../data/README.md`.
