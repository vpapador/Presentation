# Presentation
## A communal catalogue reveals Earth’s multiscale microbial diversity: soil metanalysis
## Περίληψη
Περιλαμβάνει:
- Samples από εκατοντάδες ερευνητές- μέρους του Earth Microbiome Project. Όλα τα πρωτόκολλα ήταν συντονισμένα και έγινε χρήση ακριβών αλληλουχιών (ASVs) αντί για OTUs (clustered operational taxonomic units)
- environment type, location information, host taxonomy (if relevant), and physicochemical measurements (supp.table 2) 
- environment types , geographies , and chemistries
- bacterial and archaeal components

## Σχεδιασμός
### Αλληλουχίες για στατιστική ανάλυση:
- Χρησιμοποίησαν Deblur algorithm and trimmed tag sequences to 90 bp για να συμπεριλάβουν και παλαιότερες μελέτες.
- Για να κάνουν κανονικοποίηση, έκαναν rarefaction σε διάφορα depths, και κράτησαν τα 5000 reads.
- Όταν χρησιμοποίησαν OTUs και Silva και έκαναν σύγκριση με GreenGenes και Silva είδαν ότι το ~45% της γνωστής reference diversity βρέθηκε στα δείγματα. Όταν έκαναν σύγκριση τα ASVs με τις βάσεις δεδομένων είδαν ότι χάνεται το 1/3 της πληροφορίας. Έτσι αποφάσισαν να δουλέψουν με tag sequences.
- Κρατήθηκαν μόνο tag sequences που εμφανίζονται σε τουλάχιστον 25 δείγματα.

### Samples filtering για στατιστική ανάλυση
- Κρατήθηκαν μόνο εκείνα τα samples που είχαν τουλάχιστον 1000 reads και στους 3 πίνακες (silva, gg, deblur90) και τα controls έχουν αποκλειστεί → Αυτό είναι το qc filtered dataset
- subsets with equal representation across environments (EMPO level 3): 10,000, 5,000, 2,000 samples (nested)
- Αφού έκαναν τα subsets, όρισαν επιπλέον filtering: ≥5,000 reads in Deblur 90-bp table & ≥10,000 reads in Greengenes and SILVA OTU tables.
- Για την beta diversity χρησιμοποίησαν 2,000 subset.

## Alpha & Beta diversity
- observed_otus → number of unique tag sequences (ASVs)
- Shannon → Shannon diversity index (richness + evenness)
- Chao1 → estimator of total taxa including rare ASVs
- Faith’s PD → phylogenetic diversity using the Greengenes insertion tree
- UniFrac → beta phylogenetic diversity
- Για pcoa χρησιμοποίησαν QIIME 1.9.1 (όπως και για την πλειοψηφία των αναλύσεων)

## Αποτελέσματα
### Περιβαλλοντική εξειδίκευση μικροβίων

- Τα tag sequences / ASVs (ακριβείς 16S αλληλουχίες) εμφανίζουν υψηλή περιβαλλοντική εξειδίκευση.

- Οι περισσότερες αλληλουχίες εντοπίζονται σε ένα ή λίγα περιβάλλοντα (χαμηλό Shannon entropy).

- Αντίθετα, σε υψηλότερα ταξινομικά επίπεδα (π.χ. γένος, οικογένεια):
οι μικροοργανισμοί είναι πιο ομοιόμορφα κατανεμημένοι σε διαφορετικά περιβάλλοντα (υψηλό entropy).

- Το entropy μειώνεται σταδιακά όσο αυξάνει η φυλογενετική ανάλυση.

- Στα άκρα του φυλογενετικού δέντρου (ακριβείς αλληλουχίες) παρατηρείται απότομη πτώση entropy.

*Συμπέρασμα:*
Η περιβαλλοντική εξειδίκευση αποτυπώνεται καλύτερα στο επίπεδο μεμονωμένων 16S αλληλουχιών (ASVs) και όχι στο επίπεδο OTUs (97% similarity).

