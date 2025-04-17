# lassifying Tumors In MRI Scans

## Repository Contents
This repository contains all of the necessary files and scripts for .... The analysis aims to determine whether different modeling techniques, ... , can ...

## 1. Software and Platform

### Programming Languages and Software
- **R**: For data preprocessing, model assumption testing, developing and evaluating the ...

### R Packages
- `tidyverse` – Data cleaning and data filtering
- `dplyr` – Data cleaning and data filtering
- `kableExtra` – Assistance for table layouts 

### Platform Compatibility
Developed and tested on Mac, but should work on Windows and Linux with appropriate installations.

## 2. Project Folder Structure

```
📂 S&P-500-Times-Series-Analysis  
 ├── 📂 data/  
 ├──── 📂 INITIAL/
 │   │   ├── brainTumorDataPublic_1-766
 │   │   ├── brainTumorDataPublic_1533-2298
 │   │   ├── brainTumorDataPublic_2299-3064
 │   │   ├── brainTumorDataPublic_767-1532
 ├──── 📂 FINAL/
 │   │   ├── JPG_Images
 │   │ MRI Scans Data Appendix.pdf
 │
 ├── 📂 SCRIPTS/  
 │   ├── 01_........Rmd
 │  
 ├── 📂 OUTPUT/  
 │   ├── exploratory_plots.jpeg
 │  
 ├── README.md   
```
## 3. Instructions for Reproducing Results

### Stage 1: Data Preparation and Sentiment Analysis in Python
- Download the MRI photo data set from the *link*

  ```r
  install.packages("tidyverse")
  install.packages("dplyr")
  install.packages("kableExtra")
  ```
-
- Run the code file to obtain the relevant figures and models. Since we are using the `kableExtra` package, all figures will only appear when you knit your `.Rmd` file. Knitting to HTML has been found to be the easiest way to do this. The following is an outline of the figures:

  - **Times Series Plots** (contains multiple times series plots to determine stationarity)
  - **Differencing** (contains times series plots of differenced data)
  - **ACF + PACF Plots for ARIMA Model Building** (contains the ACF and PACF plot of transformed data for ARIMA model building)
  - **ARIMA Model Performance** (contains the summarized model performance metrics of the ARIMA models)
  - **ACF + PACF plots + Hypothesis Testing for GARCH Model Building** (contains the ACF and PACF plot of log returns for GARCH model building)
  - **GARCH Model Performance** (contains the summarized model performance metrics of the GARCH models)
- Annotate any figures using Google Slides
