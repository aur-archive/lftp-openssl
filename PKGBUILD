pkgname=lftp-openssl
pkgrname=lftp
provides=('lftp')
conflicts=('lftp')
pkgver=3.7.14
pkgrel=1
pkgdesc="Sophisticated command line based FTP client with openssl"
arch=('i686' 'x86_64')
license=('GPL3')
depends=('gcc-libs' 'readline' "gnutls>=2.6.6" "expat>=2.0.1-2" 'perl')
url="http://lftp.yar.ru/"
backup=('etc/lftp.conf')
source=(http://ftp.yars.free.net/pub/source/lftp/${pkgrname}-${pkgver}.tar.bz2)
md5sums=('723d372833d6a94c15cc78cc98565517')

build() {
  cd ${srcdir}/${pkgrname}-${pkgver}
  ./configure --prefix=/usr --with-gnutls \
	--with-openssl --disable-static
  make || return 1
  make DESTDIR=${pkgdir} install || return 1
  rm -rf ${pkgdir}/usr/lib
}
