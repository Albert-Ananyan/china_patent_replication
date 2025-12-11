# Replication Files for "Replication of 'China's Low-Productivity Innovation Drive: Evidence from Patents'"

By Albert Ananyan

Northwestern University | POLI SCI 403 | December 2025

## Summary

This repository contains replication materials for a research note that replicates and extends Ang et al. (2023), "China's Low-Productivity Innovation Drive: Evidence from Patents" (*Comparative Political Studies*).

The replication reproduces the authors' core findings on bureaucratic gaming of patent targets following China's 2006 innovation campaign. The extension examines whether party secretary characteristics (age, education, gender) moderate gaming behavior, finding that gaming is universal across all official types.

## Folder Structure

```
china_patent_replication/
├── README.md                         # This file
├── readme.pdf                        # PDF version of this README
├── replication_code.qmd              # Main Quarto document (all replication code)
├── china_patent_replication.pdf      # Rendered PDF paper
├── references.bib                    # Bibliography
├── data/
│   ├── main.dta                      # Main city-year panel dataset
│   └── national_yearly.dta           # National time series data
└── ssrn-3714029.pdf                  # Original Ang et al. (2023) paper
```

## Datasets

This replication uses the original datasets from Ang et al. (2023):

- **main.dta**: Main panel dataset. Unit of analysis is city-year. Contains 276 cities from 1990-2012, including patent outcomes, political competition measures, and party secretary characteristics. Used to generate regression results.

- **national_yearly.dta**: Time series dataset at the national level from 1990-2014. Used to generate Figures 1 and 3 showing aggregate patent trends.

## Variable Mapping

| Variable in Paper | Variable Name in Data |
|-------------------|----------------------|
| Number of patents (log) | `lnpatent_count` |
| Share of novel patents (%) | `patent_novelshare` |
| Intensity of political competition (IPC) | `govrevenueg_cls` |
| Post-Campaign | `post` |
| GDP per capita (log) | `lngdppc` |
| Population growth | `popugrowth` |
| FDI/GDP | `fdishare` |
| Gender | `gender` |
| Age | `age` |
| Education | `edu` |
| Ethnic minority | `minority` |
| Provincial GDP (log) | `lngdp_province` |

## Software Requirements

The analysis was conducted in R. Required packages:

```r
install.packages(c(
  "tidyverse",       # Data manipulation and visualization
  "haven",           # Reading Stata .dta files
  "broom",           # Tidy regression output
  "estimatr",        # Robust standard errors and fixed effects
  "tinytable",       # PDF tables
  "modelsummary",    # Regression tables
  "marginaleffects", # Visualizing interaction effects
  "scales",          # Plot formatting
  "rsample"          # Bootstrap resampling
))
```

To render the Quarto document, install [Quarto](https://quarto.org/docs/get-started/).

## Reproducing the Analysis

1. **Clone or download** this repository

2. **Install R packages** (see above)

3. **Open and render** `replication_code.qmd`:
   - In RStudio: Open the file and click "Render"
   - From command line: `quarto render replication_code.qmd`

All code uses relative paths, so the analysis should run cleanly from start to finish.

## Key Results Replicated

- **Figure 1**: Patent quantity surge after 2006
- **Figure 3**: Novel patent share decline after 2006
- **Table 4 (Models 2-3)**: IPC × Post effect on patent quantity (+) and novel share (-)

## Extension Analysis

The extension tests whether gaming varies by party secretary characteristics using three-way interactions (IPC × Post × Moderator). Results show:

- No significant heterogeneity by age, education, or gender
- Gaming is a universal response to institutional incentives
- Null results robust to winsorization of outcome variable

## Original Data Sources

As documented by Ang et al. (2023):

- Patent variables: China's State Intellectual Property Office (SIPO/CNIPA)
- City-level statistics: China City Statistical Yearbooks
- Party secretary characteristics: China Stock Market & Accounting Research (CSMAR) Database
- Provincial GDP: China National Bureau of Statistics

## References

Ang, Yuen Yuen, Nan Jia, Bo Yang, and Kenneth G. Huang. 2023. "China's Low-Productivity Innovation Drive: Evidence from Patents." *Comparative Political Studies*.

## Contact

Albert Ananyan
Email: albertananyan2031@northwestern.edu
