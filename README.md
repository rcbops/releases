# Releases
This repository stores RPC meta-releases.

Each release is represented by a file in [releases/](releases).
This file contains the name of the release, description and a list of all
the components included in the release.

## Release file specification
Name must match the following regex: `YYYY\.MM?\.yml`

The file is yaml, so should begin `---`

The yaml document should be a dictionary with single top level key: **meta-release**. Meta-relase should be a dictionary with three keys:
  * **name**: String, name of the release, should be the filename without `.yml`
  * **description**: String, free form text describing the release
  * **components**: List of every component included in the release
    Each item in the list must be a dictionary with three keys:
      * **name**: Name of the component
      * **url**: Url to the repo or artifact for that component
      * **version**: Version of the component included with this release.

Example:
```
---
  meta-release:
    name: 2017.8
    description: |
      The first RPC meta-release :)
    components:
      - name: rpc-openstack
        url: https://github.com/rcbops/rpc-openstack
        version: r14.1.1
      - name: rpc-maas
        url: https://github.com/rcbops/rpc-maas
        version: 1.0.0
```
