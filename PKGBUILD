pkgname=luanti
pkgver=5.13.0
pkgrel=1
pkgdesc="Multiplayer infinite-world block sandbox game"
arch=(i686 x86_64 armv7h aarch64)
url="https://www.luanti.org/"
license=(LGPL)
depends=(curl libvorbis sqlite openal hicolor-icon-theme desktop-file-utils xdg-utils freetype2 luajit postgresql-libs spatialindex jsoncpp libgl libjpeg-turbo libxi)
makedepends=(libcurl-gnutls cmake libpng libogg gmp leveldb ncurses zstd gettext sdl2)
conflicts=(minetest)
replaces=(minetest)
source=("luanti-${pkgver}.tar.gz::https://github.com/luanti-org/luanti/archive/refs/tags/${pkgver}.tar.gz")
b2sums=(SKIP)

prepare () { 
        return 0 
}

pkgver () {
        echo "${pkgver}"
}

build () {
        cd "${pkgname}-${pkgver}"
        mkdir build
        cd build
        cmake -DCMAKE_BUILD_TYPE="Release" -DCMAKE_INSTALL_PREFIX="/usr" ..
        make
}

check () {
        return 0
}

package () {
        cd "${pkgname}-${pkgver}"
        cd build
        make DESTDIR="${pkgdir}" install
}

