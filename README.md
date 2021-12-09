# blobtools

https://blobtools.readme.io/docs/my-first-blobplot

## creating hits file

https://blobtools.readme.io/docs/taxonomy-file

### download db

`wget "ftp://ftp.ncbi.nlm.nih.gov/blast/db/nt.??.tar.gz"`

### extract files

`for file in *.gz
do
tar -zxvpf "$file"
rm "$file"
done`

### blast

`blastn -task megablast -db ../nt_db/nt -query /mnt/md0/piper/LH-Assembly/redundans/hc1neg_redundans/hc1negred/hc1neg_gapcloser.1.1.fa -outfmt '6 qseqid staxids bitscore std' -max_target_seqs 1 -max_hsps 1 -num_threads 16 -out test5blasthc1neg_blobtools.out -evalue 1e-25`

## blobtools create db

Generic:

`./blobtools create \
 -i example/assembly.fna \
 -b example/mapping_1.bam \
 -t example/blast.out \
 -o example/my_first_blobplot`
 
My example:

`python /mnt/md0/piper/LH-Assembly/blobtools/blobtools/lib/create.py \
 -i /mnt/md0/piper/LH-Assembly/redundans/hc1neg_redundans/hc1negred/hc1neg_gapcloser.1.1.fa \
 -b /mnt/md0/piper/LH-Assembly/referee/bwa/hc1neg-mapped-hd.bam \
 -t /mnt/md0/piper/LH-Assembly/blobtools/hits_generation/testhc1neg/test5blasthc1neg_blobtools.out \
 -o test_hc1neg_blobplot`
 
