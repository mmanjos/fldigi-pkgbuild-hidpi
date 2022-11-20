# Maintainer: not_anonymous <nmlibertarian@gmail.com>
# Previous Maintainers: Andreas Schreiner <andreas.schreiner@sonnenmulde.at>
#      and: [Vitaliy Berdinskikh](mailto:ur6lad@archlinux.org.ua) aka UR6LAD
# Original Submission: Bob Finch <w9ya@qrparci.net>

pkgname=fldigi
pkgver=4.1.22
pkgrel=2
pkgdesc="Digital Modem Program for Amateur Radio"
arch=('i686' 'x86_64' 'aarch64')
url="http://w1hkj.com"
license=('GPL')
depends=('cty' 'fltk-git' 'libsamplerate' 'flxmlrpc>=1.0.1'
         'portaudio' 'libpulse' 'hamlib' 'hamradio-menus')
optdepends=('libsndfile: sound file support'
            'pulseaudio: pulseaudio support')
source=(https://github.com/w1hkj/fldigi/archive/master.zip)

prepare() {
  patch --directory="$pkgname-master" --forward --strip=1 --input="${srcdir}/../hidpi-fix.patch"
}

build() {
	cd "$srcdir"/$pkgname-master
	autoreconf -fi
	./configure --prefix=/usr \
		--enable-tls --with-flxmlrpc --without-asciidoc
#		--enable-tls --without-flxmlrpc --without-asciidoc
#			(^^^ temporary, until flxmlrpc is updated)
	make ASCIIDOC_ICONS_DIR=/etc/asciidoc/images/icons/
}

check() {
	cd "$srcdir"/$pkgname-master

	make -k check
}

package() {
	cd "$srcdir"/$pkgname-master

	make DESTDIR="$pkgdir" install
}
md5sums=('ecd6998e50c3888008baac5e3bc382b0')
sha256sums=('0b146f3cec9d51b0c3000edda416041b49d6de4216a331a3a008a91ec2c731fe')
