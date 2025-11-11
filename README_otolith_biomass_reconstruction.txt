This README.txt file was generated on 2025-11-10 by Erin Dillon.

########## GENERAL INFORMATION ##########

Dataset Title: “Data from: Fossil otolith assemblages reveal millennial-scale changes in reef fish biomass and trophic structure across the Isthmus of Panama”

Author Information: 
Name: Erin Dillon
Institution: Smithsonian Tropical Research Institute
Address: Balboa, 0843, Republic of Panamá
Email: dillone@si.edu

Dates of Data Collection: 2012 – 2025

Geographic Location: Caribbean Panama (Bocas del Toro) and Pacific Panama (Gulf of Panama) 

Funding Sources:
US National Science Foundation
Smithsonian Institution
Save Our Seas Foundation
Selin, Payne, and Bytnar Families


########## SHARING/ACCESS INFORMATION ##########

This dataset is supplement to: Dillon et al. (2025) Fossil otolith assemblages reveal millennial-scale changes in reef fish biomass and trophic structure across the Isthmus of Panama. 
Philosophical Transactions B. https://doi.org/10.1098/rstb.2024.0419.

Scripts for data analysis are available at: https://github.com/erinmdillon/cross-isthmian-otolith-biomass-reconstruction

Dataset citation: Dillon et al. (2025), Data from: Fossil otolith assemblages reveal millennial-scale changes in reef fish biomass and trophic structure across the Isthmus of Panama, Zenodo, Dataset.


########## DATA & FILE OVERVIEW ##########

This project includes the following 16 csv files:

1) bchron_age_depth.csv: age-depth model outputs (from `BChron` package) from reef matrix cores collected in Pacific Panama

2) sampling_intervals_pacific.csv: reef matrix core sampling intervals to map age-depth model outputs onto our labeling system

3) oto_abund.csv: otolith counts in each sample

4) dd_abund.csv: dermal denticle counts in each sample

5) oto_family.csv: family-level otolith classifications

6) carib_oto_meas_r1.csv: otolith measurements from Caribbean Panama, dataset 1/3

7) carib_oto_meas_r2.csv: otolith measurements from Caribbean Panama, dataset 2/3

8) carib_oto_meas_r3.csv: otolith measurements from Caribbean Panama, dataset 3/3

9) pacific_oto_meas.csv: otolith measurements from Pacific Panama

10) oto_reference_collection_main.csv: otolith and fish measurements from our in-house reference collection

11) oto_reference_collection_lutjanus.csv: otolith and fish measurements from additional Lutjanus collected in the Atlantic (https://doi.org/10.1111/jai.13744)

12) aforo_morphometrics.csv: otolith and fish measurements downloaded from the AFORO database (source: http://aforo.cmima.csic.es/)

13) carib_fish_functions.csv: family-level trait data for Caribbean fish

14) pacific_fish_functions.csv: family-level trait data for Pacific fish

15) species_list_caribbean_swecoregion.csv: fish species list for Caribbean Panama (source: Robertson & Van Tassell 2023, "Shorefishes of the Greater Caribbean: online information system")

16) species_list_pacific_panama.csv: fish species list for Pacific Panama (source: Robertson & Allen 2024, "Shorefishes of the Tropical Eastern Pacific: online information system")


Additionally, two datasets downloaded within the scripts using the `rfishbase` package are archived:

17) lwr_fishbase_2025: fish length-weight coefficients downloaded from FishBase (June 2025)

18) taxa_data_fishbase_2025.csv: fish taxonomy downloaded from FishBase (June 2025)


########## METHODOLOGICAL INFORMATION ##########

This analysis uses fish otoliths preserved in modern and mid-Holocene reef sediments collected from Caribbean and Pacific Panama to reconstruct millennial-scale changes in fish community structure and per-capita biomass. Sample collection details are available in Dillon et al. (2025).

To run the otolith abundance and compositional analysis, use the script `cross-isthmian-otolith-abundance-final.Rmd` which compares otolith abundances between time periods and regions, calculates relative abundances, and plots an NMDS of otolith assemblage composition.

