# Maintainer: Maxime Gauduin <alucryd@archlinux.org>

pkgname=libretro-yabause-git
pkgver=r3296.f515e5a49
pkgrel=1
pkgdesc='Sega Saturn core'
arch=('i686' 'x86_64')
url='https://github.com/libretro/yabause'
license=('GPL2')
groups=('libretro-unstable')
depends=('glibc' 'libretro-core-info')
makedepends=('git')
provides=('libretro-yabause')
conflicts=('libretro-yabause')
source=('libretro-yabause::git+https://github.com/libretro/yabause.git')
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/libretro-yabause/yabause/"

  echo "r$(git rev-list --count HEAD).$(git rev-parse --short HEAD)"
}

prepare() {
  cd "$srcdir/libretro-yabause/yabause"
  cmake .
}

build() {
  cd "$srcdir/libretro-yabause/yabause/src/libretro"
  make
}

package() {
  cd "$srcdir/libretro-yabause/yabause/src/libretro"

  install -Dm 644 yabause_libretro.so -t "${pkgdir}"/usr/lib/libretro/
}

# vim: ts=2 sw=2 et:
