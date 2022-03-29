#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>
pkgname=gcstar
_pkgname=GCstar
pkgver=1.7.3
pkgrel=3
pkgdesc="A collection management application"
arch=("any")
url="http://www.gcstar.org"
license=("GPL")
depends=(
  # Official Arch Linux Repositories
  "hicolor-icon-theme"
  "perl-archive-zip"
  "perl-date-calc"
  "perl-datetime-format-strptime"
  "perl-gd"
  "perl-gdgraph"
  "perl-gtk3-simplelist"
  "perl-http-cookies"
  "perl-http-date"
  "perl-http-message"
  "perl-json"
  "perl-locale-codes"
  "perl-libwww"
  "perl-lwp-protocol-https"
  "perl-mp3-info"
  "perl-sort-naturally"
  "perl-switch"
  "perl-xml-libxml"
  "perl-xml-parser"
  "perl-xml-simple"

  # Archiv8 / AUR
  "perl-mp3-tag"
  "perl-net-freedb"
  "perl-ogg-vorbis-header-pureperl"
   )
optdepends=(
  # Official Arch Linux Repositories
  "perl-image-exiftool:  to retrieve data from a mkv file"
  )
source=(https://gitlab.com/Kerenoc/GCstar/-/archive/v$pkgver/${_pkgname}-v$pkgver.tar.bz2)
sha256sums=(
  "9b5b1f6b37e73b3401030a0816acc6922c9f65e56d94a279b615e40a1fb5915a"
  )

package() {
  cd ${_pkgname}-v$pkgver/$pkgname
  perl ./install --text --prefix="$pkgdir"/usr
  install -D -m644 "$pkgdir"/usr/share/gcstar/icons/gcstar_256x256.png \
                   "$pkgdir"/usr/share/pixmaps/gcstar.png
  install -D -m644 "$pkgdir"/usr/share/gcstar/icons/gcstar_32x32.png \
                   "$pkgdir"/usr/share/pixmaps/gcstar32.png
  cp -R share/applications "$pkgdir"/usr/share
# cleaning up
  rmdir "$pkgdir"/usr/share/icons/hicolor/scalable/{apps,mimetypes}
  rmdir "$pkgdir"/usr/share/icons/hicolor/scalable/
  rm "$pkgdir"/usr/share/applications/mimeinfo.cache
  rm -rf "$pkgdir"/usr/share/mime
}
