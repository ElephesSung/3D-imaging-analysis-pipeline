# 3D-imaging-analysis-pipeline
An end-to-end Jupyter notebook for 3D time-lapse microscopy analysis: imports raw CZI files, applies anisotropy correction and noise removal, extracts object features, tracks particles with Trackpy and btrack, and offers interactive visualizations via Matplotlib, Plotly, ipywidgets, and Napari. Outputs are saved as pickle and Excel files.

**Author**: Elephes The Martian  
**Affiliation**: Department of Life Sciences (DoLS), Imperial College London  
**E‑mail**: eu23@ic.ac.uk  
**Last updated**: 28 July 2025

---

## Description

This Jupyter notebook implements a complete pipeline for processing and analyzing 3D time‑lapse biological imaging datasets. It covers:

- **Data Import**: Loading multi‑dimensional image and mask files (e.g., CZI) into NumPy arrays.  
- **Pre‑processing**: Correcting anisotropy, removing noise and small artifacts, and standardizing voxel dimensions.  
- **Region Extraction**: Computing per‑frame object properties (volume, intensity statistics, shape descriptors) using `skimage.measure.regionprops`.  
- **Tracking**: Linking objects over time with `trackpy` and `btrack`, and calculating dynamic metrics such as speed and turning angle.  
- **Visualization**: Interactive plotting controls via `ipywidgets`, inline Matplotlib plots, and 3D visualization in Napari.  
- **Export**: Saving raw and filtered tracking results to binary (`.pkl`) and Excel (`.xlsx`) files for downstream analysis.

## Requirements

- Python 3.8+  
- Jupyter Notebook or JupyterLab

**Key Python libraries:**
```
numpy, pandas, scipy, matplotlib, seaborn, plotly,
scikit-image, tifffile, aicspylibczi (or czifile), pims,
cellpose, btrack, trackpy, napari, ipywidgets,
tqdm, joblib, colorama
```

## Installation

Install dependencies via pip:
```bash
pip install numpy pandas scipy matplotlib seaborn plotly \
            scikit-image tifffile aicspylibczi pims \
            cellpose btrack trackpy napari ipywidgets tqdm joblib colorama
```

## Usage

1. Clone or download the repository containing `Tracking_Basu.ipynb`.  
2. Open a terminal and navigate to the notebook directory.  
3. Launch Jupyter:
   ```bash
   jupyter notebook Tracking_Basu.ipynb
   ```
4. In the notebook, configure the input/output paths and calibration parameters (pixel size, frame interval).  
5. Execute cells in order to process images, extract features, track objects, and visualize results.  
6. Generated outputs:
   - `ioi_tracking.pkl`: Pickled tracking dictionary per file.  
   - `ioi_tracking_filtered_with_sphericity.xlsx`: Excel workbook with filtered tracks and computed sphericity metrics.

## Notebook Structure

1. **Importing Libraries**: Load all required packages and initialize settings.  
2. **Plotting Control Panel**: Interactive widgets to tweak visualization parameters.  
3. **α‑1. Import Data**: Read image and mask files into memory.  
4. **α‑2. Pre‑processing**: Apply anisotropy correction and small object removal.  
5. **γ‑1. Region Extraction**: Calculate object properties for each frame.  
6. **Δ. Tracking**: Link objects over time and compute dynamics.  
7. **Visualization & Analysis**: Plot time‑series metrics and scatter comparisons (e.g., sphericity vs. volume).  
8. **Export**: Serialize and save results for further downstream analysis.

## Contact

For questions or collaborations, please reach out to Elephes The Martian at eu23@ic.ac.uk.

## License

This project is licensed under the MIT License. Feel free to use and modify it for academic or commercial purposes.

