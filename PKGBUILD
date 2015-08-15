# Maintainer: Nuno Araujo <nuno.araujo@russo79.com>
pkgname=enki-git
pkgver=1.9r158.a24aa3b
pkgrel=1
pkgdesc="Fast 2D robot simulator"
arch=('x86_64' 'i686')
url="http://home.gna.org/enki/"
license=('GPL')
#depends=('qt4' 'glu')
#makedepends=('git' 'cmake' 'python2' 'boost')
makedepends=('git' 'cmake' 'qt4' 'glu' 'sdl')
provides=('enki')
conflicts=('enki')
options=('staticlibs')
source=("$pkgname"::'git+https://github.com/enki-community/enki.git')
md5sums=('SKIP')

build() {
  cd "$srcdir/$pkgname"
  cmake -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd "$srcdir/$pkgname"
  make DESTDIR="$pkgdir/" install
  rm -rf "$pkgdir/usr/include/enki/CMakeFiles/"
}

pkgver() {
  cd "$srcdir/$pkgname"
  printf "1.9r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}
# vim:set ts=2 sw=2 et:
