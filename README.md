<h1 align="center">app-selecting-ICA-components-manually</h1>

<p align="center">
  Marks ICA components for exclusion in an MNE ICA object and saves it with a plot of the components (MNE-Python).
</p>

<p align="center">
  <a href="https://github.com/brainlife/abcd-spec"><img src="https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg" alt="ABCD Spec v1.1"></a>
  <a href="https://doi.org/10.25663/brainlife.app.678"><img src="https://img.shields.io/badge/Brainlife-brainlife.app.678-blue.svg" alt="Run on brainlife.io"></a>
</p>

## At a glance

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Marks ICA components for exclusion in an MNE ICA object and saves it with a plot of the components (MNE-Python).**

Reads an MNE ICA solution, sets ica.exclude and saves the updated ICA file with a topography plot of the components. Use it to record which artefact components should be removed before applying ICA to MEG/EEG data. Warning: on this branch the excluded components are hard-coded to [0, 1] and the exclude parameter is not read.

| | |
|---|---|
| **Inputs** | `neuro/meeg/mne/ica` |
| **Outputs** | `neuro/meeg/mne/ica` · `generic/image/png` |
| **Container** | `brainlife/mne:1.0.2` |
| **Resources** | 8 CPUs |
| **Run it** | [doi.org/10.25663/brainlife.app.678](https://doi.org/10.25663/brainlife.app.678) |

#### Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `ica` | `neuro/meeg/mne/ica` | yes | MNE ICA solution file (ica.fif). |

#### Outputs

| Output | Datatype | Description |
|---|---|---|
| `out_dir` | `neuro/meeg/mne/ica` | ICA file (ica.fif) with the excluded components set. |
| `out_figs` | `generic/image/png` | Plot of the ICA component topographies (ica.png). |

<details>
<summary><b>Parameters</b> (1)</summary>

| Parameter | Type | Default | Description |
|---|---|---|---|
| `exclude` | number |  | Intended indices of the ICA components to exclude; currently not read by main.py (components 0 and 1 are always excluded). |

</details>

<!-- brainlife-app:end -->

## Running the App

### On brainlife.io

Open the App at [doi.org/10.25663/brainlife.app.678](https://doi.org/10.25663/brainlife.app.678), choose `neuro/meeg/mne/ica` from your project, set the parameters and press **Execute**. The results are saved to your project as `neuro/meeg/mne/ica`, `generic/image/png`.

### Locally

You need [Singularity/Apptainer](https://apptainer.org/) (the App runs in `brainlife/mne:1.0.2`), [`jq`](https://jqlang.github.io/jq/).

1. Clone this repository.
2. Create `config.json` with the paths to your inputs and the parameters:

   ```json
   {
       "ica": "/path/to/ica/ica",
       "exclude": "<number>"
   }
   ```

3. Run `./main`.

## app-selecting-ICA-components-manually

documentation

2) Input file is:
    * components to be excluded
    * `ica/fif` ica object file
5) Ouput files are:
    * `ica/fif` ica object file which included the indices to be execluded

## Citing

If you use this App, please cite it, the software it builds on and brainlife.io:

- app-selecting-ICA-components-manually. brainlife.io App. [doi:10.25663/brainlife.app.678](https://doi.org/10.25663/brainlife.app.678)
- Gramfort A, et al. MEG and EEG data analysis with MNE-Python. Front Neurosci 7(267):1-13 (2013). [doi:10.3389/fnins.2013.00267](https://doi.org/10.3389/fnins.2013.00267)
- Hayashi S, Caron BA, Heinsfeld AS, et al. brainlife.io: a decentralized and open-source cloud platform to support neuroscience research. *Nature Methods* 21:809–813 (2024). [doi:10.1038/s41592-024-02237-2](https://doi.org/10.1038/s41592-024-02237-2)
- Avesani P, McPherson B, Hayashi S, et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. *Scientific Data* 6:69 (2019). [doi:10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

## Authors

- Saeed ZAHRAN

## Funding

[![Wellcome-226486/Z/22/Z](https://img.shields.io/badge/Wellcome-226486%2FZ%2F22%2FZ-purple.svg)](https://wellcome.org/)
[![NIH-NINDS-U24NS140384](https://img.shields.io/badge/NIH_NINDS-U24NS140384-green.svg)](https://reporter.nih.gov/project-details/11261037)
[![NIH-NINDS-UM1NS132207](https://img.shields.io/badge/NIH_NINDS-UM1NS132207-green.svg)](https://reporter.nih.gov/project-details/11411328)
[![NIH-NIBIB-R01EB029272](https://img.shields.io/badge/NIH_NIBIB-R01EB029272-green.svg)](https://reporter.nih.gov/project-details/10262925)
[![NIH-NIBIB-R01EB030896](https://img.shields.io/badge/NIH_NIBIB-R01EB030896-green.svg)](https://reporter.nih.gov/project-details/10428625)
[![NIH-NIMH-R01MH126699](https://img.shields.io/badge/NIH_NIMH-R01MH126699-green.svg)](https://reporter.nih.gov/project-details/10460628)
[![NIH-NIDCD-R01DC020088](https://img.shields.io/badge/NIH_NIDCD-R01DC020088-green.svg)](https://reporter.nih.gov/project-details/11140284)
[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1734853)
[![NSF-BCS-2203524](https://img.shields.io/badge/NSF_BCS-2203524-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2203524)
[![NSF-IIS-1636893](https://img.shields.io/badge/NSF_IIS-1636893-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1636893)
[![NSF-OAC-2148729](https://img.shields.io/badge/NSF_OAC-2148729-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2148729)
[![NSF-IIS-1912270](https://img.shields.io/badge/NSF_IIS-1912270-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1912270)
[![NSF-IIS-2148700](https://img.shields.io/badge/NSF_IIS-2148700-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2148700)
[![NSF-OAC-1916518](https://img.shields.io/badge/NSF_OAC-1916518-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1916518)

<sub>brainlife.io, which runs this App, is publicly funded by Wellcome, the U.S. National Institutes of Health and the U.S. National Science Foundation; acknowledging that support helps keep it running.</sub>
