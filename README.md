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

### Tag Sequences- Rarefaction
#### Πρόβλημα που πρέπει να λυθεί- δεύτερη γνώμη
Εδώ αντιμετώπισα μία δυσκολία. Το paper αναφέρει ότι δούλεψαν με ASVs και καταλαβαίνω ότι είναι τα Tag seq με deblur90bp. Ωστόσο, έχουν και δεδομένα από Silva και Greengenes. Εγώ πιστεύω ότι είναι το taxonomy των OTUs αυτό και όχι το taxonomy των ASVs ωστόσο δεν είμαι βέβαιη και δεν το διευκρινίζει. Παρακάτω ωστόσο δίνει ASVs taxonomy - tradng cards using green genes database με το taxonomy των deblur90bp αλλά μόνο στα 2000 subset. Από αυτά τα 2000, εντοπίζονται 20/500 δικά μου άρα αυτό είναι ένα πρόβλημα. Έκανα μια αναγνώριση και αντιστοίχιση των αλληλουχιών μου και υπάρχουν ταξινομημένες ~40000 από τις ~70000 αλληλουχίες. Έτσι, αποφάσισα να λύσω το πρόβλημα χρησιμοποιώντας vsearch και silva database. Αναγνώρισα επιπλέον ~20.000 αλληλουχίες και έτσι έχω περίπου 60000 ταξινομημένες. Ωστόσο, δεν ξέρω αν μπορώ όντως να κάνω vsearch σε 90 μόνο βάσεις, δεν ξέρω αν είναι σωστό.

#### Sequencing depths- phyloseq
Για να μπορέσω να προχωρήσω σε στατιστική ανάλυση, πρέπει να κάνω κανονικοποίηση. Επιλέγω να δημιουργήσω phyloseq object και να δουλέψω στην R. Έχω αποθηκεύσει το subset_500.csv και πάω στην Python. Από εκεί θα απομονώσω από το αρχικό .biom deblur_90bp μόνο τα 500 samples

```
Python
!pip install biom-format
#dont forget to restart the kernel

#ανεβάζω τα δεδομένα μου
import os
os.chdir(r"C:\Users\User\Documents\emp_data_from_zenodo\Python_analysis")

from biom import load_table
table = load_table("emp_deblur_90bp.release1.biom")

#τα μετατρέπω σε dataframe
table.shape
emp_deblur_90bp_release1 = table.to_dataframe()

#Και στην συνέχεια φορτώνω τα 500 samples που έχω επιλέξει
import pandas as pd
# Φόρτωμα του CSV
subset_500= pd.read_csv("subset_500.csv", sep=";")

#Απομονώνω από το emp_deblur_90bp μόνο τα samples που με ενδιαφέρουν και στην συνέχεια αφαιρώ αυτά που έχουν 0 reads across the samples
subset_500=emp_deblur_90bp_release1.loc[:, emp_deblur_90bp_release1.columns.isin(subset_500["X.SampleID"])]
import numpy as np
mask_h = np.any(subset_500.values, axis=1)
subset_500= subset_500.loc[mask_h]
subset_500.shape

subset_500.to_csv("subset_final.csv", index=False, sep=";")
```
 Το πρώτο βήμα που έκανα, είναι να μετατρέψω το φιλτραρισμένο .csv file σε .biom
 ```
R
library("phyloseq")
library("ggplot2")
library("permute")
library("vegan")
library("biomformat")
library(tidyr)
library(dplyr)
#περιέχει τα 500 samples, και τις αλληλουχίες tag που εντοπίζονται μόνο στα 500

subset_final<- read.table(file.choose(), header = TRUE, sep = "\t")
dim(subset_final)
head(subset_final,1)

#μετατροπή σε .biom για να κάνω phyloseq_object
subset_final_1<-subset_final
otu_ids <- subset_final_1[,1]
counts <- subset_final_1[,-1]
counts <- data.frame(lapply(counts, as.numeric))
rownames(counts) <- otu_ids
mat <- as.matrix(counts)
dim(mat)
head(rownames(mat))
otu_table <- make_biom(data = mat)
otu_table
write_biom(otu_table, "otu_table.biom")
```

To phyloseq object απαιτεί ακόμα τις αλληλουχίες .fasta όμως πρέπει να έχει ίδιο μέγεθος με το .biom. Οπότε πάω στην python

