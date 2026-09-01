# Primer schemes

A versioned and schematised community repository of tiled amplicon primer scheme definitions (created with e.g. [Primal Scheme](https://primalscheme.com)) for pathogen sequencing, made with the objective of eliminating ambiguity in scheme naming and versioning and maximising the findability, accessibility, interoperability and reusability ([FAIRness](https://www.go-fair.org/fair-principles/)) of primer schemes and associated sequencing data. An example of a canonical primer scheme name is `artic-sars-cov-2/400/v4.1.0`.

The repository includes a top-level machine readable [index](https://github.com/pha4ge/primer-schemes/blob/main/index.json) of available primer scheme definitions.



## Scheme specification

A scheme definition has three components:

1.  A reference sequence (e.g. [`reference.fasta`](https://github.com/pha4ge/primer-schemes/blob/main/schemes/artic-sars-cov-2/400/v4.1.0/reference.fasta))
2.  A seven column Primal Scheme-like BED file of primer sequences & coordinates (e.g. [`primer.bed`](https://github.com/pha4ge/primer-schemes/blob/main/schemes/artic-sars-cov-2/400/v4.1.0/primer.bed))
3.  A metadata file in JSON format adhering to a [schema](https://github.com/pha4ge/primaschema/blob/main/src/primaschema/schema/info.yml) (e.g. [`info.json`](https://github.com/pha4ge/primer-schemes/blob/main/schemes/artic-sars-cov-2/400/v4.1.0/info.json))



## Tooling

The repository's companion tool [Primaschema](https://github.com/pha4ge/primaschema) is used to automatically validate schemes in this repository, create graphics and manage checksums, as well as generate a six column scheme.bed for legacy tool compatibility. It may be installed standalone using `pip install` for fetching, validating and interrogating primer schemes.



## Contributing new scheme definitions

We encourage contributions of any schemes the others might wish to use, especially if sequencing data has been or will be deposited publicly. We're working to make this process easier, but in the meantime please either follow the instructions below to send us a draft scheme, or create a pull request using GitHub if comfortable doing so.

A scheme definition comprises *i)* a reference sequence (`reference.fasta`), *ii)* a BED file of primer sequences & reference coordinates (`primer.bed`), and *iii)*, a metadata file in JSON format adhering to [this schema](https://github.com/pha4ge/primaschema/blob/main/src/primaschema/schema/info.yml), called `info.json`. If you've created a scheme you probably already have i) and ii), and need to make `info.json`. It's easiest to begin by modifying a copy of an existing `info.json` [such as this one](https://github.com/pha4ge/primer-schemes/blob/main/schemes/eden/2500/v1.0.0/info.json).

1. Check that the `target_organisms` field in your scheme's `info.json` references the correct pathogen. If there are no existing schemes for the target pathogen, please [open a GitHub issue](https://github.com/pha4ge/primer-schemes/issues) to request it be added.
2. Choose a scheme name and version, e.g `midnight-sars-cov-2` and `v1.0.0`. The name should not include special characters except hyphens.
    - If adding a new scheme, choose any name.
    - If updating your existing scheme, keep the same name and update the version:
      - Versions must take the form `v{major}.{minor}.{patch}`, optionally followed by a hyphenated suffix (e.g. `v3.0.0-ont`)
      - For primer changes beyond adding primers, increment the *major* version
      - If only adding primers with respect to an existing version, increment the *minor* version
      - For smaller technical changes, the *patch* version may be incremented
    - If updating a third party's existing scheme, you may propose a new scheme name with version `v1.0.0` rather than increment the existing scheme's version.
3. Complete the `name` and `version` fields inside your new scheme's `info.json`, along with the other required fields:
    - `amplicon_size`: the approximate integer amplicon length in bp
    - `contributors`: a list of contributor names or organisations
    - `target_organisms`: a list of target organisms
4. [Open a GitHub issue](https://github.com/pha4ge/primer-schemes/issues) attaching or linking to your `reference.fasta`, `primer.bed` and `info.json` files.
5. If you wish, you may install [primaschema](https://github.com/pha4ge/primaschema) and run `primaschema build {scheme-directory}` to validate your newly created scheme and add checksums etc. However this is not necessary.



## Scheme definitions

### MPXV

- `yale-mpox/2000/v1.0.0`
- `rigshospitalet/2500/v1.0.0`

### NiV

- `nipah/400/v1.0.0`

### SARS-CoV-2

- `eden/2500/v1.0.0`
- `midnight-sars-cov-2/1200/v1.0.0`
- `midnight-sars-cov-2/1200/v2.0.0`
- `bccdc-midnight-sars-cov-2/1200/v1.0.0`
- `bccdc-midnight-sars-cov-2/1200/v2.0.0`
- `bccdc-midnight-sars-cov-2/1200/v3.0.0`
- `bccdc-midnight-sars-cov-2/1200/v4.0.0`
- `ont-midnight-sars-cov-2/1200/v3.0.0`
- `artic-sars-cov-2/400/v1.0.0`
- `artic-sars-cov-2/400/v2.0.0`
- `artic-sars-cov-2/400/v3.0.0`
- `artic-sars-cov-2/400/v4.0.0`
- `artic-sars-cov-2/400/v4.1.0`
- `artic-sars-cov-2/400/v5.0.0`
- `artic-sars-cov-2/400/v5.2.0`
- `artic-sars-cov-2/400/v5.3.2`
- `artic-sars-cov-2/400/v5.4.2`
