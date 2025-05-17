# Premade barcodes

<mark>**Note: shuffle the set before selecting elements!**</mark> This way this hopefully retains diversity across libraries - it would not be very nice if many libraries ended up using the first $x$ elements, for instance. (Not sure if having this repo in the first place is a good idea.)

This repo contains text files with pre-computed barcodes of certain length with certain distances between them.
E.g. barcodes/barcodes.12bp.hamming3.txt gives you a set of 12 bp barcodes with Hamming distance 3 between them.



## Construction of barcodes

These barcodes were generated using the library `DNABarcodes`. Note that this doesn't give you the theoretical maximum number of codes of that length at that distance - by default Conway's algorithm is used - see [this vignette](https://www.bioconductor.org/packages/devel/bioc/vignettes/DNABarcodes/inst/doc/DNABarcodes.html) for how the package works.
```R
library("DNABarcodes")

mySet <- create.dnabarcodes(12, dist=3)
write.table(data.frame(mySet),
            file = "barcodes/barcodes.12bp.hamming3.txt", sep="\t",
            col.names = FALSE, row.names = FALSE, quote = FALSE)
```
