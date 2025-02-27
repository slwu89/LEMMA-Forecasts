
<!-- README.md is generated from README.Rmd. Please edit that file -->
<!-- # Useage -->
<!-- To run a set of scenarios for Alameda county, you'd run the same code as the non-package version of LEMMA-Forecasts: -->
<!-- ```{r,eval=FALSE} -->
<!-- library(LEMMA.forecasts) -->
<!-- writedir <- normalizePath("~/Desktop/tmp/") -->
<!-- county.dt <- GetCountyData(remote = TRUE) -->
<!-- max.date <- Get1(county.dt[!is.na(hosp.conf), max(date), by = "county"]$V1) -->
<!-- cat("max date = ", as.character(max.date), "\n") -->
<!-- doses.dt <- GetDosesData(remote = TRUE) -->
<!-- county.by.pop <- unique(county.dt[!is.na(population), .(county, population)]) #NA population if no hospitalizations -->
<!-- setorder(county.by.pop, -population) -->
<!-- county.set <- county.by.pop[, county] -->
<!-- county.set <- setdiff(county.set, "Colusa"); cat("excluding Colusa\n") -->
<!-- print(county.set) -->
<!-- # scenario-specific functions are appended with `_scen`, minor difference from other code -->
<!-- RunOneCounty_scen(county1 = "Alameda",county.dt = county.dt,doses.dt = doses.dt,remote = TRUE,writedir = writedir) -->
<!-- ``` -->

# LEMMA.forecasts

This package organizes the functions in **LEMMA-Forecasts** into a
package, for easier use in [Shiny
application](https://slwu89.shinyapps.io/LEMMA-Shiny/). Please see the
vignette for an example of how to use the package.

Within the `R/` directory the code is organized as:

1.  `GenerateEmail.R`
    1.  `GenerateEmail`
2.  `GetCountyData_Scenario.R`
    1.  `GetCountyInputs_scen`
    2.  `Scenario`
    3.  `GetResults_scen`
3.  `GetCountyData.R`
    1.  `GetCountyData`
    2.  `GetStateData`
    3.  `ReadCsvAWS`
    4.  `ConvertNegative`
    5.  `GetOldAdmits`
    6.  `GetAdmits`
    7.  `GetAdmits_notused`
    8.  `GetSantaClaraData`
4.  `GetCountyInputs.R`
    1.  `Get1`
    2.  `GetCountySheets`
    3.  `GetCountyInputs`
5.  `GetDosesData.R`
    1.  `GetDosesData.old`
    2.  `GetDosesData`
    3.  `ReadSFDoses.old`
    4.  `SFDosesToAWS`
    5.  `ReadSFDoses`
6.  `RunCounty_Scenario.R`
    1.  `RunOneCounty_scen`
7.  `RunCounty.R`
    1.  `RunOneCounty`
8.  `CreateStateOverview.R`
    1.  `CreateOverview`
    2.  `RtMap`
