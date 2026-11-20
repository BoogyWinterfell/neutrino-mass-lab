# Finding an Upper Limit for the Electron Neutrino's Mass

## Abstract
This repository contains the raw experimental data and analysis code for the laboratory report *Finding an Upper Limit for the Electron Neutrino's Mass* by Amir Sufa and Ben Gordon. In this experiment, we calibrated a radiation detection system using pulser measurements and standard gamma-ray sources (<sup>133</sup>Ba, <sup>241</sup>Am, <sup>137</sup>Cs, and <sup>54</sup>Mn), and measured the beta-decay spectrum of <sup>204</sup>Tl to determine an upper bound on the electron antineutrino mass. The Jupyter notebook in this repository parses raw multichannel analyzer (MCA) count files, performs piecewise Gaussian peak fitting and Orthogonal Distance Regression (ODR) channel-to-energy calibrations, and analyzes the <sup>204</sup>Tl endpoint spectrum. Running the notebook reproduces all calibration curves, spectral fits, residual plots, and final figures presented in the paper.

## File Descriptions

### Analysis & Environment Files
* **`Neutrino_Mass_Workspace_Amir_and_Ben.ipynb`**
  * **Description:** Main analysis notebook that loads raw MCA spectra, fits Gaussian and exponential+Gaussian peak models to pulser and gamma calibration data, performs ODR linear regressions for channel-to-energy calibration, and fits the <sup>204</sup>Tl beta spectrum to extract the endpoint energy and neutrino mass bound.
  * **Inputs:** All `.txt` measurement files located in `neutrino-mass-data/OriginalMeasurements/`.
  * **Outputs:** Generates all calibration curves, spectral fits, residual plots, and beta endpoint / Kurie plots presented in the paper.
* **`requirements.txt`**
  * **Description:** Lists the Python package dependencies required to run the analysis notebook locally.
  * **Inputs:** None.
  * **Outputs:** Installs the required Python environment when passed to `pip install -r requirements.txt`.

### Raw Data (`neutrino-mass-data/OriginalMeasurements/`)
* **`100 mV Pulser FINAL.txt`**
  * **Description:** Raw MCA channel-count spectrum for a constant 100 mV pulser signal recorded across multiple amplifier gain settings.
  * **Inputs:** None (raw experimental data).
  * **Outputs:** Used by `Neutrino_Mass_Workspace_Amir_and_Ben.ipynb` to generate the piecewise Gaussian peak fits and linear ODR pulser calibration plot.
* **`200 Times Amp 10-20-40-60-80-100 mV FINAL.txt`**
  * **Description:** Raw MCA channel-count spectrum for pulser amplitudes of 10, 20, 40, 60, 80, and 100 mV at 200× amplification to verify detector linearity.
  * **Inputs:** None (raw experimental data).
  * **Outputs:** Used by `Neutrino_Mass_Workspace_Amir_and_Ben.ipynb` to generate the amplifier voltage-linearity calibration plot in the paper.
* **`Amp6-40-Ba133.txt`**
  * **Description:** Raw gamma-ray energy spectrum of <sup>133</sup>Ba used for low-to-mid energy channel calibration.
  * **Inputs:** None (raw experimental data).
  * **Outputs:** Used by `Neutrino_Mass_Workspace_Amir_and_Ben.ipynb` to produce the <sup>133</sup>Ba ODR peak fit.
* **`Amc 241 Amp 250.txt`**
  * **Description:** Raw gamma-ray energy spectrum of <sup>241</sup>Am recorded at 250× amplification for low-energy calibration.
  * **Inputs:** None (raw experimental data).
  * **Outputs:** Used by `Neutrino_Mass_Workspace_Amir_and_Ben.ipynb` to produce the <sup>241</sup>Am ODR peak fit.
* **`Amp6-40-Cs137.txt`**
  * **Description:** Raw gamma-ray spectrum of <sup>137</sup>Cs used to evaluate high-energy photopeak visibility and Compton continuum behavior.
  * **Inputs:** None (raw experimental data).
  * **Outputs:** Used by `Neutrino_Mass_Workspace_Amir_and_Ben.ipynb` to produce the <sup>137</sup>Cs spectrum plot.
* **`Amp 6-40-Mn54.txt`**
  * **Description:** Raw gamma-ray energy spectrum of <sup>54</sup>Mn (835 keV photopeak) used for high-energy channel calibration.
  * **Inputs:** None (raw experimental data).
  * **Outputs:** Used by `Neutrino_Mass_Workspace_Amir_and_Ben.ipynb` to produce the <sup>54</sup>Mn peak fit and final channel-to-energy calibration plot in the paper.
* **`Amp 6-40-Tl204.txt`**
  * **Description:** Raw beta-decay energy spectrum of <sup>204</sup>Tl used to analyze the spectral endpoint and bound the electron antineutrino mass.
  * **Inputs:** None (raw experimental data).
  * **Outputs:** Used by `Neutrino_Mass_Workspace_Amir_and_Ben.ipynb` to produce the <sup>204</sup>Tl beta spectrum and endpoint fit plots in the paper.

---

## Running the Notebook

### In Google Colab
1. Upload `Neutrino_Mass_Workspace_Amir_and_Ben.ipynb` to any open Google Colab window (the Colab environment already includes the required dependencies).
2. Open the **Files** sidebar on the left and upload/copy the files under `neutrino-mass-data/OriginalMeasurements` directory into `/content/` (so it sits alongside the default `sample_data` directory).
3. Run all cells (`Runtime > Run all`). The paths in the notebook are pre-configured for `/content/neutrino-mass-data/`.

### Locally (VS Code)
1. In your selected virtual environment, install the dependencies:
   ```bash
   pip install -r requirements.txt
2. Update the data directory path at the top of Neutrino_Mass_Workspace_Amir_and_Ben.ipynb to point to your local neutrino-mass-data folder, then run all cells.