### Nestedness vs Turnover στη β-ποικιλότητα
- Αν κυριαρχεί το turnover → διαφορετικές κοινότητες έχουν μοναδικά taxa.
- Αν κυριαρχεί το nestedness → κοινότητες με μικρότερη ποικιλότητα αποτελούν υποσύνολα πιο πλούσιων κοινοτήτων.

*Αποτελέσματα:*
- Οι μικροβιακές κοινότητες είναι σημαντικά nested.
- Κοινότητες χαμηλής ποικιλότητας περιέχουν κυρίως taxa που υπάρχουν και σε κοινότητες υψηλής ποικιλότητας.
- Το μοτίβο παραμένει ακόμη και μετά την αφαίρεση των πολύ κοινών taxa.
- Το nestedness είναι πιο εμφανές σε υψηλότερα ταξινομικά επίπεδα.

### Σχέση γεωγραφικού πλάτους - βιοποικιλότητας
*Το EMP έδειξε ότι για free-living μικρόβια χωρίς ξενιστή:*
- η ποικιλότητα αυξάνεται σε χαμηλά γεωγραφικά πλάτη
- το μοτίβο εμφανίζεται τόσο εντός όσο και μεταξύ μελετών.

### Επίδραση φυσικοχημικών παραμέτρων
pH
- Η μικροβιακή ποικιλότητα είναι μέγιστη κοντά στο ουδέτερο pH (~7).
- Μειώνεται σε πιο όξινες ή πιο αλκαλικές συνθήκες.
- Το μοτίβο επιβεβαιώθηκε στο EMP για soil και aquatic free-living μικρόβια.

Θερμοκρασία
- Στο EMP η μέγιστη ποικιλότητα παρατηρήθηκε σε σχετικά χαμηλές θερμοκρασίες (~10 °C).

### Ελεύθερα vs host-associated μικρόβια
Οι host-associated κοινότητες έχουν:
μικρότερο richness από τις free-living κοινότητες.

Εξαίρεση:
η ριζόσφαιρα φυτών, η οποία μοιάζει με soil communities σε richness και σύσταση.

Υπάρχει έντονη διαφοροποίηση σύστασης μεταξύ:
- αλατούχων (saline) και
- μη αλατούχων (non-saline) περιβαλλόντων.

### ACN (Average Community Copy Number)
*Το ACN εκφράζει τον μέσο αριθμό αντιγράφων του 16S rRNA gene ανά γονιδίωμα σε μια κοινότητα.*

Οικολογική σημασία:
Υψηλό ACN → γρήγορη ανάπτυξη → copiotrophic στρατηγική
Χαμηλό ACN → αργή ανάπτυξη → oligotrophic στρατηγική

Free-living και plant-associated κοινότητες:
- ACN ≈ 2.2

Animal-associated κοινότητες:
- ACN ≈ 3.4

## Επεξεργασία δεδομένων 
### Sample metadata
#### emp_qiime_mapping_qc_filtered_20170912
Από τα δεδομένα του paper στο zenodo κατέβασα το αρχείο *emp_qiime_mapping_qc_filtered_20170912* και το άνοιξα στην R
```
R
emp_qiime_mapping_qc_filtered_20170912 <- read.delim(file.choose(), header = TRUE, sep = "\t", quote = "", stringsAsFactors = FALSE, fill = TRUE, comment.char = "")
head(emp_qiime_mapping_qc_filtered_20170912, 1)
```
Περιέχει πληροφορίες για τα samples που έχουν περάσει φιλτράρισμα. Το αρχείο emp_qiime_mapping_release1_20170912 είναι πριν το φιλτράρισμα, ενώ τα αρχεία emp_qiime_mapping_subset_10k_20170912, emp_qiime_mapping_subset_5k_20170912 και emp_qiime_mapping_subset_2k_20170912 είναι τα υποσύνολα που έχουν δημιουργήσει. Παρακάτω ακολουθεί το δικό μου φιλτράρισμα.

