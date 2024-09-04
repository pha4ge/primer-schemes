[![Tests](https://github.com/pha4ge/primer-schemes/actions/workflows/test.yml/badge.svg)](https://github.com/pha4ge/primer-schemes/actions/workflows/test.yml)

# Primer schemes 

**🚨 Migration to v1 scheme specification in progress**

A versioned and schematised community repository of tiled amplicon primer scheme definitions (created with e.g. [Primal Scheme](https://primalscheme.com)) for pathogen sequencing, made with the objective of eliminating ambiguity in scheme naming and versioning and maximising the findability, accessibility, interoperability and reusability ([FAIRness](https://www.go-fair.org/fair-principles/)) of primer schemes and associated sequencing data. An example of a canonical primer scheme name is `sars-cov-2/midnight/1200/v1.0.0`.

The repository includes a top-level machine readable [index](https://github.com/pha4ge/primer-schemes/blob/main/index.yml) of available primer scheme definitions.



## Scheme specification

A scheme definition has three components:

1.  A reference sequence (e.g. [`reference.fasta`](https://github.com/pha4ge/primer-schemes/blob/main/schemes/sars-cov-2/artic/400/v4.1.0/reference.fasta))
2.  A seven column Primal Scheme-like BED file of primer sequences & coordinates (e.g. [`primer.bed`](https://github.com/pha4ge/primer-schemes/blob/main/schemes/sars-cov-2/artic/400/v4.1.0/primer.bed))
3.  A metadata file in YAML format adhering to a [schema](https://github.com/pha4ge/primaschema/blob/main/src/primaschema/schema/info.yml) (e.g. [`info.yml`](https://github.com/pha4ge/primer-schemes/blob/main/schemes/sars-cov-2/artic/400/v4.1.0/info.yml))



## Tooling

The repository's companion tool [Primaschema](https://github.com/pha4ge/primaschema) is used to automatically validate schemes in this repository, create graphics and manage checksums, as well as generate a six column scheme.bed for legacy tool compatibility. It may be installed standalone using `pip install` for fetching, validating and interrogating primer schemes.



## Contributing new scheme definitions

We encourage contributions of any schemes the others might wish to use, especially if sequencing data has been or will be deposited publicly. We're working to make this process easier, but in the meantime please either follow the instructions below to send us a draft scheme, or create a pull request using GitHub if comfortable doing so.

A scheme definition comprises *i)* a reference sequence (`reference.fasta`), *ii)* a BED file of primer sequences & reference coordinates (`primer.bed`), and *iii)*, a metadata file in YAML format adhering to [this schema](https://github.com/pha4ge/primaschema/blob/main/src/primaschema/schema/info.yml), called `info.yml`. If you've created a scheme you probably already have i) and ii), and need to make `info.yml`. It's easiest to begin by modifying a copy of an existing `info.yml` [such as this one](https://github.com/pha4ge/primer-schemes/blob/main/schemes/sars-cov-2/eden/2500/v1.0.0/info.yml).

1. Check that the `organism` field in your scheme's `info.yml` references the correct pathogen. If there are no existing schemes for the target pathogen, please [open a GitHub issue](https://github.com/pha4ge/primer-schemes/issues) to request it be added.
2. Choose a scheme name and version, e.g `midnight` and `v1.0.0`. The name should not include special characters except hyphens.
    - If adding a new scheme, choose any name, preferably not referencing the organism name. 
    - If updating your existing scheme, keep the same name and update the version:
      - Versions must take the form `v{major}.{minor}.{patch}`
      - For primer changes beyond adding primers, increment the *major* version
      - If only adding primers with respect to an existing version, increment the *minor* version
      - For smaller technical changes, the *patch* version may be incremented
    - If updating a third party's existing scheme, you may propose a new scheme name with version `v1.0.0` rather than increment the existing scheme's version.
3. Complete the `name` and `version` fields inside your new scheme's `info.yml`, along with the other required fields:
    - `amplicon_size`: the approximate integer amplicon length in bp
    - `developers`: a list of developer names or organisations
4. [Open a GitHub issue](https://github.com/pha4ge/primer-schemes/issues) attaching or linking to your `reference.fasta`, `primer.bed` and `info.yml` files.
5. If you wish, you may install [primaschema](https://github.com/pha4ge/primaschema) and run `primaschema build {scheme-directory}`to validate your newly created scheme and add checksums etc. However this is not necessary.



## Scheme definitions

### MPXV

- `mpxv/yale/2000/v1.0.0`
- `mpxv/rigshospitalet/2500/v1.0.0`

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
