# BP3red
# Introduction
BP3red is developed for predicting, desiging and scanning Blood-Brain Barrier Penetrating peptides (B3PPs). More information on BP3red is available from its web server http://webs.iiitd.edu.in/raghava/b3pred . This page provide information about stnadalone version of BP3red. Please read/cite following paper for complete information including algorithm behind BP3red.

Models: In this program, one model has been incorporated for predicting B3PPs. The model is trained on B3PPs and Non-B3PPs.

Modules/Jobs: This program implement three modules (job types); i) Predict: for predictin B3PPs, ii) Design: for generating all possible peptides which can penetrate blood-brain barrier, iii) Scan: Creats all possible overlapping peptides of given length (window).

Minimum USAGE: Minimum usage is "python bp3red.py -i peptide.fa" where peptide.fa is a input fasta file. This will predict the B3PPs from the sequences in the fasta format. It will use other parameters by default. It will save output in "outfile.csv" in CSV (comma seperated variables).

Full Usage: Following is complete list of all options, you may get these options by "python bp3red.py -h" 

bp3red.py [-h] -i INPUT [-o OUTPUT] [-j {1,2,3}] [-t THRESHOLD]
                  [-w {5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,27,28,29,30}]
                  [-d {1,2}]

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        Input: protein or peptide sequence in FASTA format or single sequence per line in single letter code
  -o OUTPUT, --output OUTPUT
                        Output: File for saving results by default outfile.csv
  -j {1,2,3}, --job {1,2,3}
                        Job Type: 1:predict, 2:design and 3:scan, by default 1
  -t THRESHOLD, --threshold THRESHOLD
                        Threshold: Value between 0 to 1 by default 0.11
  -w {5,6,7,..,30}, --winleng
                        Window Length: 5 to 30 (scan mode only), by default 10
  -d {1,2}, --display {1,2}
                        Display: 1: B3PPs, 2: All peptides, by default 1
Input File: It allow users to provide input in two format; i) FASTA format (standard) and ii) Simple Format. In case of simple format, file should have one one peptide sequence in a single line in single letter code (eg. peptide.seq). Please note in case of predict and design module (job) length of peptide should be upto 30 amino acids, if more than 30, program will take first 30 residues. In case of scan module, minimum length of protein/peptide sequence should be more than equal to window length (pattern), see peptide.fa . Please note program will ignore peptides having length less than 5 residues (e.g., protein.fa).

Output File: Program will save result in CSV format, in case user do not provide output file name, it will be stored in outfile.csv.

Threshold: User should provide threshold between 0 and 1.


BP3red Package Files
=======================
It contantain following files, brief descript of these files given below

INSTALLATION  	: Installations instructions

LICENSE       	: License information

README.md     	: This file provide information about this package

RF_model        : Model file required for running Model 2

bp3red.py 	: Main python program 

outfile.csv	: Example output file in csv format

peptide.fa	: Example file contain peptide sequenaces in FASTA format

peptide.seq	: Example file contain peptide sequenaces in simple format

protein.fa	: Example file contain protein sequenaces in FASTA format 

Data            : This folder contains the files required to run the in-built python scripts.

