# Cursive Line Segmentation for Historical Manuscripts

> An unsupervised seam-carving pipeline for converting 19th-century cursive manuscript pages into individual text-line images.

## Overview

This repository is the public research-code home for a line-segmentation pipeline designed to prepare historical handwritten documents for downstream transcription. The workflow crops rough page borders, binarizes the image, identifies low-cost horizontal seams through background regions using dynamic programming, and extracts individual text-line images.

The method was developed for 19th-century cursive manuscript pages, where connected components can merge across lines because ascenders and descenders overlap. The project is described in the supplied [UWM 2026 poster](docs/poster/DedeM_Summer_2026_Poster_Final.pdf).

## Project poster

[View the project poster (PDF)](docs/poster/DedeM_Summer_2026_Poster_Final.pdf).

## Repository contents

| Path | Purpose |
|---|---|
| `src/` | Reusable preprocessing and segmentation code. |
| `scripts/` | Reproducible command-line entry points. |
| `configs/` | Documented parameter sets for experiments. |
| `examples/` | Small, approved example inputs and outputs. |
| `docs/poster/` | The supplied UWM 2026 project poster. |
| `data/README.md` | Dataset provenance and access instructions. The full corpus is not bundled. |

## Method

The project pipeline consists of border cropping, binarization, seam carving, line extraction, and optional heuristic text assignment. The method should be evaluated with special attention to dense pages and overlapping cursive because segmentation can degrade in those cases.

## Quick start

Add the project’s tested dependencies to `requirements.txt`, then replace the sample command below with the command verified for this repository.

```bash
git clone https://github.com/PMartey/historical-manuscript-line-segmentation
cd historical-manuscript-line-segmentation
python -m venv .venv
# Windows PowerShell: .venv\Scripts\Activate.ps1
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
python scripts/run_example.py --input examples/input/[SAMPLE_FILE] --output examples/output/[RUN_NAME]
```

> Do not leave an untested quick-start command in the public README.

## Data access and responsible reuse

The full manuscript corpus is not redistributed in this repository. Consult [DATA_POLICY.md](DATA_POLICY.md) and [data/README.md](data/README.md) before acquiring, using, or redistributing collection material.

## Citation

Before public release, copy `CITATION.cff.template` to `CITATION.cff`, replace every bracketed value, and use the resulting **Cite this repository** option on GitHub.

## Authors and acknowledgments

The supplied project poster credits Pamela Martey, Micah Hesketh, and Dr. Istvan Lauko. Confirm all author, institutional, source-collection, and funder wording before the public release.

## License

Choose a license for the project’s original code only after the authors agree. See `LICENSE-DECISION.md`.

## References

1. Das, M., & Panda, M. (2023). *Seam carving, horizontal projection profile and contour tracing for line and word segmentation of language independent handwritten documents*. Results in Engineering, 19, 101110. https://doi.org/10.1016/j.rineng.2023.101110
2. Newberry. *Policies: Open Access Policy*. https://www.newberry.org/policies
3. [Project poster (PDF)](docs/poster/DedeM_Summer_2026_Poster_Final.pdf)