To run the biomass reconstruction analysis, use the script `cross-isthmian-otolith-size-final.Rmd` which applies allometric power models (built using a fish reference collection, the AFORO database, and FishBase) to reconstruct fish total length and per-capita biomass from otolith length or width.

To run the sensitivity analysis, use the script `cross-isthmian-otolith-sensitivity.Rmd` which explores how power model uncertainty affects the reconstructions of fish total length and per-capita biomass. 


########## DATA-SPECIFIC INFORMATION ##########

Data that are missing or not applicable are indicated with a period (".") or "NA"

1) bchron_age_depth.csv: age-depth model outputs (from `BChron` package) from reef matrix cores collected in Pacific Panama
(630 obs. of 18 variables)
a. X: row counter
b. region: collection region (Gulf of Panama)
c. date_locality: collection locality
d. unique: unique core interval code, in the format collector-year-site-core-depth, where the depth is the midpoint
e. sample: core code, using the same format
f. depth: depth (position) in the core, in cm from the core top (note that these are the midpoints of each sampling interval)
g. interval_no: interval number in each core, where the top is 1
h. min: lower bound of 95% credible interval, in years BP
i. median: median predicted year, in years BP
j. predicted_age_BP: mean predicted year, in years BP
k. max: upper bound of 95% credible interval, in years BP
l. predicted_age_AD_BC: mean predicted year, in BC/BCE
m. perc_2.5: 2.5% quantile of estimated number of years in the sampling interval based on the sedimentation rate
n. perc_25: 25% quantile of estimated number of years in the sampling interval based on the sedimentation rate
o. perc_50: 50% quantile (median) of estimated number of years in the sampling interval based on the sedimentation rate
p. perc_75: 75% quantile of estimated number of years in the sampling interval based on the sedimentation rate
q. perc_97.5: 97.5% quantile of estimated number of years in the sampling interval based on the sedimentation rate
r. time_uncert: difference between 75% and 25% quantiles of estimated number of years in the sampling interval


2) sampling_intervals_pacific.csv: reef matrix core sampling intervals to map age-depth model outputs onto our labeling system
(630 obs. of 10 variables)
a. region: collection region (Gulf of Panama)
b. date_locality: collection locality
c. unique: unique core interval code, in the format collector-year-site-core-depth, where the depth is the midpoint
d. sample: core code, using the same format
e. depth: depth (position) in the core, in cm from the core top (note that these are the midpoints of each sampling interval)
f. depth_upper: upper depth of sampling interval, in cm
g. depth_lower: lower depth of sampling interval, in cm
h. thickness: thickness of sampling interval, in cm (most are 5cm)
i. thick.not.5: binary yes/no to keep track of samples for which the thickness is not 5cm
j. sampling_unique: unique core interval code (our labeling system), in the format collector-year-site-core-depth, where the depth is `depth_lower`


3) oto_abund.csv: otolith counts in each sample
(620 obs. of 14 variables)
a. basin: basin (Caribbean or Pacific)
b. region: collection region (Bocas del Toro or Gulf of Panama)
c. sample: sample, either corresponding to a collection locality in the Caribbean (collector-year-site) or core in the Pacific (collector-year-site-core)
d. depth: depth (position) in the core, in cm from the core top (applies to core samples only)
e. unique: unique sample code, either in format collector-year-site-sample (Caribbean) or collector-year-site-core-depth (Pacific) 
f. site_name: collection locality
g. type: sample type (modern_bulk, Holocene_bulk, or core)
h. num_yrs_est_bulks: estimated temporal resolution of bulk samples (Caribbean only, see dates reported in Dillon et al. 2021 https://doi.org/10.1073/pnas.2017735118)
i. total_oto_count: number of otoliths
j. sed_weight_whole_sample_kg: weight of sediment in the whole sample, in kg
k. sed_weight_500_kg: weight of sediment in just the >500kg fraction picked for otoliths, in kg
l. group: group number (within a site or core)
m. group_name: pooled sample group name, in format sample_group
n. age_ref: age group (modern or pre_exp)


4) dd_abund.csv: dermal denticle counts in each sample
(163 obs. of 9 variables)
a. basin: basin (Caribbean or Pacific)
b. region: collection region (Bocas del Toro or Gulf of Panama)
c. site_name: collection locality
d. sample: sample, either corresponding to a collection locality in the Caribbean (collector-year-site) or core in the Pacific (collector-year-site-core)
e. depth: depth (position) in the core, in cm from the core top (applies to core samples only)
f. unique: unique sample code, either in format collector-year-site-sample (Caribbean) or collector-year-site-core-depth (Pacific)
g. type: sample type (modern_bulk, Holocene_bulk, or core)
h. total_dd_count: number of denticles
i. sed_weight_kg: weight of sediment in the >106 to >500kg fraction picked for denticles, in kg 


