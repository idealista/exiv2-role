# Change Log
All notable changes to this project will be documented in this file.
This project adheres to [Semantic Versioning](http://semver.org/) and [Keep a changelog](https://github.com/olivierlacan/keep-a-changelog).

## [Unreleased](https://github.com/idealista/exiv2-role/tree/develop)

## [1.0.2](https://github.com/idealista/exiv2-role/tree/1.0.2)
[Full Changelog](https://github.com/idealista/exiv2-role/compare/1.0.1...1.0.2)
### Added
- *[#7](https://github.com/idealista/exiv2-role/pull/7) (2024-01-17)- Add ".gitattributes" file for linguist detection.* @ygomezsaiz
### Changed
- *[#11](https://github.com/idealista/exiv2-role/issues/11) Migrate the test suite to Molecule 3 with a pipenv-pinned toolchain, replacing the Molecule 1.25 setup that no longer runs* @danieljesus
- *[#11](https://github.com/idealista/exiv2-role/issues/11) Declare an `author` and use `galaxy_tags` instead of the deprecated `categories` in the role metadata* @danieljesus
- *[#11](https://github.com/idealista/exiv2-role/issues/11) Update the README for the new toolchain, and drop the Vagrant, landrush and VirtualBox prerequisites along with the driver they described* @danieljesus
### Fixed
- *[#8](https://github.com/idealista/exiv2-role/issues/8) Use the `is failed` test instead of the `failed` filter removed in Ansible 2.9* @danieljesus
- *[#11](https://github.com/idealista/exiv2-role/issues/11) Point the molecule container at archive.debian.org, the tested Debian suites are EOL* @danieljesus
- *[#11](https://github.com/idealista/exiv2-role/issues/11) Keep the goss spec parameterised on `exiv2_version` rather than hardcoding the version it asserts* @danieljesus

## [1.0.1](https://github.com/idealista/exiv2-role/tree/1.0.1)
[Full Changelog](https://github.com/idealista/exiv2-role/compare/1.0.1...1.0.0)
### Fixed
- [#2](https://github.com/idealista/exiv2-role/issues/2) *Fixing Exiv2 source package download URL* @dortegau

## [1.0.0](https://github.com/idealista/exiv2-role/tree/1.0.0)
### Added
- *First release* @jmonterrubio
