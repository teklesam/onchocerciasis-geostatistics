# Geostatistical Modelling of Onchocerciasis Prevalence

Why does river blindness persist in Tanzania's Mahenge focus despite 88–93% reported ivermectin coverage? This project models village-level onchocerciasis prevalence from the 2014 REMO surveys with environmental, topographic and hydrological covariates.

## Analyses

- **`tanzania_onchocerciasis_geostatistics.Rmd`**: single-country analysis of 324 villages.
  - Binomial generalised linear mixed models (GLMMs), then a Gaussian-process geostatistical model fitted by Monte Carlo maximum likelihood (PrevMap).
  - Hydrological covariates (D8 flow accumulation, river distance, riparian vegetation) derived from a DEM with WhiteboxTools.
  - Covariates screened for collinearity with variance inflation factors (VIF); temperature and elevation entered as change-point splines with bootstrap CIs.
  - Prevalence surfaces from kriging, population-weighted burden, and maps of the probability that prevalence exceeds a threshold.
- **`multicountry_climate_heterogeneity.Rmd`**: extension pooling four REMO surveys (Tanzania, Cameroon, Malawi, Mozambique).
  - Covariates standardised on one pooled scale, so the climate, hydrology and climate-anomaly (SPEI-12, excess-heat) slopes can be compared across countries.
  - Likelihood-ratio test of whether these slopes differ by country, plus a separate Gaussian-process model for each country. Its AI-use statement is in the file.

## Data

Data are not included. Sources: the REMO onchocerciasis surveys (2014); 2014 rasters of EVI, night-time lights, temperature and precipitation; SRTM elevation via `geodata`; Natural Earth river centrelines; Climate Hazards Center SPEI and CHIRTS products. Place the files in the working directory and knit.

## Tools

R: `PrevMap`, `lme4`, `terra`, `sf`, `whitebox`, `geodata`, `ggplot2`.

## Context

Developed during my MPhil in Population Health Sciences (Health Data Science) at the University of Cambridge, 2025–26.

**Author:** Samuel Tekle Mengistu · [GitHub](https://github.com/teklesam) · [ORCID](https://orcid.org/0000-0002-2817-1421)