5) oto_family.csv: family-level otolith classifications
(1824 obs. of 12 variables)
a. basin: basin (Caribbean or Pacific)
b. region: collection region (Bocas del Toro or Gulf of Panama)
c. site_name: collection locality
d. sample: sample, either corresponding to a collection locality in the Caribbean (collector-year-site) or core in the Pacific (collector-year-site-core)
e. depth: depth (position) in the core, in cm from the core top (applies to core samples only)
f. unique: unique sample code, either in format collector-year-site-sample (Caribbean) or collector-year-site-core-depth (Pacific)
g. type: sample type (modern_bulk, Holocene_bulk, or core)b.
h. family: fish family name
i. family_count: number of otoliths classified to that family per sample
j. oto_count_total: total number of otoliths per sample
k. sed_weight_whole_sample_kg: weight of sediment in the whole sample, in kg
l. sed_weight_500_kg: weight of sediment in just the >500kg fraction picked for otoliths, in kg


6) carib_oto_meas_r1.csv: otolith measurements from Caribbean Panama, dataset 1/3
(2897 obs. of 9 variables)
a. Family: fish family name
b. MajorAxisLength: otolith length, mm*100
c. MinorAxisLength: otolith width, mm*100
d. Sample: unique sample code, in format collector-year-site-sample
e. Oto length (mm): otolith length, in mm
f. Oto length (um): otolith length, in um
g. Type age: age group (Sub Recent, Holocene)
h. Region: collection region (Bocas)
i. Locality: collection locality


7) carib_oto_meas_r2.csv: otolith measurements from Caribbean Panama, dataset 2/3
(3029 obs. of 10 variables)
a. Sample: unique sample code, in format collector-year-site-sample
b. Type age: age group (Sub Recent, Holocene)
c. Region: collection region (Bocas)
d. Locality: collection locality
e. Family: fish family name
f. genus: fish genus name (if available)
g. MajorAxisLength: otolith length, mm*100
h. MinorAxisLength: otolith width, mm*100
i. oto_length_mm: otolith length, in mm
j. oto_length_um: otolith length, in um


8) carib_oto_meas_r3.csv: otolith measurements from Caribbean Panama, dataset 3/3
(1032 obs. of 10 variables)
a. ocean: basin (Caribbean)
b. region: collection region (Bocas del Toro)
c. site_name: collection locality
d. sample: unique sample code, in format collector-year-site-sample 
e. age_group: age group, corresponding to `type age` (modern_bulk, Holocene_bulk)
f. otolith: otolith identifier
g. length_um: otolith length, in um
h. width_um: otolith width, in um
i. family: fish family name


9) pacific_oto_meas.csv: otolith measurements from Pacific Panama
(1207 obs. of 11 variables)
a. basin: basin (Pacific)
b. region: collection region (Gulf of Panama)
c. site_name: collection locality
d. sample: core code, in the format collector-year-site-core
e. depth: depth (position) in the core, in cm from the core top
f. unique: unique core interval code, in the format collector-year-site-core-depth
g. age_group: age group (modern or pre_exp)
h. otolith: otolith identifier 
i. length_um: otolith length, in um
j. width_um: otolith width, in um
k. family: fish family name


