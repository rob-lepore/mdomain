# LB1 project

```sh
./mdomain --pfam PF00014 --min-length 50 --max-length 80 --clust-th 50 --hmm-name kunitz
```

## Flow
1. Retrieve PDB structures based on PFAM, CATH and Interpro
2. Structures are clustered using PDB representatives
3. Multiple structural alignment (USalign)
4. HMM based on the alignment (HMMER)
5. Get dataset of positive and negative from UniProt
6. Remove the positive entries corresponding to the structures used in the alignment
7. Use 60% of the records as training set and 40% as test set
8. Find optimal e-value threshold for classification using 10-fold CV on the training set
9. Evaluate performance on the test set
10. List false predictions