#### Samples filtering emp_qiime_mapping_qc_filtered_20170912
Από την στιγμή που δουλεύω με soil data χρησιμοποιώ ως φίλτρα τα:
- env_material == "soil",
- envo_biome_1 == "terrestrial biome",
- empo_1 == "Free-living",
- empo_3 == "Soil (non-saline)"

```
R
library(dplyr)

filtered_df <- emp_qiime_mapping_qc_filtered_20170912 %>%
  filter(sample_scientific_name %in% c(
      "soil metagenome",
      "ecological metagenomes",
      "permafrost metagenome",
      "metagenomes"
    ),
    env_material == "soil",
    envo_biome_1 == "terrestrial biome",
    empo_1 == "Free-living",
    empo_3 == "Soil (non-saline)"
  )
library(writexl)
write_xlsx(filtered_df, "filtered_df.xlsx")

```
Αποθηκεύω τα αποτελέσματα και κάνω επεξεργασία στο excel

#### Ακολουθεί φιλτράρισμα δεδομένων στο Excel

- anthropogenetic: εξαιρώ τα croplands και τα βοσκοτόπια
- desert: αφαίρεσα τα polar γιατί ήταν oil contaminated soil
- forest: εξαιρώ extreme temperature, oil contaminated soil και oil palm plantation(βιβλιογραφία)
- grassland: αφαίρεσα το forest soil
- shrubland: δεν αφαίρεσα
- tundra: αφαίρεσα bog, permafrost, forest soil, peatland, dry lake, clay soil

| biome           | studies | samples |
| --------------- | ------- | ------- |
| anthropogenetic | 3       | 843     |
| desert          | 3       | 25      |
| forest          | 13      | 375     |
| grassland       | 5       | 287     |
| shrubland       | 4       | 270     |
| tundra          | 5       | 245     |

Βλέπω ότι έχω αναμοιομορφία samples/biome αλλά και studies/samples που μπορεί να οδηγήσει σε bias. Έτσι, αποθηκεύω και ακολουθώ επιπλέον επεξεργασία όμοια με το paper.

#### Filtering με βάση τα observation reads
Κάνω αντιγραφή επικόλληση τα samples που έχω επιλέξει από το excel και έπειτα τα απομονώνω από το μεγάλο αρχείο που είχα φτιάξει πριν με όλα τα soil samples

```
R
soil_metadata_filtered<-read.table("clipboard", sep="," , header=TRUE, dec=".")
head(soil_metadata_filtered)

emp_filtered <- emp_qiime_mapping_qc_filtered_20170912[  emp_qiime_mapping_qc_filtered_20170912$X.SampleID %in% soil_metadata_filtered$X.SampleID,]

View(emp_filtered)
```
Έπειτα, φιλτράρω με βάση τα reads και τα thresholds των συγγραφέων δημιουργώντας 3 datasets

```
R
library(dplyr)

metadata <- emp_filtered

minCounts <- 1000

filtered_metadata <- metadata %>%
  filter(
    observations_closed_ref_greengenes >= minCounts,
    observations_closed_ref_silva >= minCounts,
    observations_open_ref_greengenes >= minCounts,
    observations_deblur_90bp >= minCounts,
    empo_1 != "Control",
    !is.na(empo_0),
    !is.na(empo_1),
    !is.na(empo_2),
    !is.na(empo_3)
  )

minCountsReference <- 10000
minCountsDeblur <- 5000

subset_metadata <- metadata %>%
  filter(
    observations_closed_ref_greengenes >= minCountsReference,
    observations_closed_ref_silva >= minCountsReference,
    observations_open_ref_greengenes >= minCountsReference,
    observations_deblur_90bp >= minCountsDeblur,
    empo_1 != "Control",
    !is.na(empo_0),
    !is.na(empo_1),
    !is.na(empo_2),
    !is.na(empo_3)
  )

emp_metadata <- metadata %>%
  filter(
    !is.na(sequences_split_libraries),
    sequences_split_libraries != 0
  )

nrow(metadata)
nrow(filtered_metadata)
nrow(subset_metadata)
nrow(emp_metadata)
```

