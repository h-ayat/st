# Maintainer:

pkgname=st-monosans-git
pkgver=0.8.4.1136.4a7d578
pkgrel=1
pkgdesc='Simple (suckless) terminal with scrollback, ligatures and One Dark color scheme'
url='https://github.com/monosans/st'
arch=('i686' 'x86_64')
license=('MIT')
depends=('libxft' 'harfbuzz' 'ttf-jetbrains-mono')
makedepends=('git')
source=('git://github.com/monosans/st')
sha256sums=('SKIP')
provides=('st')
conflicts=('st')

pkgver() {
  cd st
  _pkgver=$(awk '/VERSION/ {print $3}' config.mk|head -1)
  echo "${_pkgver}.$(git rev-list --count HEAD).$(git rev-parse --short HEAD)"
}

prepare() {
	cd $srcdir/st
	sed -i '/tic /d' Makefile
}

build() {
	cd st
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
	cd st
	make PREFIX=/usr DESTDIR="${pkgdir}" install
}
