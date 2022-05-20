# Dev README
## How to make a ebuild
An ebuild file is a text file, usually stored in a repository, which identifies a specific software package and tells the Gentoo package manager how to handle it.

ebuilds contain metadata about each version of a piece of available software (name, version number, license, home page address...), dependency information (both build-time and run-time), and instructions on how to build and install the software (configure, compile, build, install, test...).

The default location for ebuilds in Gentoo is the Gentoo ebuild repository (/var/db/repos/gentoo/).

**It do follow bash-like configuration**
## sample
```bash
# Copyright 1999-2022 Gentoo Authors
# Distributed under the terms of the GNU General Public License v2
 
EAPI=8
 
DESCRIPTION="Some words here"
HOMEPAGE="https://github.com/{name}/{repo}"
SRC_URI="https://github.com/{name}/{repo}/releases/download/{version}/XXX.1.0.1.tar.gz"
 
LICENSE="GPL-2"
SLOT="0"
KEYWORDS="~amd64 ~x86 ~sparc64-solaris"
IUSE="+extra +cjk +terminal"
 
DEPEND="
        systemd.2.49.0
        gpg? ( >=app-crypt/gpgme-1.13.0:= )
"

RDEPEND="${DEPEND}"

BDEPEND="
        acct-group/hellp
        doc? ( sys-apps/fakeroot )
        test? (
                sys-apps/fakechroot)

"

```
