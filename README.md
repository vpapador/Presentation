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
Εδώ αντιμετώπισα μία δυσκολία. Το paper αναφέρει ότι δούλεψαν με ASVs και καταλαβαίνω ότι είναι τα Tag seq με deblur90bp. Ωστόσο, έχουν και δεδομένα από Silva και Greengenes. Εγώ πιστεύω ότι είναι το taxonomy των OTUs αυτό και όχι το taxonomy των ASVs ωστόσο δεν είμαι βέβαιη και δεν το διευκρινίζει. Από την άλλη οι αλληλουχίες fasta είναι διαφορετικές και για τα 3 .biome. Μπορώ να δουλέψω αποκλειστικά με τα tag seq έτσι και αλλιώς σε επίπεδο ~ είδους, αλλά για να δουλέψω σε μεγαλύτερες τάξεις πρέπει να λυθεί. Προσωρινά, έλυσα το πρόβλημα χρησιμοποιώντας το vsearch στο bash όπου έκανα εκ νέου taxonomy στα ASVs, απλά δεν ξέρω αν αυτό είναι σωστό δεδομένουν ότι έχω μόνο 90bp. Χρησιμοποίησα την Silva.

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


<img width="1206" height="633" alt="image" src="https://github.com/user-attachments/assets/485368c9-b9cd-4181-8937-80c4f50c4e67" />



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

<img width="1180" height="633" alt="image" src="https://github.com/user-attachments/assets/ae7cfd31-b81f-44e5-be98-78b7c0c0d228" />


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


<img width="1106" height="633" alt="image" src="https://github.com/user-attachments/assets/6a84f388-e491-4dde-81ab-164a841b8a07" />




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

<img width="821" height="687" alt="image" src="https://github.com/user-attachments/assets/cb7d4a6c-1de0-430f-82fe-341010149e2a" />





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

<img width="920" height="687" alt="image" src="https://github.com/user-attachments/assets/56884314-12f4-4c97-8664-ac02dfc6d919" />




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







