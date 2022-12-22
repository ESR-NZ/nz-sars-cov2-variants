
:calendar: This repository will not be updated between December 23rd and
Jan 13th 2023.

# Prevelence of SARS-CoV-2 Variants of Concern in Aoteoroa New Zealand

The `data/` directory contains four csv files, providing rolling 7-day
averages of genomic results. These include two frequently update files.

-   `all_variant_counts.csv`, which includes lineage data from all
    samples sequenced by ESR since the August 2021 Delta outbreak.
-   `rbd_levels.csv`, which includes information on the number of key
    mutations observed in the receptor binding domain of the spike
    protein. Higher values of this measure are [associated with
    increased immune
    evasiveness](https://virological.org/t/sars-cov-2-evolution-post-omicron/911).

In addition two files are provided but no longer updated.

`community_variant_counts.csv` and `border_variant_counts.csv` break
down the lineage data into those cases associated with
community-acquired infections and border-associated infections
respectively. Border and community cases can no longer be reliably
differentiated, so this data is no longer updated.

## Example

A brief example of how the data might be used, using the R language.

``` r
library(lubridate)
library(tidyr)
library(ggplot2)
library(forcats)

voc <- read.csv("data/all_variant_counts.csv")
voc$report_date <- ymd(voc$report_date)
tidy_voc <- pivot_longer(voc, !report_date, names_to = "variant", values_to = "n_genomes")

order_of_arrival <- c("Delta", "BA.1", "BA.2", "BA.5", "BA.4", "BA.2.75", 
"BQ.1.1", "XBB", "XBC")

tidy_voc$variant <- fct_relevel(tidy_voc$variant, order_of_arrival)

voc_pal <-   c(`Delta` = "#3182bd", 
               `BA.1` = "#bd0026", 
               `BA.2` = "#fd8d3c", 
               `BA.4` = "#B14B02",
               `BA.5` = "#FD3A6B",
               `BA.2.75` = "#fecc5c", 
               `BQ.1.1`  = "#5d3cc9", 
               `XBB` = "#b6db3a", 
               `XBC` = "#57badb"
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
