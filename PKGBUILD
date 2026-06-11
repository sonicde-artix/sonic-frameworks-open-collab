# Maintainer: callmetango
# Contributor: Felix Yan <felixonmars@archlinux.org>
# Contributor: Antonio Rojas <arojas@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=sonic-frameworks-open-collab
pkgver=6.26.0
pkgrel=1
arch=(x86_64)
pkgdesc='Qt library that implements the Open Collaboration Services API'
url='https://github.com/Sonic-DE/sonic-frameworks-open-collab'
license=(LGPL-2.0-only LGPL-3.0-only)
depends=(glibc
         libstdc++
         qt6-base)
makedepends=(doxygen
             qt6-tools
             sonic-frameworks-cmake-modules)
provides=(attica)
conflicts=(attica)
groups=(sonicde-frameworks)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('326e4010ae83cb3f4b1ddcac54d39e2a2672e7706ff39ae320b35b13a50fbf11')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
