
# Prevelence of SARS-CoV-2 Variants of Concern in Aoteoroa New Zealand

The `data/` directory contains three csv files,
`community_variant_counts.csv` and `border_variant_counts.csv` and
`all_variant_counts.csv`. Each of these files contains a rolling 7-day
average for the number of genomes from selected SARS-CoV2-2 lineages or
variants of concern sequenced by ESR.

With the end of the Covid-19 Protection Framework it is no longer
possible to reliably distinguish border- and community-associated cases.
For this reason, the community and border cases will no longer be
updated. The `all_variant_counts.csv` file contains data on all samples
sequenced by ESR since the August 2021 Delta outbreak.

## Example

A brief example of how the data might be used, using the R language.

``` r
library(lubridate)
library(tidyr)
library(ggplot2)


voc <- read.csv("data/all_variant_counts.csv")
voc$report_date <- ymd(voc$report_date)
tidy_voc <- pivot_longer(voc, !report_date, names_to = "variant", values_to = "n_genomes")

voc_pal <-   c(`Delta` = "#3182bd", 
               `BA.1` = "#bd0026", 
               `BA.2` = "#fd8d3c", 
               `BA.4` = "#B14B02",
               `BA.4.6` = "#A202B1",
               `BA.5` = "#FD3A6B",
               `BA.2.75` = "#fecc5c"
)


ggplot(tidy_voc, aes(report_date, n_genomes, fill=variant)) + 
    geom_area(position = 'fill', colour='black', size=0.3) +
    scale_fill_manual(values=voc_pal)+
    theme_bw(base_size = 16)  
```

![](images/plot-1.png)<!-- -->

## License

The data is released under a [CC-BY 4.0 international
license](https://creativecommons.org/licenses/by/4.0/). You are free to
copy, distribute or adapt this data as long as you acknowledge ESR.
