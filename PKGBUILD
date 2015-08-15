pkgname=fpc-i386-freebsd-lcl
pkgver=0.9.30.2
pkgrel=1
pkgdesc='Lazarus Component Library (i386-freebsd)'
url='http://www.lazarus.freepascal.org/'
license=('GPL2' 'MPL' 'custom:LGPL')
arch=('any')
depends=('ppcross386' 'fpc' 'fpc-src' 'fpc-i386-freebsd-rtl' 'lazarus')
makedepends=('ppcross386')
options=('!emptydirs' '!makeflags')
source=(http://downloads.sourceforge.net/project/lazarus/Lazarus%20Zip%20_%20GZip/Lazarus%20$pkgver/lazarus-$pkgver-src.tar.bz2)
md5sums=('0dcf54613c2f9d38a32d183431e2dfc9')

build() {
  cd $srcdir/lazarus
  make FPC=/usr/bin/fpc clean lcl packager/registration ideintf packager components OS_TARGET=freebsd CPU_TARGET=i386
}

package() {
  cd $srcdir/lazarus
  
  # skip the 'make install' mess completely and do everything manually
  mkdir -p $pkgdir/usr/lib/lazarus
  find . -type f -path *i386-freebsd* -exec cp --parents '{}' $pkgdir/usr/lib/lazarus/ \;
}

