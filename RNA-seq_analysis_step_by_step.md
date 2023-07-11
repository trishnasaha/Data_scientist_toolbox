## Reference types

### depends on the available information about the species.

### quantify against a genome
![alt text](<image/Screenshot 2023-07-07 at 11.53.29 AM.jpg>)

### classify against a transcriptome
![alt text](<image/Screenshot 2023-07-07 at 11.59.58 AM.jpg>)

[mRNA-seq data analysis workflow](https://biocorecrg.github.io/RNAseq_course_2019/workflow.html)

[Informatics for RNA Sequencing: A Web Resource for Analysis on the Cloud](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1004393#sec003)

### Tools
FastQC
Trimmomatic/cutadapt
STAR / HISAT2
FeatureCount


### Raw data
NCBI -> GEO datasets -> search with GSE accession number -> Look for experimental details, samples, normalization method -> click on SRA Run Selector -> get accesion list

use the following command in filename.sh script.

```
cat SRR_Acc_List.txt | parallel fasterq-dump --split-files
```
rewrite permission with 
```
chmod 755 filename.sh
```
submit job
```
nohup bash download.sh &
```

Replace _1.fastq with _R1.fastq and _2.fastq with R2.fastq

```
for i in *_1.fastq; do mv $i ${i%_1.fastq}_R1.fastq; done

for i in *_2.fastq; do mv $i ${i%_2.fastq}_R2.fastq; done
```


### Quality control (QC) using fastqc



