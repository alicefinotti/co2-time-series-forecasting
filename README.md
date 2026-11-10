# CO₂ Time Series Analysis and Forecasting

**R | Time Series Analysis | ARIMA | STL Decomposition**

## Overview

This project analyzes monthly atmospheric CO₂ concentrations measured at the Mauna Loa Observatory and forecasts their evolution using seasonal time-series models. It also illustrates how projected CO₂ concentrations can be translated into temperature-anomaly scenarios, with reference to the Paris Agreement's 1.5°C and 2°C warming thresholds.

The analysis uses observations **through December 2019**, avoiding the pandemic period in model estimation. It was developed as a university group project at the University of Texas at Austin.

## Methodology

- **Time-series exploration:** Examine the long-run trend, annual seasonality, autocorrelation, and stationarity of the monthly CO₂ series.
- **Model development:** Apply STL (Seasonal-Trend decomposition using Loess) and ARIMA models to the trend and seasonal components.
- **Diagnostics:** Assess stationarity with the KPSS test and evaluate fitted-model residuals using autocorrelation and normality diagnostics.
- **Forecasting:** Generate multi-year CO₂ forecasts and uncertainty intervals, then apply an illustrative logarithmic CO₂–temperature sensitivity relationship to assess warming scenarios.

## Findings

The historical CO₂ series exhibits a pronounced upward trend and recurring annual seasonality. The original analysis identified **ARIMA(1,2,2)** for the seasonally adjusted component, alongside a seasonal model, and found clear evidence of non-stationarity (KPSS statistic ≈ 10.38).

Under the project's forecast and climate-sensitivity assumptions, the illustrative temperature scenario reaches the **2°C threshold around August 2059**. This is a model-dependent scenario—not a probabilistic climate forecast or a precise prediction of when the Paris Agreement threshold will be crossed. Actual warming depends on emissions pathways and other climate-system factors beyond the univariate CO₂ model.

## Repository contents

- [`co2_forecasting.Rmd`](co2_forecasting.Rmd) — Time-series preparation, STL/ARIMA modeling, diagnostics, and forecast visualizations
- [`data/monthly_in_situ_co2_mlo.dat`](data/monthly_in_situ_co2_mlo.dat) — Monthly Mauna Loa CO₂ observations
- [`report/report.pdf`](report/report.pdf) — Research report with methodology, results, and figures

## Reproduce the analysis

Install R and RStudio, then install the packages used in the analysis:

```r
install.packages(c("tidyverse", "fpp3", "nortest", "gridExtra", "rmarkdown"))
```

Open `co2_forecasting.Rmd` in RStudio and knit the document from the repository's root directory. The R Markdown code uses the relative path to the data in `data/`.

**Data source:** [Scripps Institution of Oceanography — Keeling Curve, Mauna Loa in situ CO₂ record](https://scrippsco2.ucsd.edu/data/atmospheric_co2/primary_mlo_co2_record.html).
