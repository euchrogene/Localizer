# This is for EuchroGene Members.

Localizer is a machine learning-based prediction tool designed to predict the subcellular 
localization of pathogen effector proteins (and plant proteins) within plant cells, specifically 
identifying targeting to chloroplasts, mitochondria, or the nucleus.

Functions:

 - Predict Subcellular Localization: Classifies proteins based on their predicted destination 
   within the plant host cell, specifically targeting the chloroplast, mitochondrion, or nucleus.

 - Identify Targeting Signals: Detects specific sequence motifs and features, such as Nuclear 
   Localization Signals (NLS) and N-terminal transit peptides, to determine sorting destinations.

 - Handle Multiple Targets: Capable of predicting multiple potential localization sites for a 
   single protein (e.g., dual targeting to mitochondria and chloroplasts).

 - Screen High-Throughput Data: Efficiently processes large-scale datasets of secreted proteins or 
   effectors to hypothesize their potential sites of action and function within the host environment.

## To install, copy and paste the following commands in a Jupyter Terminal, and execute:

1. install the software:
```
wget https://github.com/euchrogene/EffectorP3.0/raw/refs/heads/main/Install_EffectorP3.0.sh
sudo bash Install_EffectorP3.0.sh
sudo rm Install_EffectorP3.0.sh
```

2. display installed software
```
EG_tools
```

3. download example protein sequence
```
wget https://github.com/euchrogene/EffectorP3.0/raw/refs/heads/main/Example_protein.fa
```

4. example command line
```
EffectorP3.0 -i Example_protein.fa
```

5. show help contents
```
EffectorP3.0
```

## Help contents:
```
________________________________________________________________________________________________

________________________________________________________________________________________________

Tool Type: Localizer

Localizer is a machine learning-based prediction tool designed to predict the subcellular 
localization of pathogen effector proteins (and plant proteins) within plant cells, specifically 
identifying targeting to chloroplasts, mitochondria, or the nucleus.

Functions:

 - Predict Subcellular Localization: Classifies proteins based on their predicted destination 
   within the plant host cell, specifically targeting the chloroplast, mitochondrion, or nucleus.

 - Identify Targeting Signals: Detects specific sequence motifs and features, such as Nuclear 
   Localization Signals (NLS) and N-terminal transit peptides, to determine sorting destinations.

 - Handle Multiple Targets: Capable of predicting multiple potential localization sites for a 
   single protein (e.g., dual targeting to mitochondria and chloroplasts).

 - Screen High-Throughput Data: Efficiently processes large-scale datasets of secreted proteins or 
   effectors to hypothesize their potential sites of action and function within the host environment.

If you find any bugs, please email: bioinformatics@euchrogene.com

________________________________________________________________________________________________

You can run this software by modifying the following example:

Localizer -i test_prot.fa -o output_directory -E effector_fasta.fa -N non-effector_fasta.fa

# General syntax
Localizer -i <input_fasta> -o <output_directory> -e

# Example: Running in Effector mode (recommended for fungal effectors)
Localizer -i predicted_effectors.fasta -o results_dir -e

# Example: Running in Plant mode (for host proteins)
Localizer -i arabidopsis_proteins.fasta -o results_dir -p
________________________________________________________________________________________________

Usage;

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# LOCALIZER :: predicting subcellular localization of plant and eukaryotic effector proteins
# LOCALIZER 1.0.5 (June 2020); http://localizer.csiro.au/
# Copyright (C) 2016-2017 Jana Sperschneider, CSIRO.
# Freely distributed under the GNU General Public License (GPLv3).
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
    
Usage for LOCALIZER: 
python LOCALIZER.py [-options] -i <input_file>


required option:
    -p      : Run in plant mode. This means LOCALIZER will search for transit peptides starting at the first amino acid.
  OR
    -e      : Run in effector mode. This means LOCALIZER will search for transit peptides after the signal peptide has been removed.

other options in effector mode:
    -M      : in effector mode, do not remove the signal peptide. Use this if you are providing mature effector sequences.
    -S <x>  : in effector mode, remove the signal peptide by deleting the first x aas (default: 20).

other options:
    -o <f>  : save a tab-separated output table (Results.txt) and proteins with predicted localizations to FASTA files in folder <f>
    -h      : show brief help on version and usage

______________________________________________________________________________________________
```


# Citation

## EffectorP 3.0
Sperschneider J, Dodds P. EffectorP 3.0: prediction of apoplastic and cytoplasmic effectors in fungi and oomycetes. Mol Plant Microbe Interact. 2021. doi: 10.1094/MPMI-08-21-0201-R
