# scFiltering

#Example data set same frome
https://support.10xgenomics.com/single-cell-gene-expression/datasets/3.0.0/pbmc_1k_v2

In fact from :
http://cf.10xgenomics.com/samples/cell-exp/3.0.0/pbmc_1k_v2/pbmc_1k_v2_filtered_feature_bc_matrix.tar.gz

Where I use : cellranger mat2csv filtered_feature_bc_matrix/ filtered_feature_bc_matrix.csv

And then ome filtering to remove many genes in order to play with a small file.

cat  Desktop/filtered_feature_bc_matrix.csv  | awk '{split($0,t,/,/); print $0","t[1]'} | cut  -d "," -f2-998 > Desktop/filtered_feature_bc_matrix.csv2

 tail -n 1 Desktop/filtered_feature_bc_matrix.sorted.csv2 > Desktop/filtered_feature_bc_matrix.sorted.3000.csv2
 
 tail -n 3001 Desktop/filtered_feature_bc_matrix.sorted.csv2 | tail -n 3000 >> Desktop/filtered_feature_bc_matrix.sorted.3000.csv2
