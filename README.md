# README

This repository contains supplementary digital resources, scripts, and files used in the paper Porter et al. 2023 "All boreal forest successional stages needed to maintain the full suite of biodiversity, community composition, and function following wildfire." Scientific Reports, 13: 7978.

## Digital Resources

We used some key references from the literature to produce lists of fire-associated organisms and ecological traits that can be easily imported into R for analysis.  

### Pyrophilous Taxa

See /PyrophilousTaxa/README.docx for further details.

Fire-associated bacteria (/PyrophilousTaxa/FireAssociatedBacteria_2022-03-28.xlsx, /infiles/FireBacteria.csv).

Fire-loving fungi (/PyrophilousTaxa/FireLovingFungi_2022-04-28.xlsx, /infiles/Firefungi.csv).  If you use this file please site the original sources published largely by Zak and Wicklow (1980) as well as Dix and Webster (1995). 

Fire-associated arthropods that can be used to screen datasets for pyrophilous arthropods (/PyrophilousTaxa/FireAssociatedArthropods_2022-03-18.xlsx, /infiles/FireInsects.csv).  If you use this file please site the original sources published largely by Wikars (1997) that are listed in the file.  

### Ecological Function Annotations

See /EcologicalFunctionAnnotation/README.docx for further details.

CSV file of FAPROTAX bacterial traits supplemented with additional N fixation, K and P solubilization traits by Sansupa et al. (2021) and further supplemented with additional taxa with chitinolytic capabilities (/EcologicalFunctionAnnotations/FAPROTAX_Sansupa_Puri.txt, /infiles/FAPROTAX_Sansupa_Puri.txt).  Formatted for use with FAPROTAX.

CSV file of fungal traits for rhizomorph-forming, ericoid, and fire-associated fungi.  Column names were chosen to be compatible with the FungalTraits database (/infiles/FungalTraits_RhizomorphEricoidFireAnnotations.csv).  If you use this file please cite the original sources largely from Boddy (1993) for saprotrophic rhizomorph-forming fungi,  Agerer (2006) for ectomycorrhizal rhizomorph-forming fungi, as well as Zak and Wicklow (1980) and Dix and Webster (1995) for fire-loving fungi.

CSV file of terrestrial arthropod functional feeding guilds (/infiles/EPA.csv, /infiles/Moog.csv, /infiles/Tachet.csv).  These functions were assigned based on the literature with effort made to use the same terminology used by the US EPA for functional feeding guilds in freshwater macroinvertebrates where possible to facilitate comparisons across these diverse taxa.

## Infiles

16S_results.csv  

16S_trainset18_db_taxid.txt  

BE_results.csv  

CO1_v4.0.1_mytaxon.txt  

EPA.csv  

F230_results.csv  

FireBacteria.csv  

FireFungi.csv  

FireInsects.csv  

func_table_ammended_Puri.tsv  

FungalTraits_RhizomorphEricoidFireAnnotations.csv  

ITS_results.csv  

metadata.csv  

Moog.csv  

Tachet.csv  

UNITEv8.2_v2_mytaxon.txt  

veg.csv  


## R Scripts

Use /scripts/tax_summary.R with outfiles from MetaWorks for each marker (/infiles/BE_results.csv, /infiles/F230_results.csv, /infiles/ITS_results.csv, 16S_results.csv) along with /infiles/metadata.csv to create /outfiles/tax_meta.csv used in future analyses.  

Fig 1 Experimental design.  Use /scripts/Fig1_map_wildfire.R with /infiles/metadata.csv to create /outfiles/Fig1_map.df .

Fig 2 Contrasting patterns of diversity seen for soil bacteria, fungi, and arthropods.  Use /scripts/Fig2_Biodiversity.R with /outfiles/tax_meta.csv to create /outfiles/Fig2_biodiversity.pdf .

Fig 3 Contrasting recovery patterns of soil taxa along an 85-year chronosequence following natural wildfire disturbance.  Use /scripts/Fig3_FigS1_beta_NODF.R with /outfiles/tax_meta.csv and /infiles/metadata.csv to create /outfiles/NODF.csv,  /outfiles/Fig3_NODF.pdf and /outfiles/FigS1.pdf .

Fig 4 Each stand development stage is important for maintaining gamma diversity and whole community nestedness.  Use /scripts/Fig4_Simulation.R with /outfiles/tax_meta.csv to create /outfiles/Simulation.csv and /outfiles/Fig4_Simulation.pdf .

