```
cd /home/estudiante/TP4
```

```
mkdir /home/estudiante/TP4/reads/trimm
```

```
trimmomatic PE \
/home/estudiante/TP4/reads/MISEQ_SRR2075910_1.fastq.gz /home/estudiante/TP4/reads/MISEQ_SRR2075910_2.fastq.gz \
/home/estudiante/TP4/reads/trimm/MISEQ_SRR2075910_trim_1p.fastq.gz \
/home/estudiante/TP4/reads/trimm/MISEQ_SRR2075910_trim_1u.fastq.gz \
/home/estudiante/TP4/reads/trimm/MISEQ_SRR2075910_trim_2p.fastq.gz \
/home/estudiante/TP4/reads/trimm/MISEQ_SRR2075910_trim_2u.fastq.gz \
ILLUMINACLIP:/home/estudiante/software/Trimmomatic-0.38/adapters/TruSeq3-PE-2.fa:2:30:10 \
LEADING:20 TRAILING:20 SLIDINGWINDOW:5:20 MINLEN:50
```

```
trimmomatic SE \
/home/estudiante/TP4/reads/GA2_DRR001063_redset.fastq.gz \
/home/estudiante/TP4/reads/trimm/GA2_DRR001063_redset_trim.fastq.gz \
ILLUMINACLIP:/home/estudiante/software/Trimmomatic-0.38/adapters/TruSeq2-SE.fa:2:30:10 \
LEADING:20 TRAILING:20 SLIDINGWINDOW:5:20 MINLEN:50
```

```
zcat /home/estudiante/TP4/reads/trimm/MISEQ_SRR2075910_trim_1u.fastq.gz > /home/estudiante/TP4/reads/trimm/MISEQ_SRR2075910_trim_U.fastq; zcat /home/estudiante/TP4/reads/trimm/MISEQ_SRR2075910_trim_2u.fastq.gz >> /home/estudiante/TP4/reads/trimm/MISEQ_SRR2075910_trim_U.fastq; gzip /home/estudiante/TP4/reads/trimm/MISEQ_SRR2075910_trim_U.fastq
```