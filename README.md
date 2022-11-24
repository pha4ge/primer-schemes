# Primer-schemes

A collection of primer scheme definitions for sequencing viral pathogens. A definition minimally comprises a reference sequence (`reference.fasta`), YAML metadata (`scheme.yaml`), and a Primal Scheme-like BED file describing primer sequences and their positions in reference coordinates (`primer.bed`). Each scheme is assigned an identifier consisting of the scheme family and version, e.g. `artic-v4.1`, `midnight-v2`. Checksums of primer and reference sequence composition are generated at build time and added to `scheme.yaml`.

Use [Primaschema](https://github.com/pha4ge/primaschema) to build primer scheme bundles from a `scheme.yaml`, `reference.fasta` and either `primer.bed` (7 column format) or `scheme.bed` (6 column format).

*The schema definition format has not been finalised and should be considered unstable until initial release. Thereafter the `schema_definition` will be incremented by any further changes.*



## Supported schemes

### SARS-CoV-2

- **`artic-v4.1`**
- **`eden-v1`** 
- **`midnight-v1`**
- **`midnight-v2`**
- **`midnight-ont-v3`**
- **`midnight-bccdc-v1`**
- **`midnight-bccdc-v2`**
- **`midnight-bccdc-v3`**
- **`midnight-bccdc-v4`**

### MPXV

- **`yale-v3`**



## Contributing

Pull requests containing new schemes or modifications to existing schemes are encouraged. We wish to make contributing new schemes as easy as possible and are working to simplifty this process.
