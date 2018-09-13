

* [Install](https://github.com/xingshaocheng/architect-awesome/blob/master/README.md#Install)

* [Manual](https://github.com/xingshaocheng/architect-awesome/blob/master/README.md#Manual)

* [Release History](https://github.com/xingshaocheng/architect-awesome/blob/master/README.md#Release History)


`bed_anno_methy` help you to get annotation for genomic region based on 450K annotation information and calculate their methylation based on 450K methylation matrix.

* __Contact__: wangxinyuhs@126.com

![workflow](https://github.com/methylation/toolkits/blob/master/imgs/bed_anno_methy.jpg "foo")

### Install
* bed_anno_methy can be used directly after decompressing. 
* you could change the permission in Linux, then you can use `bed_anno_methy` to see the manual or just use `perl bed_anno_methy`.
```
chmod 755 bed_anno_methy
```


### Manual

* annotation and calculate mean methylation for each region in `dmrs.bed`. `dmrs.bed` has header.
```
bed_anno_methy -r dmrs.bed -rh -ri DMR -g GPL13534_HumanMethylation450_15017482_v.1.1.csv.gz -m UCEC_450K_matrix_sort.txt -o DMR 
```

* annotation and calculate mean methylation for each region in `UCSC_CGI.bed`. Regions which length less than 200 or cg probes less than 5 are removed; region_identifier is CGI1,CGI2... 
```
bed_anno_methy -r UCSC_CGI.bed -ri CGI -g GPL13534_HumanMethylation450_15017482_v.1.1.csv.gz -lc 200 -cc 5 -m TCGA-LGG.gz -o LGG_CGI
```

### Release History
#### v1.1.1 2018/9/13
* Rename filtered annotation file and add region identifier at first column.
* Setting default params: length_cutoff , cg_count_cutoff to 1.

#### v1.1.0 2018/4/20
* Add parameters: --region_header, --length_cutoff, --cg_count_cutoff, --region_identifier
* Support .gz format for methy & gpl file.

#### v1.0.0 2018/4/19
* First version.