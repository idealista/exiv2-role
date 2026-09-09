![Logo](https://raw.githubusercontent.com/idealista/exiv2-role/master/logo.gif)

[![Build Status](https://app.travis-ci.com/idealista/exiv2-role.svg?branch=master)](https://app.travis-ci.com/idealista/exiv2-role)
# Exiv2 Ansible role

This ansible role installs Exiv2 image metadata manager tool/libs in a debian environment. It also builds [Expat](https://libexpat.github.io/) from sources, which Exiv2 depends on.

- [Getting Started](#getting-started)
	- [Prerequisities](#prerequisities)
	- [Installing](#installing)
- [Usage](#usage)
- [Testing](#testing)
- [Built With](#built-with)
- [Versioning](#versioning)
- [Authors](#authors)
- [License](#license)
- [Contributing](#contributing)

## Getting Started

These instructions will get you a copy of the role for your ansible playbook. Once launched, it will install a [exiv2](http://www.exiv2.org/) tool and libraries.

### Prerequisities

Ansible 2.3.1.0 or above installed. The role is tested against Ansible 2.9.
Inventory destination should be a Debian environment. Stretch and Buster are the suites covered by the test matrix.

For testing purposes, Python 3.7 with [Molecule](https://molecule.readthedocs.io/) and [Docker](https://www.docker.com/).

### Installing

Create or add to your roles dependency file (e.g requirements.yml):

```
- src: idealista.exiv2-role
  version: 1.0.3
  name: exiv2
```

Install the role with ansible-galaxy command:

```
ansible-galaxy install -p roles -r requirements.yml -f
```

Use in a playbook:

```
- hosts: someserver
  roles:
    - role: exiv2
```

## Usage

Look to the [defaults](defaults/main.yml) properties file to see the possible configuration properties.

`exiv2_version` defaults to 0.26, and `expat_version` to 2.2.5. Both are built from sources into `exiv2_root_path` and `expat_root_path`.

`exiv2_version` can be overridden within the 0.26 line only: the role builds with autotools (`make config`, `./configure`, `make`), and Exiv2 moved to a CMake-only build in 0.27, so anything from 0.27 onwards fails at `make config`.

The goss spec reads `exiv2_version` from [defaults/main.yml](defaults/main.yml), so changing the default there propagates to the verification. Overriding the variable from a playbook does not — the role would build one version while the test still asserts the default.

Set `exiv2_force_reinstall: true` to rebuild even when the expected version is already installed.

## Testing

```sh
$ pip install pipenv
$ pipenv sync
$ pipenv run molecule test
```

The scenario runs against `debian:buster-slim` by default. `MOLECULE_DISTRO` selects the other tested suite:

```sh
$ MOLECULE_DISTRO=debian:stretch-slim pipenv run molecule test
```

## Built With

![Ansible](https://img.shields.io/badge/ansible-2.9.27-green.svg)
![Molecule](https://img.shields.io/badge/molecule-3.0.4-green.svg)
![Goss](https://img.shields.io/badge/goss-0.3.16-green.svg)


## Versioning

For the versions available, see the [tags on this repository](https://github.com/idealista/exiv2-role/tags).

Additionaly you can see what change in each version in the [CHANGELOG.md](CHANGELOG.md) file.

## Authors

* **Idealista** - *Work with* - [idealista](https://github.com/idealista)

See also the list of [contributors](https://github.com/idealista/exiv2-role/contributors) who participated in this project.

## License

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

This project is licensed under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) license - see the [LICENSE](LICENSE) file for details.

## Contributing

Please read [CONTRIBUTING.md](.github/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.
