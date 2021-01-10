# packages

This repository hosts a static Debian package repository for APT clients.

Its contents are incrementally deployed using the canonical static deploy pipeline, which itself is
triggered by the Debian package release pipeline. The site is deployed automatically as a static
subsite and is also redundantly hosted on Github Pages via CNAME `packages.kevinlin.info`.

## Instructions

Import the GPG public key:

```bash
$ wget -qO- https://packages.kevinlin.info/gpg.key | sudo apt-key add -
```

Add a source line in `/etc/apt/sources.list.d/packages.list` for each package:

```
deb https://apt.internal.kevinlin.info/packages.kevinlin.info/<package> /
```
