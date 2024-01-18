 # Illuminating Dark Chemical Matter using the Cell Painting Assay

Axel Pahl, Jie Liu, Sohan Patil, Soheila Rezaei Adariani, Beate Schölermann, Jens Warmers, Jana Bonowski, Sandra Koska. Yasemin Akbulut, Carina Seitz, Sonja Sievers, Slava Ziegler*, Herbert Waldmann*

This repository contains the datasets for the manuscript titled above.


## dcm_pub.tsv

Dataset with the full morphological profiles of the 549 DCM compounds that were tested twice in the Cell Painting assay (`Run` `1` and `2`, 1098 entries in total). Compounds that showed an `Induction` >= 10 in the first measurement (`Run` `1`) where submitted to a repeat measurement (`Run` `2`).

### Columns
* `Run`: First or second measurement of the compound
* `Compound_Id`: Structure identifier
* `Well_Id`: Unique identifier of a measurement in the dataset
* `Induction`: Cell painting induction value
* `Rel_Cell_Count`: Cell count in percent, relative to DMSO controls
* `Toxic`: Whether the compound is toxic (`Rel_Cell_Count` < 50) or not at the tested concentration
* `Cluster_High`: The biological cluster with the highest similarity to this measurement, using subprofile analysis
* `Cluster_Sim`: The biosimilarity value to this cluster, in percent
* `Cluster_*`: Individual biosimilarity to the given biological cluster, using subprofile analysis, in percent
* `Median_*`: The 579 individual Cell painting feature values (Z-scores)
* `Chiral`: Chiral flag for the structure
* `Smiles`: SMILES encoding of the structure


## rep_act_no_cluster_run2.tsv

Dataset of 182 active compounds (Induction >= 5.0) from `Run` `2` for which no similar biological cluster was found.

### Columns
* `Run`: First or second measurement of the compound. Always `2` in this dataset, since only data from `Run` `2` is shown.
* `Compound_Id`: Structure identifier
* `Well_Id`: Unique identifier of a measurement in the dataset
* `Induction`: Cell painting induction value
* `Rel_Cell_Count`: Cell count in percent, relative to DMSO controls
* `Toxic`: Whether the compound is toxic (`Rel_Cell_Count` < 50) or not at the tested concentration
* `Cluster_High`: The biological cluster with the highest similarity to this measurement, using subprofile analysis
* `Cluster_Sim`: The biosimilarity value to this cluster, in percent
* `Cluster_*`: Individual biosimilarity to the given biological cluster, using subprofile analysis, in percent
* `Chiral`: Chiral flag for the structure
* `Smiles`: SMILES encoding of the structure
* `Median_*`: The 579 individual Cell painting feature values (Z-scores)


## rep_act_sim_refs.tsv

Dataset with the 10 most biosimilar reference compounds (down to a biosimilarity of 65%) for 176 out of the 182 compounds for which no biological cluster could be found (previous dataset). For 6 DCM compounds, no similar reference compounds were found (next dataset).

### Columns
* `Well_Id`: Unique identifier of a measurement in the dataset
* `Induction`: Cell painting induction value
* `Rel_Cell_Count`: Cell count in percent, relative to DMSO controls
* `Compound_Id`: Structure identifier of the tested DCM compound
* `Ref_Id`: `Well_Id` of the reference compound measurement
* `RefCpd_Id`: Structure identifier of the reference compound
* `Similarity`: Biosimilarity of the DCM compound to the reference compound's morphological profile
* `Induction_Ref`: Induction of the reference compound measurement
* `Conc_uM_Ref`: Assay concentration of the reference compound, in µM
* `Rel_Cell_Count_Ref`: Cell count of the reference compound measurement in percent, relative to DMSO controls
* `Trivial_Name_Ref`: Trivial name of the reference compound, if known
* `Known_Act_Ref`: Annotated activity of the reference compound, if known
* `Chiral_Ref`: Chiral flag for the structure of the reference compound
* `Smiles_Ref`: SMILES encoding of the reference compound's structure


## rep_act_no_refs.tsv

Dataset with 6 out of the 182 DCM compounds for which no biological cluster was found. For these 6, also no similar reference compounds could be found.

### Columns
* `Well_Id`: Unique identifier of a measurement in the dataset
* `Compound_Id`: Structure identifier
* `Induction`: Cell painting induction value
* `Rel_Cell_Count`: Cell count in percent, relative to DMSO controls
* `Chiral`: Chiral flag for the structure
* `Smiles`: SMILES encoding of the structure
* `Median_*`: The 579 individual Cell painting feature values (Z-scores)


## cluster_representatives.tsv

Representative compounds for the 13 biological clusters, one for each cluster.  
For each cluster, the measurement which is closest to the geometric center of the UMAP plot formed by all the measurements that define the cluster was chosen as representative.  
Please refer to the [Subprofile repo](https://github.com/mpimp-comas/2022_pahl_ziegler_subprofiles) (DOI: [10.5281/zenodo.10513621](https://doi.org/10.5281/zenodo.10513621)) for a list of cluster-defining compounds and measurements.

### Columns
* `Well_Id`: Unique identifier of a measurement in the dataset
* `Compound_Id`: Structure identifier
* `Supplier_Id`: The internal identifier of the compound supplier
* `Conc_uM`: Assay concentration of the compound in µM
* `Induction`: Cell painting induction value
* `Rel_Cell_Count`: Cell count in percent, relative to DMSO controls
* `Toxic`: Whether the compound is toxic (`Rel_Cell_Count` < 50) or not at the tested concentration
* `Cluster_High`: The biological cluster with the highest similarity to this measurement, using subprofile analysis
* `Cluster_Sim`: The biosimilarity value to this cluster, in percent
* `Cluster_*`: Individual biosimilarity to the given biological cluster, using subprofile analysis, in percent
* `Median_*`: The 579 individual Cell painting feature values (Z-scores)
* `Chiral`: Chiral flag for the structure
* `Smiles`: SMILES encoding of the structure