Έπειτα φτιάχνω subsets των samples ώστε να έχω ισοκατανεμημένο αριθμό samples και studies στα envo_biome_2. Αποφασίζω να δημιουργήσω 3 subsets στα 500, 1000 και 1500 samples

```
R
library(dplyr)

# setSizes μπορεί να είναι όποια θέλεις
setSizes <- c(500, 1000, 1500, 2044)
setSizes <- sort(pmin(setSizes, nrow(subset_metadata)))

subsets <- list()

for (i in seq_along(setSizes)) {
  setSize <- setSizes[i]
  subsets[[as.character(setSize)]] <- c()
  
  if (i == 1) {
    unusedMetadata <- subset_metadata
  } else {
    subsets[[as.character(setSize)]] <- subsets[[as.character(setSizes[i-1])]]
    unusedMetadata <- subset_metadata %>%
      filter(!X.SampleID %in% subsets[[as.character(setSizes[i-1])]])
  }
  
  envo_groups <- unusedMetadata %>% group_by(envo_biome_2) %>% group_split()
  envo_seen <- 0
  
  for (grp in envo_groups) {
    remaining_slots <- setSize - length(subsets[[as.character(setSize)]])
    remaining_groups <- length(envo_groups) - envo_seen
    quota <- remaining_slots / remaining_groups
    
    if (nrow(grp) <= quota) {
      toAdd <- grp$X.SampleID
    } else {
      toAdd <- c()
      study_groups <- grp %>% group_by(study_id) %>% group_split()
      study_seen <- 0
      for (sg in study_groups) {
        study_quota <- ceiling((quota - length(toAdd)) / (length(study_groups) - study_seen))
        if (nrow(sg) <= study_quota) {
          toAdd <- c(toAdd, sg$X.SampleID)
        } else {
          toAdd <- c(toAdd, sample(sg$X.SampleID, study_quota))
        }
        study_seen <- study_seen + 1
      }
    }
    
    subsets[[as.character(setSize)]] <- c(subsets[[as.character(setSize)]], toAdd)
    envo_seen <- envo_seen + 1
  }
}

# Έλεγχος: πόσα samples έχει κάθε subset
sapply(subsets, length)
```

Έπειτα ελέγχω πόσα samples από κάθε biome έχω:
```
R
for (size in names(subsets)) {
  cat("\nSubset", size, "\n")
  subset_df <- subset_metadata %>% filter(X.SampleID %in% subsets[[size]])
  print(table(subset_df$envo_biome_2))
}
```
Στο τέλος το αποτέλεσμα που έχω είναι κάτι τέτοιο:
| Subset | Anthropogenic terrestrial biome | Desert biome | Forest biome | Grassland biome | Shrubland biome | Tundra biome |
| ------ | ------------------------------- | ------------ | ------------ | --------------- | --------------- | ------------ |
| 500    | 84                              | 25           | 98           | 98              | 88              | 107          |
| 1000   | 184                             | 25           | 198          | 149             | 213             | 223          |
| 1500   | 274                             | 25           | 265          | 266             | 270             | 243          |


αυτοί είχαν setSizes = [1000, 2000, 5000, 10000]

Από αυτά, αποφασίζω να κρατήσω το subset των 500 για να είναι πιο balanced. Αυτοί δούλεψαν απλά με τα QC filtered, δηλαδή με τα αποτελέσματα του προηγούμενου κώδικα (subset_metadata). Μετά για prevalence distributions χρησιμοποιήσαν τα subsets των 2000. Ωστόσο, δούλεψαν με envo και ήταν πιο καλά αντιπροσωπευμένα. Εγώ αποφασίζω να δουλέψω με τα 500. Ωστόσο, αυτοί στο prevalence distributions δούλεψαν και με 30 samples από κάθε study. Samples από studies με μικρότερο από αυτόν τον αριθμό απορρίπτονταν. Εγώ για αρχή δεν το κάνω αυτό, μετά θα δω.