10) oto_reference_collection_main.csv: otolith and fish measurements from our in-house reference collection
(1802 obs. of 22 variables)
a. Collection_Number: unique identifier, in format collection-family-number
b. Year of collection: collection date
c. Age: sample type (all relevant samples are recent)
d. Ocean: basin
e. Region: collection region
f. Locality: collection locality
g. Order: order name
h. Family: family name
i. genus: genus name
j. cf. genus: if cf., otherwise blank
k. species: species name
l. subspecies: subspecies name, if applicable, otherwise blank
m. cf. species: if cf., otherwise blank
n. Complete_name: complete scientific name of fish (binomial nomenclature)
o. total_length_cm: total length of fish, in cm
p. standard_length_cm: standard length of fish, in cm
q. number_of_otoliths: number of otoliths in collection
r. left otolith length mm: length of left otolith, in mm
s. right otolith length mm: length of right otolith, in mm
t. Author_species: species reference
u. Collector: name of collector
v. Compiler: name of data compiler


11) oto_reference_collection_lutjanus.csv: otolith and fish measurements from additional Lutjanus collected in the Atlantic (https://doi.org/10.1111/jai.13744)
(132 obs. of 22 variables)
a. Collection_Number: unique identifier
b. Order: order name
c. Family: family name
d. genus: genus name
e. species: species name
f. Complete_name: complete scientific name of fish (binomial nomenclature)
g. Ocean: basin
h. Site: collection region
i. Locality: NA
j. standard_length_mm: standard length of fish, in mm 
k. total_length_mm: total length of fish, in mm
l. standard_length_cm: standard length of fish, in cm
m. total_length_cm: total length of fish, in cm
n. mass_g: fish mass, in g
o. Otolith_length_mm: length of right otolith, in mm
p. right otolith length mm: length of right otolith, in mm (duplicate)
q. right_Otolith_width_mm, width of right otolith, in mm
r. right_Otolith_mass_g: mass of right otolith, in g
s. Collection: data reference
t. Collector: name of collector
u. Compiler: name of data compiler


12) aforo_morphometrics.csv: otolith and fish measurements downloaded from the AFORO database (source: http://aforo.cmima.csic.es/)
(3501 obs. of 11 variables)
a. family: family name
b. inst_code: institutional code
c. fish_length: fish length, in mm
d. length_type: length type, e.g. SL (standard length) or TL (total length)
e. area: otolith area, in mm^2
f. perimeter: otolith perimeter, in mm
g. otolith_length: length of right otolith, in mm
h. otolith_width: width of right otolith, in mm
i. aspect_ratio: otolith width / otolith length
j. otolith_rel_length: calculated as 100*(otolith length/fish length)
k. otolith_rel_size: calculated as 1000*(otolith area/fish length^2)
										

13) carib_fish_functions.csv: family-level trait data for Caribbean fish
(109 obs. of 12 variables)
a. in_holocene_study: found in Holocene or modern reef sediments
b. Family: family name
c. Feeding: feeding mode (herbivore, planktivore, omnivore_carnivore, piscivore) [sources: Shorefishes of the Greater Caribbean: online information system; cross-checked with FishBase]
d. Piscivore: binary Yes/No if piscivorous [sources: Shorefishes of the Greater Caribbean: online information system; cross-checked with FishBase]
e. Habit: position in water column [sources: Shorefishes of the Greater Caribbean: online information system; cross-checked with FishBase]
f. Cryptobenthic: binary Cryptobenthic/Not cryptobenthic [sources: Brandl et al. 2018 (https://doi.org/10.1111/brv.12423) and Goatley and Brandl 2017 (https://doi.org/10.1016/j.cub.2017.03.051)] 
g. Gross_habitat: broad habitat type (marine, freshwater, estuarine)
h. harvested_in_sitio_drago: binary Yes/No if present in middens in Bocas del Toro from Wake et al. 2013 (https://doi.org/10.5343/bms.2012.1066) and/or Martin 2015 (https://escholarship.org/uc/item/5gj2w070)
i. prey_of_harvested_fishes: binary Yes/No if considered a common prey item of larger fishes and sharks that are consumed by humans past and present (Randall 1977, https://www.aoml.noaa.gov/general/lib/CREWS/Cleo/PuertoRico/prpdfs/randall-habits.pdf); see O'Dea et al. 2025 (https://doi.org/10.1073/pnas.2503986122)
j. Order: order name
k. Class: class name
l. Reef_associated: binary Yes/No if reef-associated [sources: Shorefishes of the Greater Caribbean: online information system & FishBase]
											

14) pacific_fish_functions.csv: family-level trait data for Pacific fish
(111 obs. of 14 variables)
a. in_holocene_study: found in Holocene or modern reef sediments
b. Family: family name
c. Feeding: feeding mode (herbivore, planktivore, omnivore_carnivore, piscivore) [sources: Shorefishes of the Tropical Eastern Pacific: online information system; cross-checked with FishBase]
d. Piscivore: binary Yes/No if piscivorous [sources: Shorefishes of the Tropical Eastern Pacific: online information system; cross-checked with FishBase]
e. Habit: position in water column [sources: Shorefishes of the Tropical Eastern Pacific: online information system; cross-checked with FishBase]
f. Reef_associated: binary Yes/No if reef-associated [sources: Shorefishes of the Tropical Eastern Pacific: online information system & FishBase] 
g. Cryptobenthic: binary Cryptobenthic/Not cryptobenthic [sources: Brandl et al. 2018 (https://doi.org/10.1111/brv.12423) and Goatley and Brandl 2017 (https://doi.org/10.1016/j.cub.2017.03.051)]
h. Gross_habitat: broad habitat type (marine, freshwater, estuarine)
i. harvested_archaeo: binary Yes/No if present in middens in Pacific Panama, data compiled in Cybulski et al. 2025 (https://doi.org/10.1098/rstb.2024.0042)
j. harvested_modern: binary Yes/No if present in modern catch records, data compiled by Harper et al. 2014 Marine Fisheries Review and Sea Around Us (https://www.seaaroundus.org/data/#/eez/952?chart=catch-chart&dimension=taxon&measure=tonnage&limit=10; https://www.seaaroundus.org/data/#/eez/952/exploited-organisms)
k. harvested_combined: binary Yes/No if found either in archaeological middens (column i) or modern catch records (column j)
l. prey_of_harvested_fishes: if considered a common prey item of larger fishes and sharks that are consumed by humans past and present (Randall 1977, https://www.aoml.noaa.gov/general/lib/CREWS/Cleo/PuertoRico/prpdfs/randall-habits.pdf)
m. Order: order name
n. Class: class name


15) species_list_caribbean_swecoregion.csv: fish species list for Caribbean Panama (source: Robertson & Van Tassell 2023, "Shorefishes of the Greater Caribbean: online information system")
(1156 obs. of 1 variable)
a. species_name: scientific name (genus species)


16) species_list_pacific_panama.csv: fish species list for Pacific Panama (source: Robertson & Allen 2024, "Shorefishes of the Tropical Eastern Pacific: online information system")
(1036 obs. of 1 variable)
a. species_name: scientific name (genus species)


17) lwr_fishbase_2025: fish length-weight coefficients downloaded from FishBase (June 2025)
(1128 obs. of 6 variables)
a. Family: family name
b. Species: scientific name (genus species)
c. Type: type of length (TL = total length)
d. Locality: collection locality
e. a: coefficient `a` in length-weight power model W=aL^b (units: cm-g)
f. b: coefficient `b` in length-weight power model W=aL^b (units: cm-g)


18) taxa_data_fishbase_2025.csv: fish taxonomy downloaded from FishBase (June 2025)
(35731 obs. of 8 variables)
a. SpecCode: species code, see FishBase
b. Species: species name
c. Genus: genus name
d. Subfamily: subfamily name
e. Family: family name
f. Order: order name
g. Class: class name
h. SuperClass: super class name
