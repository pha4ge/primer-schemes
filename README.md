[![Tests](https://github.com/pha4ge/primer-schemes/actions/workflows/test.yml/badge.svg)](https://github.com/pha4ge/primer-schemes/actions/workflows/test.yml)

# Primer schemes 

**🚨 Migration to v1 scheme specification in progress**

A versioned and schematised community repository of tiled amplicon primer scheme definitions (created with e.g. [Primal Scheme](https://primalscheme.com)) for pathogen sequencing, made with the objective of eliminating ambiguity in scheme naming and versioning and maximising the findability, accessibility, interoperability and reusability ([FAIRness](https://www.go-fair.org/fair-principles/)) of primer scheme definitions and associated sequencing data.


## Scheme specification

A scheme definition has three components:

1.  A reference sequence ([`reference.fasta`](https://github.com/pha4ge/primer-schemes/blob/main/sars-cov-2/artic/v4.1/reference.fasta))
2.  A seven column BED file of primer sequences & positions in reference coordinates ([`primer.bed`](https://github.com/pha4ge/primer-schemes/blob/main/sars-cov-2/artic/v4.1/primer.bed))
3.  A metadata file in YAML format adhering to [this schema](https://github.com/pha4ge/primaschema/blob/main/src/primaschema/schema/info.yml) ([`info.yml`](https://github.com/pha4ge/primer-schemes/blob/main/schemes/sars-cov-2/artic/400/v4.1.0/info.yml))



## Contributing new schemes

*Coming soon*



## Tooling

The repository's companion tool [Primaschema](https://github.com/pha4ge/primaschema) is used to automatically validate schemes in this repository and create plots, as well as generate a six column scheme.bed for legacy tool compatibility. It can also be installed standalone.



## Scheme definitions

### MPXV

- `mpxv/yale/2000/v1.0.0`
- `mpxv/erasmus/2500/v1.0.0`

### NIV

- `niv/nipah/400/v1.0.0`

### SARS-CoV-2

- `sars-cov-2/eden/2500/v1.0.0`
- `sars-cov-2/midnight/1200/bccdc-v1.0.0`
- `sars-cov-2/midnight/1200/bccdc-v3.0.0`
- `sars-cov-2/midnight/1200/bccdc-v2.0.0`
- `sars-cov-2/midnight/1200/bccdc-v4.0.0`
- `sars-cov-2/midnight/1200/v2.0.0`
- `sars-cov-2/midnight/1200/v1.0.0`
- `sars-cov-2/midnight/1200/ont-v3.0.0`
- `sars-cov-2/artic/400/v3.0.0`
- `sars-cov-2/artic/400/v2.0.0`
- `sars-cov-2/artic/400/v1.0.0`
- `sars-cov-2/artic/400/v5.0.0`
- `sars-cov-2/artic/400/v4.0.0`
- `sars-cov-2/artic/400/v4.1.0`
- `sars-cov-2/artic/400/v5.3.2`
- `sars-cov-2/artic/400/v5.4.2`
- `sars-cov-2/artic/400/v5.2.0`
