# neutrino-mass-lab
All code used during the creation of the neutrino mass lab report by Amir Sufa and Ben Gordon.

# Running the notebook

## In Google Colab
1. Upload the notebook to any open Google Colab window (the Colab environment already includes the required dependencies).
2. Open the **Files** sidebar on the left, and upload/copy the `neutrino-mass-data` directory into `/content/` (so it sits alongside the default `sample_data` directory).
3. The paths in the Colab notebook are already configured for `/content/neutrino-mass-data/`.

## Locally
We recommend using the VS Code extension for Jupyter notebooks.

1. In your selected virtual environment (or default Python environment), install the dependencies using the provided `requirements.txt` file:
   ```bash
   pip install -r requirements.txt
   ```
2. Update the file paths at the start of the notebook to point to where you saved the `neutrino-mass-data` directory.
