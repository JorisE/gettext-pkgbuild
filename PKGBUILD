# $Id$
# Maintainer:

pkgname=gettext
pkgver=0.18.3.2
pkgrel=1
pkgdesc="GNU internationalization library"
arch=('i686' 'x86_64')
url="http://www.gnu.org/software/gettext/"
license=('GPL')
groups=('base' 'base-devel')
depends=('gcc-libs' 'acl' 'sh' 'glib2' 'libunistring')
optdepends=('git: for autopoint infrastructure updates')
options=(!docs)
install=gettext.install
source=(ftp://ftp.gnu.org/pub/gnu/gettext/${pkgname}-${pkgver}.tar.gz{,.sig})
md5sums=('241aba309d07aa428252c74b40a818ef'
         'SKIP')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr
  make
}

check() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make -j1 -k check
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
}
