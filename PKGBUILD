# $Id:$
# Maintainer: <fero dot kiraly at gmail.com>

pkgname=pd-vanilla
pkgver=0.46.6
_ver=${pkgver%.*}-${pkgver##*.}
pkgrel=1
pkgdesc="vanilla version of PureData by Miller Puckette"
arch=('i686' 'x86_64')
url="http://crca.ucsd.edu/~msp/software.html"
license=('custom:BSD')
optdepends=('puredata-utils' 'pd-extended')
source=("http://msp.ucsd.edu/Software/pd-$_ver.src.tar.gz")
md5sums=('341649683c1ff3902e1578f7eae99272')

build() {
  #MAKE --------------------------------------------------------------------------
  cd "$srcdir/pd-$_ver" || return 1
  ./autogen.sh
  ./configure --enable-jack
  make BUILDLAYOUT_DIR=$srcdir/$pkgname/packages \
    DESTDIR=$pkgdir \
    prefix=/usr
}

package(){
  cd "$srcdir/pd-$_ver"
  make DESTDIR=$pkgdir \
    prefix=/usr install
  rm $pkgdir/usr/bin/pdreceive
 rm $pkgdir/usr/bin/pdsend
 rm $pkgdir/usr/share/man/man1/pdreceive.1
 rm $pkgdir/usr/share/man/man1/pdsend.1
 rm $pkgdir/usr/lib/libportaudio.so.2.0.0
 rm $pkgdir/usr/lib/libportaudio.so.2
 rm $pkgdir/usr/lib/libportaudio.so
 rm $pkgdir/usr/lib/libportaudio.la
 rm $pkgdir/usr/lib/libportaudio.a
 rm $pkgdir/usr/include/portaudio.h
 rm $pkgdir/usr/include/pa_linux_alsa.h
 rm $pkgdir/usr/include/pa_jack.h
 rm $pkgdir/usr/lib/pkgconfig/portaudio-2.0.pc

}
