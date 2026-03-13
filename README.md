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
