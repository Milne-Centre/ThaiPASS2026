# ThaiPASS 2025 — How Giants Grow

A short astronomy workbook for high-school students who want to **weigh a real
supermassive black hole**. Using a single SDSS spectrum of the nearby Seyfert-1
galaxy **Markarian 79**, students:

1. Plot a real astronomical spectrum.
2. Use **PCA** to separate galaxy starlight from AGN (black-hole) light.
3. Fit the **broad Hβ emission line** with a Gaussian.
4. Compute the central black hole's mass in solar masses.

Designed for ~1–2 hours of class time, with light instructor guidance. No prior
Python experience needed — every exercise is scaffolded with a `# YOUR CODE HERE`
blank.

## What's in this repo

- `agn_spectral_analysis.ipynb` — the workbook (Jupyter notebook).
- `content/`
  - `spec_542_51993_560.fits` — bundled SDSS spectrum of Mrk 79.
  - `eigSpec_qso_*.dat` (×50) — quasar PCA templates.
  - `galaxyKL_eigSpec_*.dat` (×10) — galaxy PCA templates.
  - `table_dr16_qso_krc213.csv` — DR16 quasar catalog (40,878 entries) for the
    optional "try a different AGN" stretch goal.

## Three ways to run it — pick whichever is easiest

### Option 1 — Run in Google Colab (recommended; nothing to install)

1. Open the workbook on Colab:
   <https://colab.research.google.com/drive/1h8eCw73PzeT1h6J8fluEGVnAb60wdapZ?usp=sharing>
2. Click **File → Save a copy in Drive** so you get your own editable version.
3. Open the data folder on Drive
   (<https://drive.google.com/drive/folders/1jwo_aVMBQVNcQZS9ttcaN8428oQoU8uK?usp=sharing>)
   and **right-click → "Add shortcut to Drive" → My Drive**. This puts a link
   to the data folder inside *your* Drive without copying any files.
4. In your Colab copy, add a new cell at the very top and run:

   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   import os
   os.chdir('/content/drive/MyDrive/AGN2026')   # adjust if your shortcut has a different name
   ```

5. Run the rest of the cells in order with `Shift + Enter`.

### Option 2 — Download from Google Drive and run locally

1. Download the entire `AGN2026` folder from
   <https://drive.google.com/drive/folders/1jwo_aVMBQVNcQZS9ttcaN8428oQoU8uK?usp=sharing>.
2. Install dependencies (one-time):

   ```bash
   pip install numpy scipy matplotlib astropy pandas jupyter
   ```

3. Launch Jupyter from inside the folder:

   ```bash
   cd AGN2026
   jupyter notebook agn_spectral_analysis.ipynb
   ```

### Option 3 — Clone the GitHub repo

```bash
git clone https://github.com/<your-username>/ThaiPASS2025.git
cd ThaiPASS2025
pip install numpy scipy matplotlib astropy pandas jupyter
jupyter notebook agn_spectral_analysis.ipynb
```

## Prerequisites

- Algebra II / pre-calculus and basic statistics (mean, variance).
- A web browser if running on Colab; Python 3.9+ if running locally.
- No prior Python or astronomy background required.

## Optional dependency

The "try a different AGN" stretch goal at the end uses `astroquery.sdss` to
download a different spectrum from SDSS over the internet. Install with:

```bash
pip install astroquery
```

The main workbook does **not** need it — the example spectrum is bundled in
`content/`.

## Credits & sources

- Spectra: **Sloan Digital Sky Survey** Data Release 16
  (<https://www.sdss.org/dr16/>).
- PCA eigenspectra: **Yip et al. (2004)** — galaxy and quasar template sets
  derived from SDSS DR1/2.
- Black-hole mass relation: **Vestergaard & Peterson (2006)**, single-epoch
  virial estimator using broad Hβ FWHM and λL_λ(5100 Å).
- Reference value for Mrk 79's mass: **Peterson et al. (2004)** reverberation
  mapping campaign, log₁₀(M/M☉) ≈ 7.7.

## License

Educational use. Underlying SDSS data are public-domain; please cite the SDSS
collaboration if you redistribute results.
