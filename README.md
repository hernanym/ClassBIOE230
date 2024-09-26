# ClassBIOE230 - Assignment 3
Repository for Class Assignments

### Go to NCBI Dataset website 
https://www.ncbi.nlm.nih.gov/datasets/genome/?taxon=2&release_year=1980:2001

Using the interface for PowerShell (MobaXTerm), I dropped the files and unzipped 

    $ unzip ncbi_dataset.zip
### Code for the Smallest and Largest Genome 

    $ pwd 
    $ ls 
    $ cd ncbi_dataset  # goes into ncbi_dataset
    $ ls      # opens this file, you should see "data"
    $ ls data   # opens data, so you can see inside 
    $ cd data   # goes into data 
    ### Should look like [username@login-r data] command

### Command for Smallest Genome
    $ tail -n+2 data_summary.tsv | cut -f 1,11 | sort -t$'\t' -n -k2 | head -n 1 | cut -f 2 
### Output:
    1042519
### Command for Largest Genome
    $ tail -n+2 data_summary.tsv | cut -f 1,11 | sort -t$'\t' -n -k2 | tail -n 1 | cut -f 2 
### Output:
    4033464
### Go back to home using command cd
### Command to Find the number of genomes that contain at least two “c” in species name: 
    $ cut -f3 ncbi_dataset.tsv | grep -io "c.*c" | uniq | wc -l
### Output: 
    7
### One line of code to find genomes with two "c" and exclude "coccus"
    $ cut -f3 ncbi_dataset.tsv | grep -io "c.*c" | grep -v "coccus" | uniq | wc -l
### Output: 
    5
### Go to data file: 
    $ cd ncbi_dataset
    $ cd data 
### Command to find all genome files (FASTA) larger than 3 Megabytes
    $ find . -type f -name "*.fna" -size +3M | wc -l
### Output: 
    $ 3
