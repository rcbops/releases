# Releases

**NOTE**: as of 2018.08, meta-release metadata will no longer be stored in [releases/](releases). This system has been replaced by the component metadata system described below. The original readme has been moved to the [releases/](releases) directory for reference.

---

This repository stores metadata about RPC component releases.

Each component is represented by a file in [components/](components).
This file contains the name of the component, description and a list of all
released versions of the component.

## Component file specification
The file is yaml, so should begin `---`

The yaml document contains a number of top-level entries:
  * **is_product**: true/false
  * **name**: String, name of the component, usually the filename without `.yml`
  * **repo_url**: The URL of the repository where the code for this component is stored
  * **releases**: Dictionary containing at least one **series** entry
      * **series**: Name of the component series (e.g. ```master```)
      * **versions**: Dictionary containing information about the released versions
        * **sha**: sha of the released version
        * **version**: version number of the released version

Example:
```
---
is_product: false
name: rpc-component-2
releases:
- series: master
  versions:
  - sha: 8fdcb3e99a71e1eeb0014484bb6492078402e563
    version: 1.0.2
  - sha: 7646f1d0ef46b997fa976efb1faa99c47b2e6cb4
    version: 1.0.1
  - sha: 76ee8bcd8862e4fb7c48e40fbf8110df80bd747c
    version: 1.0.0
```
