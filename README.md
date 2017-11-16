ms1searchpy - a proteomics search engine for LC-MS1 spectra
---------------------------------------------------------------

A description of the algorithm can be found in:

MS/MS-Free Protein Identification in Complex Mixtures Using Multiple Enzymes with Complementary Specificity

M.V. Ivanov et al., Journal of Proteome Research, 2017, DOI:10.1021/acs.jproteome.7b00365

---------------------------------------------------------------

For those who want to simply test ms1searchpy without any installation, there is a BETA web-interface on http://176.100.242.58:8890
Login - guest, password - test.

---------------------------------------------------------------
The .tsv (or mzML) and .fasta files are required for basic operation of the script.
tsv file is tab-separated text file with peptide features generated by Dinosaur software (J.Teleman et al., "Dinosaur: A Refined Open-Source Peptide MS Feature Detector", JPR 2016) from mzML file. This file can be generated by any other software for peak-picking and must contain columns 'massCalib', 'rtApex', 'charge' and 'nIsotopes' columns.
For a сonvenient usage, mzML files can be used directly and the script will run an attached version of Dinosaur (installed Java is required).  
For an efficient usage of retention time, user can install and use ELUDE prediction algorithm (-elude path_to_elude_binary should be used in parameters).

Algorithm can be run with following command (works with Python2.7):

    python search.py path_to_MZML -d path_to_fasta

    OR

    python search.py path_to_peptideFeatures -d path_to_fasta

Alternatively, "ms1searchpy" command can be used instead of "python search.py" when package was installed using setup.py .

The script output contains files: all identified proteins (filename_proteins_full.csv), filtered proteins (filename_proteins.csv), all matched peptide match fingerprints (filename_PFMs.csv).

To combine results of MS1 searches use the following command:

    python combine.py results_1_proteins_full.csv ... results_n_proteins_full.csv

Dependencies
------------

- pyteomics
- numpy
- scipy
- sklearn
- pandas
- matplotlib
- seaborn

Links
-----

- BitBucket repo & issue tracker: https://bitbucket.org/markmipt/ms1searchpy
- Mailing list: pyteomics@googlegroups.com, markmipt@gmail.com

- Dinosaur repo: https://github.com/fickludd/dinosaur