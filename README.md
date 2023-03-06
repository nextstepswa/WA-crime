# WA-crime
Official NIBRS data on crime rates in WA State from the Office of Financial Mangagement (OFM), and scripts for analyzing the data

## The data

In WA State we are lucky to have an agency, the Statistical Analysis Center (SAC) of the [Office of Financial Management (OFM)](https://ofm.wa.gov/),
that provides public access to [a range of criminal justice datasets](https://sac.ofm.wa.gov/).  SAC provides an extract of the statewide crime
data from the National Incident Based Reporting System (NIBRS), the system that feeds into the federal Uniform Crime Reports (UCR).

NIBRS allows all offenses charged for a single incident to be recorded.  It replaces the older system (the Summary Reporting System) in which
only the most serious offense would be reported for each incident.  The UCR has been in transition from the SRS to NIBRS for over a decade, and
the SRS was finally phased out in 2020.  NIBRS reporting in WA was in transition from 2012-2018, and some of the largest agencies in the state
did not complete the transition until the end of the period.  For anyone using these data to examine trends over time at county or statewide aggregate levels,
it is important to keep this in mind. There is a section of [this report](https://rpubs.com/moxbox/wa_crime2021)
that discusses the issue in more detail.  

SAC aggregates the NIBRS reports by jurisdiction at 3 different levels: the reporting law enforcement agency, the county total and the statewide total, and
provides a location-based, cleaned, harmonized NIBRS series starting in 2012, along with estimates of the population by juridiction.
The most recent year is updated each October -- for example, the data for 2022 will be available
in October of 2023, so there is a substantial lag in the system.

* The data set is location-based:  each record is one jurisdiction
* [Data fields include](https://sac.ofm.wa.gov/sites/default/files/public/pdf/nibrs_dictionary.pdf):
  + Location = jurisdiction -- LEA, county or statewide 
  + county = county name
  + IndexYear	= calendar year
  + Population = of location jurisdiction
  + Total	= total number of crimes
  + Rate = 1000 * Total / Population
  + PrsnTotal	= total number of crimes against persons
  + PrsnRate = 1000 * PrsnTotal / Population
  + PrprtyTotal	= total number of property crimes
  + PrprtyRate = 1000 * PrprtyTotal / Population
  + ScttyTotal	= total number of property crimes
  + SctyRate = 1000 * SctyTotal / Population
  + and the number of crimes in each of 23 offense categories (which includes 47 specific offenses)


## The script

This respository contains a script that downloads the OFM/SAC NIBRS data and produces a report that examines the trends, statewide
and by jurisdiction for the largest population centers in the state.  The script is based on the [R statistical computing language](https://www.r-project.org/).
**R** is a professional, flexible open-source computing platform for statistical analysis and graphics.  It is free to download, and runs on
a wide range of Unix, Windows and MacOS platforms.

The script uses [rmarkdown](https://bookdown.org/yihui/rmarkdown/) and [knitr](https://www.rstudio.com/tags/knitr/) to create a transparent, reproducible workflow.

## Questions?

* If you find an error or bug, please report this via an [issue](https://github.com/nextstepswa/WA-crime/issues) on the repo.  
* For more general or open-ended questions, please consider starting a [discussion](https://github.com/nextstepswa/WA-crime/discussions).

Suggestions and productive comments always welcome.


