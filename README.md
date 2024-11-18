# Comparative analysis of microbial genomes on Oxford nanopore

# Tutorial

Create the `params.json` file describing your task, following the example

```
{
    "sample_files": [
     "../../scratch/2024_bshC/basecalls/barcode01.pass.cram",
     "../../scratch/2024_bshC/basecalls/barcode12.pass.cram"
    ],
    "exclude_samples": [],
    "consensus_ref_sample": "barcode01",
    "data_dir": "data/nanopore_8325",
    "medaka_model": "r1041_e82_400bps_sup_v4.2.0",
    "medaka_variant_model": "r1041_e82_400bps_sup_variant_v4.2.0",

    "ref_fa": "data/saureus/Saureus8325.fasta",
    "ref_id": "SA8325",
    "ref_gff": "data/saureus/Saureus8325.gff",
    "gene_annotation_bed": "data/saureus/Saureus8325_gene_annotations.bed"
}
```

Then run the pipeline as

```
nextflow run https://github.com/BioinfoSupport/nanopore_compare.git -params-file params.json -profile local
```

You can use a preconfigured profile for SLURM executor by

```
nextflow run https://github.com/BioinfoSupport/nanopore_compare.git -params-file params.json -profile baobab
```


## Possible parameters

## Output structure





# TODO list

* Make a simpler/correct annotate consensus vcf by qualities
* Symmetric calling on consensus
  * Potential attempt in medaka_compare project
* Liftover cases (is it needed at all?)
  * Problematic case: SNP coincides with original reference, how to represent this