```
Python
ids = set()

# αυτό που κάνω είναι να διαβάσω το subset αρχείο και να προσθέτω την πρώτη στήλη στα ids (η πρώτη στήλη είναι αυτοί με τα tag)
with open("subset_final.txt", "r") as f:
    for line in f:
        first_col = line.strip().split()[0]   # πρώτη στήλη
        ids.add(first_col)

filtered = []

# στην συνέχεια διαβάζω το fasta και κρατάω μόνο τα headers+seq αν το header ταυτίζεται με τα ids
with open("emp.90.min25.deblur.seq.fasta", "r") as f:
    keep = False
    for line in f:
        if line.startswith(">"):
            header = line[1:].strip()  # αφαιρούμε το >
            keep = header in ids
        if keep:
            filtered.append(line)



# δημιουργώ ένα νέο αρχείο fasta
with open("filtered_sequences.fasta", "w") as out:
    out.writelines(filtered)
```
Τώρα έχω όλα τα αρχεία που χρειάζομαι. Τα βάζω όλα μαζί locally στον φάκελο, αλλάζω το wd και έπειτα:

```
R
ps = import_biom("tables.biom", treefilename="tree_rooted.tre", refseqfilename="otus.fasta")
ps
```

Το επόμενο βήμα είναι να δημιουργήσω ένα αρχείο metadata ώστε να αντιστοιχίσω τα samples σε biomes.

```
R
library("readr")
subset_500 <- read_tsv("subset_500.txt", quote = "\"")
str(subset_500)
colnames(subset_500)

subset_meta <- subset_500[, c("X.SampleID", "envo_biome_2", "study_id","latitude_deg", "longitude_deg", "elevation_m")]
head(subset_meta)
subset_meta$X.SampleID <- paste0("X", subset_meta$X.SampleID)

subset_meta_1<-subset_meta
subset_meta_1 <- data.frame(subset_meta_1)
rownames(subset_meta_1) <- subset_meta_1$X.SampleID
head(subset_meta_1)
subset_meta_1 <- subset_meta_1[, c("envo_biome_2", "study_id", "latitude_deg", "longitude_deg", "elevation_m")]
colnames(subset_meta_1)[colnames(subset_meta_1) == "envo_biome_2"] <- "Biome"
sample_data(ps) <- sample_data(subset_meta_1)
ps

ps1<-ps
str(sample_data(ps1))
ps1
sample_data(ps1)$latitude_deg  <- as.numeric(gsub(",", ".", sample_data(ps1)$latitude_deg))
str(sample_data(ps1))
```
Τώρα μπορώ να κάνω rarefaction. Επιλέγω να κάνω στο 90% των reads του μικρότερου σε reads samples.

```
R
#rarecurve(t(mat), step=50, cex=0.5) #κάνω έλεγχο
#επειδή είναι πολύ μεγάλο επιλέγω τυχαία 50 samples
set.seed(1)
idx <- sample(1:nrow(t(mat)), 50)

rarecurve(t(mat)[idx, ], step = 50, cex = 0.5)
ps.rarefied = rarefy_even_depth(ps1, rngseed=1, sample.size=0.9*min(sample_sums(ps1)), replace=F)
#αφαιρέθηκαν 27260 tag sequences από τα 98786
sample_sums(ps.rarefied)
```





