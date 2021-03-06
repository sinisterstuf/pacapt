## Table of contents

* [Name](#name)
* [Description](#description)
* [Installation](#installation)
* [Usage](#usage)
* [Implemented Operations](#implemented-operations)
* [Support](#support)
* [Development](#development)
* [License](#license)
* [Authors](#authors)

## Name

`pacapt` - An `Arch`'s pacman-like package manager for some `Unices`.

## Description

An `Arch`'s pacman-like package manager for some `Unices`.
Actually this `Bash` script provides a wrapper for system's package manager.
For example, on `CentOS` machines, you can install `htop` with command

    $ pacapt -S htop

Instead of remembering various options/tools on different `OS`s, you only
need a common way to manipulate packages. Not all options of the native
package manager are ported; the tool only provides a very basic interface
to search, install, remove packages, and/or update the system.

`Arch`'s pacman is chosen, as pacman is quite smart when it divides all
packages-related operations into three major groups:
  `Synchronize`, `Query` and `Remove/Clean up`.
It has a clean man page, and it is the only tool needed to manipulate
official packages on system.
(`Debian`, for example, requires you to use `apt-get`, `dpkg`, and/or `aptitude`.)

The tool supports the following package managers:

* `pacman`        by `Arch Linux`, `ArchBang`, `Manjaro`, etc.
* `dpkg/apt-get`  by `Debian`, `Ubuntu`, etc.
* `homebrew`      by `Mac OS X`
* `macports`      by `Mac OS X`
* `yum/rpm`       by `Redhat`, `CentOS`, `Fedora`, etc.
* `portage`       by `Gentoo`
* `zypper`        by `OpenSUSE`
* `pkgng`         by `FreeBSD`
* `cave`          by `Exherbo Linux`
* `pkg_tools`     by `OpenBSD`
* `sun_tools`     by `Solaris(SunOS)`
* `apk`           by `Alpine Linux`

## Installation

1. This script shouldn't be installed on an Arch-based system.
2. On `FreeBSD` and `Alpine Linux`, please install `bash` package first.
3. Use the stable script.

````
$ sudo wget -O /usr/local/bin/pacapt \
https://github.com/icy/pacapt/raw/ng/pacapt

$ sudo chmod 755 /usr/local/bin/pacapt

$ sudo ln -sv /usr/local/bin/pacapt /usr/local/bin/pacman || true
````

This script is actually picked from the latest stable branch,
which is `v2.0` at the moment. If you want to compile a script
from its components, please make sure you use a correct branch.
See `CONTRIBUTING.md` for details.

## Usage

Some basic command line options

* `-h` (`--help`): Print help message;
* `-P`: Print list of suppoted operations;
* `-V`: Print script version

Some popular options of the original `ArchLinux`'s `pacman` program
are supported and listed in the table in the next section.

A short description can be found at

  https://github.com/icy/pacapt/blob/ng/lib/help.txt.

## Implemented operations

```
           Q Qc Qi Ql Qm Qo Qp Qs Qu R Rn Rns Rs S Sc Scc Sccc Si Sii Sl Ss Su Suy Sw Sy U
      apk  y  .  y  y  .  y  .  y  y y  y   y  y y  y   y    y  y   y  y  y  y   y  y  y y
     cave  y  .  y  y  .  y  y  y  y y  y   y  y y  y   y    y  y   .  .  y  y   y  .  y y
      dnf  y  y  y  y  y  y  y  .  y y  .   .  . y  y   y    y  y   .  y  y  y   y  y  y y
     dpkg  y  .  y  y  .  y  y  y  y y  y   y  y y  y   y    y  y   y  .  y  y   y  .  y y
 homebrew  y  y  y  y  .  y  .  y  y y  .   .  y y  y   y    y  y   .  .  y  y   y  .  y .
 macports  .  y  .  y  .  y  .  .  y y  .   .  y y  y   y    .  y   .  .  y  y   y  .  y .
    pkgng  y  .  y  y  .  y  y  .  y y  .   .  y y  y   y    .  y   .  .  y  y   y  .  y .
pkg_tools  y  .  y  y  .  y  y  .  y y  y   y  y y  y   y    .  y   .  y  y  y   y  .  y .
  portage  y  y  y  y  .  y  .  .  y y  .   .  y y  y   y    y  y   .  .  y  y   y  .  y .
sun_tools  y  .  y  y  .  y  .  y  . y  .   .  . .  .   .    .  .   .  .  .  .   .  .  . y
      yum  y  y  y  y  y  y  y  .  y y  .   .  y y  y   y    y  y   y  .  y  y   y  .  y y
   zypper  y  y  y  y  y  y  y  y  y y  y   y  y y  y   y    y  y   y  y  y  y   y  .  y y
```

## Support

Please use the ticket system at https://github.com/icy/pacapt/issues .

## Development

Make sure you read some instructions in `CONTRIBUTING.md`.

A development script can be compiled from the source code.

````
$ git clone https://github.com/icy/pacapt.git
$ cd pacapt

# switch to development branch
$ git checkout ng

# compile the script
$ ./bin/compile.sh > pacapt.dev

# check if syntax is good
$ bash -n pacapt.dev

$ sudo install -m755 ./pacapt.dev /usr/local/bin/pacapt
````

Please read the sample `Makefile` for some details.

## License

This work is released under the terms of Fair license
(http://opensource.org/licenses/fair).

## AUTHORS

* 10sr
* Alexander Dupuy
* Anh K. Huynh
* Arcterus
* Carl X. Su
* Cuong Manh Le
* Daniel YC Lin
* Danny George
* Darshit Shah
* GijsTimmers
* Hà-Dương Nguyễn
* Huy Ngô
* James Pearson
* Janne Heß
* Jiawei Zhou
* Karol Blazewicz
* Konrad Borowski
* Somasis
* Vojtech Letal
