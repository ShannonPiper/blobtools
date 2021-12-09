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
