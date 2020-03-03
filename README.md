# cv4a-iclr-2020-starter-notebooks

Repository containing notebooks to get started on the [CV4A challenge at ICLR 2020](https://zindi.africa/competitions/iclr-workshop-challenge-2-radiant-earth-computer-vision-for-crop-recognition) using [`eo-learn`](https://github.com/sentinel-hub/eo-learn#eo-learn).

## Content

The [`cv4a-crop-challenge-to-eolearn`](./cv4a-process-and-train.ipynb) notebook converts the data provided as `.tiff` files into smaller `EOPatch` format files. This allows to better handle and visualise data as rasters, and to easily apply processing pipelines. 

The [`cv4a-process-and-train`](./cv4a-process-and-train.ipynb) notebook shows how to set up a processing pipeline on `EOPatch` objects, such as cloud masking and feature interpolation. This way, different pre-processing methods can be quickly tested.

The pipeline shown in the notebook includes:

 * conversion of cloud probabilities to cloud masks;
 * dilation of cloud masks;
 * `NDVI` computation;
 * linear interpolation to fill missing values;
 * utility tasks to get insights into data.
 
Features are then aggregated and used to train/evaluate a machine learning model.
 
In this starter's notebook, an untuned random forest classifier was trained on the temporal features, achieving a public score of **1.26628**.

The [`SampleSubmission.csv`](./SampleSubmission.csv) template file is added for completion.

## Requirements

The notebook assume that the data has been downloaded according to the challenge instructions. Set the path to the data in the notebooks as `ROO_DATA_DIR`.

Installing `eo-learn` according to [instructions](https://github.com/sentinel-hub/eo-learn#pypi-distribution) should cover all dependencies used in the notebooks.

## Improvements

As already noted by organisers and participants, these additions should improve performance and generalisation of the methods:

 * dealing with class imbalance (e.g. over-sampling, under-sampling, SMOTE);
 * feature analysis and engineering adding domain specific indices. You can check [this repo](https://github.com/sentinel-hub/custom-scripts#sentinel-2) for inspiration on vegetation indices derived from Sentinel-2 data;
 * use ML methods that better characterize temporal evolution of crops.
 
Good luck to all.
