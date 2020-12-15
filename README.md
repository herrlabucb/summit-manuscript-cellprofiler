# summit-manuscript-cellprofiler
Analysis of synthetic scWB images using CellProfiler.

## Dependencies
This pipeline requires CellProfiler (tested on 4.0.7).
McQuin C, Goodman A, Chernyshev V, Kamentsky L, Cimini BA, Karhohs KW, Doan M, Ding L, Rafelski SM, Thirstrup D, Wiegraebe W, Singh S, Becker T, Caicedo JC, Carpenter AE (2018). CellProfiler 3.0: Next-generation image processing for biology. PLoS Biol. 16(7):e2005970 / [doi](https://doi.org/10.1371/journal.pbio.2005970). PMID: 29969450 (Research article)

## Output
The pipeline outputs 3 CSV files:
**Bands.csv** : a comma delimited file containing the analysis results for each band. See below for details on the columns.
- **ImageNumber**: The index for the image (starts at 1)
- **ObjectNumber** : The index to the the band(starts at 1)
- **AreaShape_Area** : The area of the band in pixels
- **Intensity_IntegratedIntensity_CorrGray** : the sum of the intensities in all pixels in the band. The intensities are taken from the _background-subtracted_ image.
- **Intensity_IntegratedIntensity_OrigBlot** : the sum of the intensities in all pixels in the band. The intensities are taken from the _raw_ image.
- **Location_CenterMassIntensity_X_CorrGray** : the x coordinate of the center of mass using the pixel intensities from the _background-subtracted_ image.
- **Location_CenterMassIntensity_X_OrigBlot** : the x coordinate of the center of mass using the pixel intensities from the _raw_ image.
- **Location_CenterMassIntensity_Y_CorrGray** : the y coordinate of the center of mass using the pixel intensities from the _background-subtracted_ image.
- **Location_CenterMassIntensity_Y_OrigBlot** : the y coordinate of the center of mass using the pixel intensities from the _raw_ image.
- **Location_Center_X** : the x coordinate of the centroid of the band
- **Location_Center_Y** : the y coordinate of the centroid of the band
**Experiment.csv** : metadata about the analysis pipeline
**Image.csv** : summary information about the image that was analyzed.

Additionally, the pipeline outputs an image with the detected bands outlined to `/images/skew_sim_data_BandOutline.png`.