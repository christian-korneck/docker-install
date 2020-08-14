# about this fork

this is a quick hack of the Docker install script to work around the [broken](https://github.com/docker/for-linux/issues/955) installation on Fedora 32 via the following workarounds:
- install packages from Docker fc31 repo (as there's currently no fc32 repo)
- `firewalld` backend: `nftables` -> `iptables` (if installed)
- kernel cmdline: cgroups v1

Alternatives:
- [Fedora Magazine article](https://fedoramagazine.org/docker-and-fedora-32/) (slightly different - uses moby, stays with nftables)
- [Blogpost](https://poweruser.blog/how-to-install-docker-on-fedora-32-f2606c6934f1?source=collection_home---5------1-----------------------) (this setup manually)

How to use:

```
sudo curl -L https://raw.githubusercontent.com/christian-korneck/docker-install/master/install.sh | sh
```

and reboot

---

# docker/docker-install
Home of the script that lives at `get.docker.com` and `test.docker.com`!

The purpose of the install script is for a convenience for quickly
installing the latest Docker-CE releases on the supported linux
distros. It is not recommended to depend on this script for deployment
to production systems. For more thorough instructions for installing
on the supported distros, see the [install
instructions](https://docs.docker.com/engine/installation/).

This repository is solely maintained by Docker, Inc.

## Usage:

From `https://get.docker.com`:
```shell
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh
```

From `https://test.docker.com`:
```shell
curl -fsSL https://test.docker.com -o test-docker.sh
sh test-docker.sh
```

From the source repo (This will install latest from the `test` channel):
```shell
sh install.sh
```

## Testing:

To verify that the install script works amongst the supported operating systems run:

```shell
make check
```

## Legal
*Brought to you courtesy of our legal counsel. For more context,
please see the [NOTICE](NOTICE) document in this repo.*

Use and transfer of Docker may be subject to certain restrictions by the
United States and other governments.

It is your responsibility to ensure that your use and/or transfer does not
violate applicable laws.

For more information, please see https://www.bis.doc.gov

## Reporting security issues

The maintainers take security seriously. If you discover a security issue,
please bring it to their attention right away!

Please **DO NOT** file a public issue, instead send your report privately to
[security@docker.com](mailto:security@docker.com).

Security reports are greatly appreciated and we will publicly thank you for it.
We also like to send gifts—if you're into Docker schwag, make sure to let
us know. We currently do not offer a paid security bounty program, but are not
ruling it out in the future.

## Licensing

docker/docker-install is licensed under the Apache License, Version 2.0.
See [LICENSE](LICENSE) for the full license text.
