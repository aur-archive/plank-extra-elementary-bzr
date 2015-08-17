# Maintainer: Maxime Gauduin <alucryd@archlinux.org> 

pkgname=plank-extra-elementary-bzr
pkgver=r7
pkgrel=1
pkgdesc='Extra options for the Plank project'
arch=('i686' 'x86_64')
url='https://launchpad.net/elementary-community/elementary-plank-extra'
license=('GPL3')
depends=('plank')
makedepends=('bzr' 'cmake' 'granite' 'vala')
provides=("${pkgname%-*}")
conflicts=("${pkgname%-*}")
source=("${pkgname%-*}::bzr+http://bazaar.launchpad.net/~versable/elementary-community/elementary-plank-extra/")
sha256sums=('SKIP')

pkgver() {
  cd ${pkgname%-*}

  printf "r%s" "$(bzr revno)"
}

build() {
  cd ${pkgname%-*}

  if [[ -d build ]]; then
    rm -rf build
  fi
  mkdir build && cd build

  cmake .. -DCMAKE_INSTALL_PREFIX='/usr'
  make

  make
}

package() {
  cd ${pkgname%-*}/build

  make DESTDIR="${pkgdir}" install
}

# vim: ts=2 sw=2 et:
