# Maintainer: namelessjon <jonathan.stott@gmail.com>
# Contributor: Alessio Sergi <asergi at archlinux dot us>

pkgname=libsodium
pkgver=0.4.2
pkgrel=2
pkgdesc="P(ortable|ackageable) NaCl-based crypto library"
arch=('i686' 'x86_64')
url="https://github.com/jedisct1/libsodium"
license=('custom:ISC')
depends=('glibc')
options=('!libtool')
source=(http://download.dnscrypt.org/$pkgname/releases/$pkgname-${pkgver}.tar.gz)
sha256sums=('1a7901cdd127471724e854a8eb478247dc0ca67be549345c75fc6f2d4e05ed39')

build() {
  cd "$pkgname-$pkgver"
  ./configure --prefix=/usr
  make
}

check() {
  cd "$pkgname-$pkgver"
  make check
}

package() {
  cd "$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install

  # install license
  install -d -m 755 "$pkgdir/usr/share/licenses/$pkgname"
  install -m 644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}

# vim:set ts=2 sw=2 et:
