## 2/12/2022

* Included RBD levels file, tracking convergence of key spike proteins
(seee https://virological.org/t/sars-cov-2-evolution-post-omicron/911#post_1)


## 25/11/2022

* Added XBC (including all descendant lineages) to list of tracked variants
   - prior to change XBC genomes were not assigned to a VOC, so excluded from summary data

* Retired BA.4.6 from the list of tracked variants
   - genomes identified as BA.4.6 previously will now be included in BA.4

## 11/11/2022

* Added XBB (including all descendant lineages) to list of tracked variants
* Prior to this change most XBB genomes were identified as BA.2 (reflecting `pangolin` designation)

## 03/11/2022

* Added BQ.1.1 to list of tracked variants
* Values for BA.5 now exclude this lineage and its descendants

## 07/10/2022 

* added `data/all_variant_counts.csv` file
* community and border cases files will no longer be updated as these classes of
case can no longer be reliably distinguised.

## 16/09/2022

* added BA.4.6 to all datasaets
* Values for BA.4 are all BA.4 excluding this specific lineage

## 22/7/2022

* added BA.2.75 to both datasets.
* retired BA.2.12.1, as this lineage is not longer a focus of ESR reporting.

## 15/7/2022

* rolling meaning for VOC is now 'right-aligned' (i.e. is  mean of the
preceding 7 days), meaning most-recent dates are no longer NA-padded.
* prettified the example plot a tiny bit
