# Maintainer: Christian Hesse <mail@eworm.de>
# Contributor: Balló György <ballogyor+arch at gmail dot com>
# Contributor: Jonathan Conder <jonno.conder@gmail.com>

pkgname=gnome-packagekit
pkgver=3.14.2
pkgrel=1
pkgdesc='Collection of graphical tools for PackageKit to be used in the GNOME desktop'
arch=('i686' 'x86_64')
url='http://www.packagekit.org/'
license=('GPL')
depends=('desktop-file-utils' 'gtk3' 'libnotify' 'packagekit')
makedepends=('intltool' 'itstool' 'docbook-xsl' 'libcanberra')
install="${pkgname}.install"
source=("http://ftp.gnome.org/pub/gnome/sources/${pkgname}/${pkgver%.*}/${pkgname}-${pkgver}.tar.xz")

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"

	./configure --prefix=/usr \
		--sysconfdir=/etc \
		--disable-schemas-compile \
		--disable-gtk-doc \
	PYTHON=/usr/bin/python2
	sed -i 's|docbook2man|docbook2man --sgml|' man/Makefile
	make
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"

	make DESTDIR="${pkgdir}" install
}

sha256sums=('d3abbf6f7e599a5f39dda28b99a5f511380612283078a35ea8daf71e6c51ebc3')