![alt text](https://github.com/vpapador/Presentation/blob/a810e5aa5ee79285fce12885f67838dbd91925fb/rarefaction_curve.png)






Ταυτόχρονα κάνω prunned το φυλογενετικό δέντρο ώστε να περιέχει μόνο τις rarified αλληλουχίες


```
R
phy_tree(ps.rarefied) <- prune_taxa(taxa_names(ps.rarefied), phy_tree(ps.rarefied))
head(phy_tree(ps.rarefied)$tip.label, 10)
length(phy_tree(ps.rarefied)$tip.label)
setdiff(taxa_names(ps.rarefied), phy_tree(ps.rarefied)$tip.label)
```

### Alpha Diversity
#### Τι έκαναν αυτοί:

- μετατροπή numeric predictors σε quartiles
- φίλτρο κατηγοριών (<0.3% samples removed)
- Mann–Whitney pairwise tests
- pooled p-values ανά predictor
- Benjamini–Hochberg correction
- effect size (Cohen's d)

Δεν θα χρησιμοποιήσω το Phyloseq γιατί δεν υποστηρίζει το FaithPD. Αντίθετα θα υπολογίσω τους δείκτες Chao1, Shannon, FaithPD, Observed ξεχωριστικά και θα φτιάξω ένα dataframe ώστε να είναι πάντα διαθέσιμο με το όνομα alpha_meta όπου θα έχω και περιβαλλοντικές μεταβλητές+ study_id διαθέσιμα για στατιστική ανάλυση.

```
R
library("ape")
library("nlme")
library("picante")
otu_tab <- t(otu_table(ps.rarefied))
tree <- phy_tree(ps.rarefied)
pd_results <- pd(otu_tab, tree, include.root = TRUE)
head(pd_results)
alpha <- estimate_richness(ps.rarefied, measures=c("Observed","Shannon","Chao1"))
head(alpha)
alpha$FaithPD <- pd_results$PD
library(ggplot2)
library(gridExtra)
alpha_subset <- alpha
alpha_subset$envo_biome_2 <- sample_data(ps.rarefied)$Biome

# Δημιουργούμε τα plots
p1 <- ggplot(alpha_subset,
             aes(x = reorder(envo_biome_2, Shannon, median),
                 y = Shannon)) +
  geom_boxplot() +
  theme_bw() +
  coord_flip() +
  ggtitle("Shannon")

p2 <- ggplot(alpha_subset,
             aes(x = reorder(envo_biome_2, Chao1, median),
                 y = Chao1)) +
  geom_boxplot() +
  theme_bw() +
  coord_flip() +
  ggtitle("Chao1")

p3 <- ggplot(alpha_subset,
             aes(x = reorder(envo_biome_2, FaithPD, median),
                 y = FaithPD)) +
  geom_boxplot() +
  theme_bw() +
  coord_flip() +
  ggtitle("Faith PD")

p4 <- ggplot(alpha_subset,
             aes(x = reorder(envo_biome_2, Observed, median),
                 y = Observed)) +
  geom_boxplot() +
  theme_bw() +
  coord_flip() +
  ggtitle("Observed OTUs")

#Άλφα ποικιλότητα metadata
meta <- as(sample_data(ps.rarefied), "data.frame")
alpha$SampleID <- rownames(alpha)
alpha_meta <- merge(alpha, meta, by.x="SampleID", by.y="row.names")
head(alpha_meta)
alpha_meta$FaithPD <- alpha_meta$FaithPD.x
alpha_meta <- alpha_meta %>% select(-FaithPD.x, -FaithPD.y)

```


<img width="1106" height="633" alt="image" src="https://github.com/user-attachments/assets/87382e81-7c33-4663-b83c-88be0c711302" />

![alt text](https://github.com/vpapador/Presentation/blob/a810e5aa5ee79285fce12885f67838dbd91925fb/alpha_div.png)


### Beta diversity
#### Τι έκαναν αυτοί:

- υπολογισμός UniFrac distances
- PERMANOVA για κάθε predictor
- mdFDR correction
- effect size για significant predictors

Εγώ χρησιμοποίησα έτοιμο το Phyloseq για να υπολογίσω unifrac weighted+unweighted

```
R
wunifrac_dist = distance(ps.rarefied, method="unifrac", weighted=F)
ordination = ordinate(ps.rarefied, method="PCoA", distance=wunifrac_dist)
plot_ordination(ps.rarefied, ordination, color="Biome") + theme(aspect.ratio=1)

```




![alt text](https://github.com/vpapador/Presentation/blob/a810e5aa5ee79285fce12885f67838dbd91925fb/pca_unweighted.png)




Μπορώ να κάνω boxplots

```
R
# Μετατρέπουμε το dist object σε matrix
wunifrac_mat <- as.matrix(wunifrac_dist)

# Φτιάχνουμε ένα data.frame με όλα τα ζεύγη
wunifrac_df <- as.data.frame(as.table(wunifrac_mat))
colnames(wunifrac_df) <- c("Sample1", "Sample2", "Distance")

# Προσθέτουμε Biome info
biome_info <- data.frame(Sample = sample_names(ps.rarefied),
                         Biome = sample_data(ps.rarefied)$Biome,
                         stringsAsFactors = FALSE)

wunifrac_df <- wunifrac_df %>%
  left_join(biome_info, by = c("Sample1" = "Sample")) %>%
  rename(Biome1 = Biome) %>%
  left_join(biome_info, by = c("Sample2" = "Sample")) %>%
  rename(Biome2 = Biome)

# Επιλέγουμε μόνο τις **διασταυρώσεις εντός του ίδιου Biome** (προαιρετικό)
wunifrac_within <- wunifrac_df %>% filter(Biome1 == Biome2)


ggplot(wunifrac_within, aes(x = Biome1, y = Distance)) +
  geom_boxplot() +
  theme_bw() +
  coord_flip() +
  ylab("Unweighted UniFrac distance") +
  xlab("Biome") +
  ggtitle("Within-biome β diversity")

```



![alt text](https://github.com/vpapador/Presentation/blob/a810e5aa5ee79285fce12885f67838dbd91925fb/beta_unweighted.png)



Πρέπει να κάνω έναν έλεγχο να δω εάν τα samples εμφανίζονται μέσα στο phyloseq object με την σειρά
```
R
# Παίρνουμε τα ονόματα samples από το phyloseq object
phy_samples <- sample_names(ps.rarefied)
# Παίρνουμε τα rownames του sample_data
meta_samples <- rownames(as(sample_data(ps.rarefied), "data.frame"))
# Ελέγχουμε αν είναι ίδια και με την ίδια σειρά
all(phy_samples == meta_samples)
```

<pre>
> all(phy_samples == meta_samples)
[1] TRUE
</pre>



Μετά μπορώ να κάνω ανάλυση permanova και να δω εάν τα Biomes διαφέρουν σημαντικά στη σύνθεση των κοινοτήτων τους
```
R
adonis2(wunifrac_dist~sample_data(ps.rarefied)$Biome)
```

<pre> 
> adonis2(wunifrac_dist~sample_data(ps.rarefied)$Biome)   
Permutation test for adonis under reduced model
Permutation: free
Number of permutations: 999

adonis2(formula = wunifrac_dist ~ sample_data(ps.rarefied)$Biome)
          Df SumOfSqs      R2      F Pr(>F)    
Model      5   15.319 0.08448 9.1163  0.001 ***
Residual 494  166.023 0.91552                  
Total    499  181.342 1.00000                  
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1  
</pre>

Τι επιπλέον κάνουν αυτοί στο paper
- Κάνουν pairwise comparisons για κάθε κατηγορία.
- Εφαρμόζουν mdFDR για να ελέγξουν false positives σε πολλές συγκρίσεις.
- Υπολογίζουν effect size για κάθε παράγοντα.

Το ίδιο έκανα και για weighted unifraq:
```
R
wunifrac_dist_TR = distance(ps.rarefied, method="unifrac", weighted=T)
ordination_TR = ordinate(ps.rarefied, method="PCoA", distance=wunifrac_dist_TR)
plot_ordination(ps.rarefied, ordination_TR, color="Biome") + theme(aspect.ratio=1)
```





![alt text](https://github.com/vpapador/Presentation/blob/a810e5aa5ee79285fce12885f67838dbd91925fb/pca_weighted.png)




Επαναλαμβάνω την ίδια διαδικασία για να πάρω τα boxplots
```
R
# Μετατρέπουμε το dist object σε matrix
wunifrac_mat_TR <- as.matrix(wunifrac_dist_TR)

# Φτιάχνουμε ένα data.frame με όλα τα ζεύγη
wunifrac_df_TR <- as.data.frame(as.table(wunifrac_mat_TR))
colnames(wunifrac_df_TR) <- c("Sample1", "Sample2", "Distance")

# Προσθέτουμε Biome info
biome_info <- data.frame(Sample = sample_names(ps.rarefied),
                         Biome = sample_data(ps.rarefied)$Biome,
                         stringsAsFactors = FALSE)

wunifrac_df_TR <- wunifrac_df_TR %>%
  left_join(biome_info, by = c("Sample1" = "Sample")) %>%
  rename(Biome1 = Biome) %>%
  left_join(biome_info, by = c("Sample2" = "Sample")) %>%
  rename(Biome2 = Biome)

# Επιλέγουμε μόνο τις **διασταυρώσεις εντός του ίδιου Biome** (προαιρετικό)
wunifrac_within_TR <- wunifrac_df_TR %>% filter(Biome1 == Biome2)
head(wunifrac_within_TR,10)
head(wunifrac_df_TR)

ggplot(wunifrac_within_TR, aes(x = Biome1, y = Distance)) +
  geom_boxplot() +
  theme_bw() +
  coord_flip() +
  ylab("Weighted UniFrac distance") +
  xlab("Biome") +
  ggtitle("Within-biome β diversity")
```




![alt text](https://github.com/vpapador/Presentation/blob/a810e5aa5ee79285fce12885f67838dbd91925fb/beta_weighted.png)





Προχωράω σε ανάλυση PERMANOVA
```
R
# Παίρνουμε τα ονόματα samples από το phyloseq object
phy_samples <- sample_names(ps.rarefied)
# Παίρνουμε τα rownames του sample_data
meta_samples <- rownames(as(sample_data(ps.rarefied), "data.frame"))
# Ελέγχουμε αν είναι ίδια και με την ίδια σειρά
all(phy_samples == meta_samples)
#επίσης ελέγχω αν τα samples στις αποστάσεις είναι με την ίδια σειρά όπως στα meta_samples
all(labels(wunifrac_dist_TR) == meta_samples)
#και αν είναι με την ίδια σειρά με τα samples στα reads
all(labels(wunifrac_dist_TR) == rownames(sample_data(ps.rarefied)))
labels(wunifrac_dist_TR)[1:10]


adonis2(wunifrac_dist_TR~sample_data(ps.rarefied)$Biome)
adonis2(wunifrac_dist_TR~sample_data(ps.rarefied)$Biome+ sample_data(ps.rarefied)$study_id )
length(wunifrac_dist_TR)
head(wunifrac_dist_TR)
```


<pre>
> adonis2(wunifrac_dist_TR~sample_data(ps.rarefied)$Biome)
Permutation test for adonis under reduced model
Permutation: free
Number of permutations: 999

adonis2(formula = wunifrac_dist_TR ~ sample_data(ps.rarefied)$Biome)
          Df SumOfSqs      R2    F Pr(>F)    
Model      5   1.1298 0.23706 30.7  0.001 ***
Residual 494   3.6359 0.76294                
Total    499   4.7657 1.00000                
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

</pre>

Οι πίνακες για την β ποικιλότητα μπορούν να βρεθούν:
```
R
head(wunifrac_within,10)
head(wunifrac_df)
head(wunifrac_within_TR,10)
head(wunifrac_df_TR)
```

*προς το παρόν το workplace έχει σωθεί στο github.RData*

### Taxonomy

Για να κάνω το taxonomy δούλεψα σε linux και χρησιμοποίησα vsearch , το fasta file των 90bp deblur και την βάση δεδομένων SILVA.

```
bash
module load gcc/14.2.0 vsearch/2.22.1

#έλεγξα πόσα βακτήρια περιέχει
grep -c "Bacteria" SILVA_138.2_SSURef_NR99_tax_silva.fasta
#431166

#Έκανα μια επεξεργασία το header του fasta ώστε να κλείσω το κενό
sed '/^>/ s/ /|/' SILVA_138.2_SSURef_NR99_tax_silva.fasta > silva_fixed.fasta
#και έπειτα έτρεξα την εντολή
vsearch --usearch_global emp.90.min25.deblur.seq.fasta \
        --db silva_fixed.fasta \
        --id 0.97 \
        --blast6out fixed_silva1.txt \
        --strand plus --threads 4
```

Στην συνέχεια εισάγω το αρχείο που έχει προκύψει στην R. Όμως, περιέχονται όλες οι αλληλουχίες γιατί στην silva έδωσα το emp.90.min25.deblur.seq.fasta χωρίς να φιλτράρω. Επομένως πρέπει να κρατήσω τα taxonomy που αντιστοιχούν στα δικά μου samples. 
```
R
fixed_silva1<- read.table(file.choose(), header = TRUE, sep = "\t")
#κρατάω μόνο τις πρώτες 2 στήλες
fixed_silva2 <- fixed_silva1[, 1:2]
#και φιλτράρω για μεγαλύτερη ευκολία με το mat
fixed_silva2_filtered <- fixed_silva2[fixed_silva2[,1] %in% rownames(mat), ]
#μετατρέπω σε dataframe με rows
taxa_mat <- data.frame(OTU_taxonomy = fixed_silva2_filtered[,2],
                      row.names = fixed_silva2_filtered[,1],
                      stringsAsFactors = FALSE)
```
Το data frame έχει όλο το taxonomy μαζί. Δεν είμαι σίγουρη εάν τα taxa είναι με την σειρά, αλλά θα κάνω έναν πρώτο διαχωρισμό και ότι προκύψει θα το φιλτράρω αργότερα

```
R
split_tax <- strsplit(as.character(taxa_mat$OTU_taxonomy), "\\|")
accession <- sapply(split_tax, `[`, 1)
taxonomy <- sapply(split_tax, `[`, 2)
otu_mat2 <- data.frame(Accession = accession,
                       OTU_taxonomy = taxonomy,
                       row.names = rownames(taxa_mat),
                       stringsAsFactors = FALSE)


otu_df <- otu_mat2 %>%
  mutate(TagSeq = rownames(otu_mat2)) %>%
  select(TagSeq, Accession, OTU_taxonomy)

otu_df_sep <- otu_df %>%
  separate(OTU_taxonomy,
           into = c("Kingdom","Phylum","Class","Order","Family","Genus","Species"),
           sep = ";",
           fill = "right")  # γεμίζει με NA αν λείπουν επίπεδα


tax_cols <- c("Kingdom","Phylum","Class","Order","Family","Genus","Species")

# Αντικατάσταση με NA αν:
# - δεν ξεκινάει με κεφαλαίο γράμμα
# - περιέχει "-"
# - περιέχει αριθμό
otu_df_clean <- otu_df_sep %>%
  mutate(across(all_of(tax_cols), ~ ifelse(
    !grepl("^[A-Z]", .x) | grepl("-", .x) | grepl("[0-9]", .x),
    NA,
    .x
  )))

```
Τώρα έχω φτιάξει ένα taxonomy table για τα δεδομένα από το Vsearch. Εξετάζω το αρχείο με την δική τους ταξινόμηση

```
R
otu_summary.emp_deblur_90bp.subset_2k.rare_5000 <- read.delim(file.choose(), header = TRUE, sep = "\t", quote = "", stringsAsFactors = FALSE, fill = TRUE, comment.char = "")
head(otu_summary.emp_deblur_90bp.subset_2k.rare_5000)
```
Απομονώνω μόνο εκείνα τα tagseq που είναι στο phyloseq object μου
```
R
taxa_ids <- rownames(otu_table(ps.rarefied1))
head(taxa_ids)
otu_summary.filtered <- 
  otu_summary.emp_deblur_90bp.subset_2k.rare_5000[
    otu_summary.emp_deblur_90bp.subset_2k.rare_5000$sequence %in% taxa_ids,
  ]
```
Κάνω σύγκριση για το πόσες αλληλουχίες υπάρχουν ταξινομημένες από αυτές που έχω εγώ στα rarefied δεδομένα. Το αποτέλεσμα που παίρνω είναι 43069. Κάνω και σύγκριση μεταξύ των 2 πινάκων ταξινόμησης - vsearch και το δικό τους και υπάρχουν ~20000 κοινές αλληλουχίες 
```
R
dim(fixed_silva2_filtered)
head(fixed_silva2_filtered,1)
head(otu_summary.filtered,1)
View(otu_summary.filtered)
seq_summary <- otu_summary.filtered$sequence
seq_vsearch <- fixed_silva2_filtered[,1]
length(intersect(seq_summary, seq_vsearch))
```
Από περιέργεια ελέγχω πόσα από τα 500 samples μου βρίσκονται στα 2000 samples του subset τους
```
R
emp_qiime_mapping_subset_2k_20170912 <- read.delim(file.choose(), header = TRUE, sep = "\t", quote = "", stringsAsFactors = FALSE, fill = TRUE, comment.char = "") 
samples_phyloseq <- colnames(otu_table(ps.rarefied1))
samples_subset <- emp_qiime_mapping_subset_2k_20170912$X.SampleID
samples_subset <- paste0("X", samples_subset)
length(intersect(samples_phyloseq, samples_subset))
#μόνο 28 από τα 500 samples εντοπίζονται στο 2000 subset
```
Θέλω να καθαρίσω τα δεδομένα μου για να είμαι σίγουρη ότι δεν έχω κάνει κάποιο λάθος κατά το vsearch. Το κύριο λάθος που μπορεί να προέκυψε είναι να έγινε ταξινόμηση με κάποιον ευκαρυωτικό οργανισμό ενώ γνωρίζω ότι στα δείγματα έχω μόνο βακτήρια και αρχαία.
```
R
#τώρα αφαιρώ τα eukarytoa γιατί ξέρω ότι είναι σίγουρα λάθος
unique(otu_df_clean$Kingdom)
otu_df_clean_no_euk <- otu_df_clean[otu_df_clean$Kingdom != "Eukaryota", ]
dim(otu_df_clean_no_euk)
#αφαιρέθηκε μόνο ένα
unique(otu_df_clean_no_euk$Kingdom)
```
Φτιάχνω το δικό τους dataset ώστε να το ενώσω με το δικό μου
```
R
vsearch_taxo<-otu_df_clean_no_euk
#από το δικό τους κρατάω μόνο 2 στήλες
otu_subset <- otu_summary.filtered[, c("sequence", "taxonomy")]
taxonomy_split <- do.call(rbind, strsplit(as.character(otu_summary.filtered$taxonomy), "; "))

# Μετονομάζουμε τις στήλες
colnames(taxonomy_split) <- c("Kingdom", "Phylum", "Class", "Order", "Family", "Genus", "Species")

# Προσθέτουμε στο αρχικό dataframe
otu_summary_split <- cbind(otu_summary.filtered["sequence"], taxonomy_split)
otu_summary_split[] <- lapply(otu_summary_split, function(x) gsub("^[a-z]__","", x))
```

Σε αυτό το σημείο έκανα έναν έλεγχο για να δω εάν η στήλη Phylum ήταν η ίδια για τα 2 dataset για τις αλληλουχίες που είχαν κενές. Όμως, η gg βάση τουλάχιστον μέχρι τότε ακολουθούσε την παλιά ταξινόμηση οπότε τα ονόματα είχαν άλλες καταλήξεις και είχαν εντελώς αναντιστοιχία. Δεν βάζω τον κώδικα. Περνάω κατευθείαν στην επεξεργασία του δικού μου dataset ώστε να κάνω την συνένωση.
```
R
#Κάνω το vsearch σε ίδια δομή με το άλλο
colnames(vsearch_taxo)[colnames(vsearch_taxo) == "TagSeq"] <- "sequence"
vsearch_taxo <- vsearch_taxo[, !colnames(vsearch_taxo) %in% "Accession"]
# Κρατάμε όλες τις γραμμές από vsearch_taxo που δεν υπάρχουν στο otu_summary_split_subset
vsearch_only_df <- vsearch_taxo[!(vsearch_taxo$sequence %in% otu_summary_split_subset$sequence), ]

# Έλεγχος
head(vsearch_only_df)
dim(vsearch_only_df)  # πόσες γραμμές είναι μόνο στο vsearch
# Όλα τα column names που θέλουμε
cols_to_keep <- colnames(otu_summary_split)
# Βεβαιωνόμαστε ότι όλες οι στήλες υπάρχουν στο vsearch_only_df
for (col in cols_to_keep) {
  if (!(col %in% colnames(vsearch_only_df))) {
    vsearch_only_df[[col]] <- NA  # αν λείπει η στήλη, την δημιουργούμε με NA
  }
}
# Τώρα ευθυγραμμίζουμε τις στήλες με την ίδια σειρά
vsearch_only_aligned <- vsearch_only_df[, cols_to_keep]
otu_summary_complete <- rbind(otu_summary_split, vsearch_only_aligned)
# Έλεγχος
dim(otu_summary_complete)
head(otu_summary_complete)
num_unique_seqs <- length(unique(otu_summary_complete$sequence))
```
Από εδώ θα κάνω έναν έλεγχο στα Phylum, γιατί κάποια όπως είπα είναι συνώνυμα και ακολουθούν την παλιά ονοματολογία, αλλά και να αφαιρέσω τα tagseq που στην πραγματικότητα δεν έχουν ταξινομηθεί και έχουν συμπληρωθεί με ΝΑ ή σύμβολα
```
R
unique_phylum <- unique(otu_summary_complete$Phylum)
length(unique_phylum)
unique_phylum_df <- data.frame(Phylum =unique_phylum)
library(writexl)
write_xlsx(unique_phylum_df, path = "unique_phylum.xlsx")
```
Ακολουθεί φιλτράρισμα στο excel, όπου γκούγκλαρα όλα τα φύλα για να σιγουρευτώ ότι πράγματι αυτά με τις διαφορετικές καταλήξεις είναι παλιές/καινούργιες ονομασίες
```
R
#περιέχει μία Phylum στήλη
phyla<-read.table("clipboard", sep="\t", header=TRUE)
```
Τώρα, ζητάω να κρατήσω μόνο τις σωστές σειρές με τα Phylum
```
R
otu_summary_subset_phyla <- otu_summary_complete[
  otu_summary_complete$Phylum %in% phyla$Phylum,
]
```
Και πλέον μπορώ να αντικαταστήσω τα συνώνυμα
```
R
replace<-read.table("clipboard", sep="\t", header=TRUE)
idx <- match(otu_summary_subset_phyla$Phylum, replace$Phylum)
otu_summary_subset_phyla$Phylum[!is.na(idx)] <- replace$Replace[idx[!is.na(idx)]]
# βάζουμε τα sequence ως rownames
rownames(otu_summary_subset_phyla) <- otu_summary_subset_phyla$sequence
# αφαιρούμε τη στήλη sequence
otu_summary_subset_phyla$sequence <- NULL
```
Φτιάχνω phyloseq object για τα phylum
```
R
ps.rarefied2<-ps.rarefied1
ps.rarefied2
tax_table(ps.rarefied2) <- tax_table(otu_summary_subset_phyla)
ps.rarefied2 <- prune_taxa(taxa_names(ps.rarefied2) %in% rownames(otu_summary_subset_phyla), ps.rarefied2)
tax_table(ps.rarefied2) <- tax_table(as.matrix(otu_summary_subset_phyla))
```
Τώρα θέλω να φτιάξω ένα διάγραμμα αφθονιών Phyla/Biome
```
R
ps.rarefied4<-ps.rarefied2
sample_data(ps.rarefied4)$study_biome <- paste(
  sample_data(ps.rarefied4)$study_id,
  gsub(" ", "_", sample_data(ps.rarefied4)$Biome),
  sep = "_"
)
ps.study <- merge_samples(ps.rarefied4, "study_biome")
sd <- data.frame(sample_data(ps.rarefied4))
sd_unique <- sd[!duplicated(sd$study_biome), ]
rownames(sd_unique) <- sd_unique$study_biome
sample_data(ps.study) <- sample_data(sd_unique[sample_names(ps.study), ])

plot_bar(ps.study, fill = "Phylum") +
  facet_wrap(~Biome, scales = "free_x", nrow = 1)
```
Με το διάγραμμα αυτό προκύπτει αφθονία/sample σε κάθε Biome





![alt text](https://github.com/vpapador/Presentation/blob/58490712f6b20da68544311f373b474fd53a8deb/sample_biome_ab.png)





Ωστόσο, επειδή τα samples είναι 500 σκέφτηκα να τα χωρίσω ανά study
```
ps.phylum5 <- tax_glom(ps.study, taxrank = "Phylum")
# long format
df <- psmelt(ps.phylum5)  # Phylum, Abundance, Sample, sample_data
ggplot(df, aes(x = factor(study_id), y = Abundance, fill = Phylum)) +
  geom_bar(stat = "identity") +
  facet_wrap(~Biome, scales = "free_x", nrow = 1) +
  theme(axis.text.x = element_text(angle = 45, hjust = 1))
```






 ![alt text](https://github.com/vpapador/Presentation/blob/33bbe7ef4dc3c29320ad5cfaf43fe90065e8738a/%CE%95%CE%B9%CE%BA%CF%8C%CE%BD%CE%B100.png)





Και τώρα το κάνω και ανά Biome
```
R
library(phyloseq)
library(ggplot2)
library(dplyr)

ps.biome <- merge_samples(ps.rarefied2, "Biome")
sample_data(ps.biome)$Biome <- rownames(sample_data(ps.biome))
df <- psmelt(ps.biome) 
ggplot(df, aes(x = Biome, y = Abundance, fill = Phylum)) +
  geom_bar(stat = "identity") +
  theme_minimal() +
  ylab("Abundance") +
  xlab("Biome") +
  theme(axis.text.x = element_text(angle = 45, hjust = 1))
```




![alt text](https://github.com/vpapador/Presentation/blob/a8fa8adb273e2a2d8b2090b7345fd0738bc1857c/samples_biome.png)





Βρίσκω ποια ήταν τα πιο άφθονα φύλα

```
R
df_summary <- df %>%
  group_by(Biome, Phylum) %>%
  summarise(TotalAbundance = sum(Abundance))

df_summary

library(tidyr)
df_wide <- df_summary %>%
  pivot_wider(names_from = Phylum, values_from = TotalAbundance, values_fill = 0)

df_wide

top10_phyla <- df %>%
  group_by(Phylum) %>%            # Ομαδοποιούμε ανά Phylum
  summarise(TotalAbundance = sum(Abundance)) %>%  # Άθροιση όλων των Biome
  arrange(desc(TotalAbundance)) %>%  # Ταξινόμηση από τη μεγαλύτερη
  slice_head(n = 10)                 # Επιλέγουμε τα 10 πρώτα

top10_phyla
```

| Rank | Phylum            | Total Abundance |
| ---- | ----------------- | --------------- |
| 1    | Pseudomonadota    | 1,021,307       |
| 2    | Acidobacteriota   | 612,644         |
| 3    | Verrucomicrobiota | 382,436         |
| 4    | Actinomycetota    | 278,030         |
| 5    | Bacteroidota      | 263,392         |
| 6    | Bacillota         | 107,735         |
| 7    | Planctomycetota   | 93,645          |
| 8    | Chloroflexota     | 86,442          |
| 9    | Gemmatimonadota   | 83,936          |
| 10   | Cyanobacteriota   | 30,380          |


# Διορθώσεις
- Πρέπει να κάνω rarefaction σε ταξινομικό επίπεδο- επίπεδο Φύλου
- Scopus: a communal catalogue reveals earth’s multiscale microbial diversity και μετά φίλτρο στην αναζήτηση των citation "soil" και μετά επιλέγω "microbial community"
- Πρέπει να ψάξω αν η β ποικιλότητα είναι similarity ή dissimilarity
- venn diagram σε επίπεδο φύλου
- α και β ποικιλότητες σε επίπεδο φύλου
- heatmap? σε επίπεδο φύλου ιδανικά σε όλα τα samples
- ίσως όπως κάναμε τα gene expression trends κάτι παρόμοιο για τα μικρόβια για να δω συνεμφάνιση
- δίκτυα









