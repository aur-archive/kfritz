# Maintainer: Scheich Manfred
pkgname=kfritz
pkgver=0.0.13
pkgrel=2
pkgdesc="A KDE program for users of AVMs Fritz!Box to get call signaling and other functions. "
arch=(i686 x86_64)
url="http://kde-apps.org/content/show.php?content=120190"
license=('GPL2')
depends=('kdelibs>=4.3' 'commoncpp2')
makedepends=('automoc4' 'cmake' 'boost')
source=("http://kde-apps.org/CONTENT/content-files/120190-${pkgname}_${pkgver}.orig.tar.gz")
md5sums=('2bd31b66a5c356e58074ca5967cdfb12')

build() {
cd "$srcdir/$pkgname"

#run cmake manually to set the correct CMAKE_INSTALL_PREFIX
mkdir build
cd build
cmake -DCMAKE_INSTALL_PREFIX=/usr ..

cd $srcdir/$pkgname
LDFLAGS=""
make || return 1

}

package() {
     cd $srcdir/$pkgname/build
    make DESTDIR=$pkgdir install || return 1
    install -D -m644 $srcdir/kfritz/$pkgname.desktop $pkgdir/usr/share/applications/$pkgname.desktop
}