# Primer-schemes

A collection of descriptions of primer schemes used for sequencing viral pathogens. A scheme minimally comprises a reference sequence (`reference.fasta`), YAML metadata (`scheme.yaml`), and a Primal Scheme-like BED file describing primer sequences and their positions in reference coordinates (`primer.bed`). Each scheme is assigned an identifier consisting of the scheme family and version, e.g. `artic-v4.1`, `midnight-v2`. A checksum of the BED file contents is generated at build time and added to `scheme.yaml`.

Use [Primaschema](https://github.com/pha4ge/primaschema) to build primer scheme bundles from a `scheme.yaml`, `reference.fasta` and either `primer.bed` (7 column format) or `scheme.bed` (6 column format).



## Supported schemes

### SARS-CoV-2

- ARTIC V4.1 **`artic-v4.1`**
- Eden V1 **`eden-v1`** 

### MPXV

- Yale V3 **`yale-v3`**



## Contributing

Pull requests containing new schemes or modifications to existing schemes are encouraged. We wish to make contributing new schemes as easy as possible and are working to simplifty this process.
