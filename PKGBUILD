# Contributor: Tudhalyas <tudhalyas_AT_gmail_DOT_com>

pkgname=amulegui-upnp
pkgver=2.2.6
pkgrel=1
pkgdesc="Remote GUI for the aMule Daemon, an eMule-like client for the ed2k p2p network"
arch=('i686' 'x86_64')
url="http://www.amule.org/"
license=('GPL')
depends=('wxgtk>=2.8.0' 'gd>=2.0.34' 'binutils>=2.17.50.0.18' 'geoip>=1.4.4' 'libupnp>=1.6.6')
makedepends=('crypto++')
conflicts=('amule' 'amule-svn' 'amule-noupnp-svn' 'amule-noupnp')
provides=("amulegui=${pkgver}")
source=(http://downloads.sourceforge.net/sourceforge/amule/aMule-${pkgver}.tar.bz2)
md5sums=('530d9b48187e36f78fc21bb19e94326d')

build() {
  cd ${srcdir}/aMule-${pkgver}
  ./configure --prefix=/usr \
              --mandir=/usr/share/man \
              --enable-optimize \
              --enable-amule-gui \
              --disable-cas \
              --disable-alcc \
              --enable-upnp \
	      --enable-geoip \
	      --disable-monolithic \
              --disable-wxcas \
              --disable-alc \
              --disable-debug
  make || return 1
  make DESTDIR=${pkgdir}/ install || return 1
}

