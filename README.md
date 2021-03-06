
# Prevelence of SARS-CoV-2 Variants of Concern in Aoteoroa New Zealand

The `data/` directory contains two csv files,
`community_variant_counts.csv` and `border_variant_counts.csv`. Each of
these files contains a rolling 7-day average for the number of genomes
from selected SARS-CoV2-2 lineages or variants of concern sequenced by
ESR for community-acquired and border-associated cases respectively

This data is derived from all cases referred to to ESR for sequencing,
and not a randomised sample of all positive cases.

## Example

A brief example of how the data might be used, using the R language.

``` r
library(lubridate)
library(tidyr)
library(ggplot2)


voc <- read.csv("data/community_variant_counts.csv")
voc$report_date <- ymd(voc$report_date)
tidy_voc <- pivot_longer(voc, !report_date, names_to = "variant", values_to = "n_genomes")

voc_pal <-   c(`Delta` = "#3182bd", 
               `BA.1` = "#bd0026", 
               `BA.2` = "#fd8d3c", 
               `BA.4` = "#B14B02",
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
