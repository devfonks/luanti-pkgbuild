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
b2sums=(0aae40158f526d7f8929dca5a3748f1867f28936acd8463331a7030cc0d5a2daa176e8cd2dddd1057c96b3ff730860ee2ff849c067ddbff02e2293adfb185b70)

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
        cmake -DCMAKE_BUILD_TYPE="Debug" -DCMAKE_INSTALL_PREFIX="/usr" ..
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

