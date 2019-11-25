# EBI_SRA_Downloader
The tool that allows users to efficiently fetch studies from the European Nucleotide Archive (ENA) and the Sequence Read Archive (SRA). The downloaded and generated files are sequence files, sample file and preparation files. These files are required for Qiita (https://qiita.ucsd.edu).
## Instructions
### Create a conda environment 
conda create -name ebi-sra-importer -c bioconda xmltodict lxml pandas requests sra-tools entrez-direct  
### Switch to the conda environment
source activate ebi-sra-importer  
### Download a study
#### ENA
python3 EBI_SRA_Downloader.py -ebi [ebiaccession_number]
#### SRA
python3 EBI_SRA_Downloader.py -sra [sraaccession_number]
### Optional flags
#### Customize sample file name
-sample [sample_file_name]  
e.g. python3 EBI_SRA_Downloader.py -ebi [ebiaccession_number] -sample [sample_file_name]
#### Customize preparation file name
-prep [prep_file_name]  
e.g. python3 EBI_SRA_Downloader.py -ebi [ebiaccession_number] -prep [prep_file_name]
#### Customize study file name
-study [study_file_name]  
e.g. python3 EBI_SRA_Downloader.py -ebi [ebiaccession_number] -study [study_file_name]
#### Filter out non-metagenomic samples
-all-seqs true
without setting the flag, the non-metagenomic samples will be filtered out
e.g. python3 EBI_SRA_Downloader.py -ebi [ebiaccession_number] -all-seqs true
#### Filter out non-illumina samples
-all-platform true
without setting the flag, the non-illumina samples will be filtered out
e.g. python3 EBI_SRA_Downloader.py -ebi [ebiaccession_number] -all-platform true
#### Debug mode
-debug true
with setting the flag, the downloader will NOT download massive size sequence files (fastq)
e.g. python3 EBI_SRA_Downloader.py -ebi [ebiaccession_number] -debug true
