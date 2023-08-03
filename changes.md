## 04/08/2023

* Addictionof XBC.1.3 to tracked lineages
* This lineage was previously included in the generic "Recombinant" category

## 05/05/2023

* Major chane to list of tracked lineages. 
   - BQ.1.1, XBF and XBC are no longer tracked separately
   - XBB is broken down to include XBB.1.5, XBB.1.16 and XBB (i.e. all others)
   - CH.1.1 is broken to include FK.1.1 and CH.1.1 (i.e all others)
   
Genomes are assigned to  category on the basis of the deepest complete match to one 
of the following Pango lineages


```
Delta =       'B.1.617.2',
BA.1 =        'B.1.1.529.1'
BA.2 =        'B.1.1.529.2' 
BA.3 =        'B.1.1.529.3' 
BA.5 =        'B.1.1.529.4' 
BA.4 =        'B.1.1.529.5' 
BA.2.75 =     'B.1.1.529.2.75' 
CH.1.1 =      'B.1.1.529.2.75.3.4.1.1.1.1' 
FK.1.1 =      'B.1.1.529.2.75.3.4.1.1.1.1.17.1.1' 
XBB =         'XBB' 
XBB.1.16 =    'XBB.1.16' 
XBB.1.5 =     'XBB.1.5' 
Recombinant = 'X'
```

## 20/01/2023

* Added CH.1.1 (including all descent lineages) to tracked lineages. Prior to this
change this lineage was included in BA.2.75 (reflecting `pangolin` designation)

* Added XBF (including all descent lineages) to tracked lineages. Prior to this
change most XBF genomes were  included in BA.2 (reflecting one of the ancestors of this
recom

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
