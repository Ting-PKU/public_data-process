## 1. download sra files
```
cat sra_list|while read id;do nohup wget https://sra-pub-run-odp.s3.amazonaws.com/sra/$id/$id & done
```
## 2. transform to fastq files
```
cat sra_list|while read id;do fastq-dump -O ./ --gzip --split-3 ./$id & done
```
