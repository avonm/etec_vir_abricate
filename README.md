# etec_vir_abricate

The file sequences contains the same virulence genes as in teher etec_vir_master.fasta. However, the headers are formatted so it can be used to run abricate. 
The blast database files were generated running:
$ makeblastdb -in sequences -title etec_toxins -dbtype nucl -hash_index

Download all files and place in a directory called db/.

Run abricate:
$ bsub.py 1 log1_abricate abricate --datadir lustre/scratch118/infgen/team216/avm/abricate/db --db etec_toxins ERR1010188.contigs_velvet.fa

If you run abricate on multiple files summarise the output files to tab delimited file:
$ bsub.py 1 log_abricate_summary abricate --summary ./*.out > summary_etec_vir.tab
