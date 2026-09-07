# CryoMethViz — Group 7 Course Project

English · [简体中文](README.zh-CN.md)

This fork of the PKU-EMBL **Data Visualization and Analysis Methods** course repository contains the Group 7 project on temperature dependence of methane emissions from cryosphere lakes. It combines an R analysis script, processed research data, generated figures and reports, and a static HTML/CSS/JavaScript viewer.

Upstream course materials and licensing remain attributed to [PKU-EMBL/Data-Visualization-and-Analysis-Methods](https://github.com/PKU-EMBL/Data-Visualization-and-Analysis-Methods). The Group 7 work is a student course project, not a peer-reviewed publication or an operational climate model.

## Research question

The project examines how lake temperature relates to three methane-flux pathways:

- diffusive methane flux (`dCH4`);
- ebullitive methane flux (`eCH4`);
- total methane flux (`tCH4`).

The analysis uses Arrhenius-style regressions, mixed-effects models, spatial-correlation methods, and lake-size/depth comparisons to explore apparent temperature sensitivity and heterogeneity.

## Data source

The project README identifies the **Cryosphere Lake Greenhouse Gases Database 2025**, DOI [`10.6084/m9.figshare.29146295`](https://doi.org/10.6084/m9.figshare.29146295), as the source dataset. Consult the dataset record for provenance, citation, and reuse terms.

## Repository layout

| Path | Purpose |
|---|---|
| `group7-dvam-viewer/index.html` | Static project viewer |
| `group7-dvam-viewer/css/` | Viewer styles |
| `group7-dvam-viewer/js/` | Viewer interaction |
| `group7-dvam-viewer/assets/code/main.R` | R analysis workflow |
| `group7-dvam-viewer/assets/data/` | Processed analysis tables |
| `group7-dvam-viewer/assets/images/` | Generated visualizations |
| `group7-dvam-viewer/assets/pdfs/` | Project reports |
| `DVAM_Contribution_Sheet.pdf` | Course contribution record |

## View the project

Serve the static viewer over HTTP to avoid browser restrictions on local `file://` requests:

```powershell
cd group7-dvam-viewer
npx http-server -p 8000
```

Then open `http://localhost:8000/`.

## Re-run the R analysis

The analysis depends on a broad R geospatial and statistical stack, including `sf`, `spatialreg`, `spdep`, `nlme`, `lme4`, `lmerTest`, `tidyverse`, `ggplot2`, and related visualization packages.

```powershell
cd group7-dvam-viewer
Rscript assets/code/main.R
```

Reproduction is not turnkey: the current script includes machine-specific library paths and assumes local data/output locations. Review and replace those paths before running it elsewhere. Package versions are not locked.

## Interpretation limits

- Results are exploratory course analyses of the cited dataset.
- Apparent activation energy from a fitted relationship is not direct proof of a universal biological mechanism.
- Spatial structure, missingness, preprocessing, model choice, and grouping thresholds can change estimates.
- The repository does not claim independent replication, peer review, or prediction validity outside the observed data.

## License and attribution

The repository retains the upstream [MIT License](LICENSE). Dataset, images, reports, and other third-party materials may have separate terms. Cite both the upstream course repository and the source dataset where appropriate.