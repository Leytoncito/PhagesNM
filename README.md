# Supporting code for manuscript: Genomic identification and characterization of Neisseria meningitidis prophages from South America

### Phylogenetic and pangenome analysis:

The Phylogenetic analysis of the 157 genomes was carried out using the Randomized Axelerated Maximum Likelihood [(RAxML)](https://cme.h-its.org/exelixis/web/software/raxml/) software. The line of code used was the following:
```
./raxml-ng --msa all_genomes_nm --threads 8 --all --bs-trees 100 --model GTR+G+FO
```

### Identification and annotation of phages:

For the identification and annotation of phages VIBRANT was the software used
The line of code to run the analysis was the following:
```
for file in *.fas; do 
  VIBRANT_run.py -d /home/david/VIBRANT/databases/ -folder /home/david/VIBRANT/outputfolderNM/ -t 10 -i $file; 
done
```
### Reduction of phage redundancy

An analysis with [CD-HIT](https://github.com/weizhongli/cdhit/) was carried out in order to decrease phage redundancy. The line of code for the analysis was the following
```
cd-hit-est -i 157.fasta -c 0.75 -n 4 -M 13000 -T 0 -o 157clustered075.fasta
```
### Phylogenetic classification of representative sequences

### Presence-absence matrix generation by LS-BSR
