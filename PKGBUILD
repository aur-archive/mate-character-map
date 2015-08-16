# Maintainer : Martin Wimpress <code@flexion.org>
# Contributor: Giovanni "Talorno" Ricciardi <kar98k.sniper@gmail.com>

pkgname=mate-character-map
pkgver=1.6.0
pkgrel=5
pkgdesc="MATE Unicode Charmap"
url="http://mate-desktop.org"
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
license=('GPL')
depends=('gtk2' 'pygtk' 'python2')
makedepends=('gobject-introspection' 'mate-common' 'mate-doc-utils' 'perl-xml-parser')
options=('!emptydirs' )
groups=('mate-extra')
source=("http://pub.mate-desktop.org/releases/1.6/${pkgname}-${pkgver}.tar.xz")
sha1sums=('e378e26ebe493d3f849771d10930504b8980448e')
install=${pkgname}.install

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    PYTHON=/usr/bin/python2 ./autogen.sh \
        --prefix=/usr \
        --enable-charmap \
        --enable-python-bindings \
        --enable-introspection \
        --disable-static \
        --disable-scrollkeeper
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