Fig 5 Major groups vary across the post-fire chronosequence.  Use /scripts/Fig5_composition.R with /outfiles/tax_meta.csv and /infiles/func_table_ammended_Puri.tsv , /infiles/FungalTraits_RhizomorphEricoidFireAnnotations.csv , /infiles/EPA.csv, /infiles/Moog.csv , and /infiles/Tachet.csv to create /outfiles/Fig5_composition.pdf .

Table 1 Overview of site characteristics.  Use /scripts/Table1_devstage_years.R with /outfiles/tax_meta.csv with /infiles/veg.csv and /infiles/metadata.csv .

Fig S1 Fire-origin soil communities are largely distinct from one stand development stage to the next.  See above for Fig 3.

Fig S2 Fungal nestedness and specialization across stand development stages.  Use /scripts/FigS2_FigS3_Guild_turnover.R with /outfiles/tax_meta.csv and /infiles/FungalTraits_RhizomorphEricoidFireAnnotations.csv to create /outfiles/NODF_by_group.csv, /outfiles/FigS2_nestedness_specialization.pdf and /outfiles/FigS3_nestednessPlots_by_groups.pdf .

Fig S3 Nestedness patterns vary across major fungal functional and taxonomic groups.  See above for Fig S2.

Fig S4 The diversity and frequency of fire-associated fungal species is highest from fire-origin sites at the establishment stage.  Use /scripts/FigS4_TableS1_fireFungi.R with /outfiles/tax_meta.csv and UNITEv8.2_v2_mytaxon.txt with /infiles/FireFungi.csv to create /outfiles/FigS4_Firefungi_DevStage.pdf and /outfiles/TableS1_firefungi.csv .

Fig S5 Frequency of bacterial genera that may be associated with fire-origin sites.  Use /scripts/FigS5_fireBacteria.R with /outfiles/tax_meta.csv , /infiles/FireBacteria.csv and /infiles/16S_trainset18_db_taxid.txt to create FigS5_FireBacteria_DevStage.pdf .

Fig S6 Frequency of insect genera that may be associated with fire-origin sites.  Use /scripts/FigS6_fireInsects.R with /outfiles/tax_meta.csv , /infiles/FireInsects.csv and /infiles/CO1_v4.0.1_mytaxon.txt to create /outfiles/FigS6_FireInsects_DevStage.pdf .

Fig S7 Rarefaction curves plateau indicating sequencing depth was sufficient for each amplicon.  Use /scripts/FigS7_Rarefaction_2023-02-22.R with /outfiles/tax_meta.csv to create /outfiles/FigS7_rarefaction_amplicon/df .

Table S2 Stand development stage bioindicators from fire-origin sites.  Use /scripts/Q3_IndicVal_2022-03-28.R with /outfiles/tax_meta.csv to create /outfiles/TableS2_devstage_bioindicatorTaxa_fire.csv .

## References

Agerer, R. (2006). Fungal relationships and structural identity of their ectomycorrhizae. Mycological Progress, 5(2), 67–107. doi: 10.1007/s11557-006-0505-x

Boddy, L. (1993). Saprotrophic cord-forming fungi: Warfare strategies and other ecological aspects. Mycological Research, 97(6), 641–655. doi: 10.1016/S0953-7562(09)80141-X

Dix, N. J., & Webster, J. (1995). Phoenicoid Fungi. In Fungal Ecology. Dordrecht: Springer. Retrieved from https://doi.org/10.1007/978-94-011-0693-1_11

Sansupa, C., Wahdan, S. F. M., Hossen, S., Disayathanoowat, T., Wubet, T., & Purahong, W. (2021). Can We Use Functional Annotation of Prokaryotic Taxa (FAPROTAX) to Assign the Ecological Functions of Soil Bacteria? Applied Sciences, 11(2), 688. doi: 10.3390/app11020688

Wikars, L.-O. (1997). Effects of forest fire and the ecology of fire-adapted insects (Dissertation for the Degree of Doctor of Philosophy in Entomology). Uppsala University, Uppsala.

Zak, J. C., & Wicklow, D. T. (1980). Structure and composition of a post-fire ascomycete community: Role of abiotic and biotic factors. Canadian Journal of Botany, 58(17), 1915–1922. doi: 10.1139/b80-222

## Acknowledgements

I would like to acknowledge funding from the Canadian government from the Genomics Research and Development Initiative (GRDI), Metagenomics-Based Ecosystem Biomonitoring (Ecobiomics) project.

Last updated: December 20, 2023
