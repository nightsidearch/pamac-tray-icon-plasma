# Maintainer: Artyom Grinyov (LordTermor)

pkgname=pamac-tray-icon-plasma
pkgver=0.1.4
pkgrel=1
pkgdesc="Pamac tray icon for Plasma users"
arch=('x86_64' 'aarch64')
url="https://gitlab.com/LordTermor/pamac-tray-icon-plasma"
license=('GPL-3.0-or-later')
depends=(
  'knotifications'
  'kstatusnotifieritem'
  'libnotify'
  'pamac-all'
  'qt6-base'
)
makedepends=(
  'cmake'
  'git'
)
conflicts=('pamac-tray-appindicator')
replaces=('pamac-tray-appindicator')
_commit=58353a1b0fc4d1ba0957883da27c63aa04d0cdf2
source=("git+https://gitlab.com/LordTermor/pamac-tray-icon-plasma.git#commit=${_commit}")
sha256sums=('2637180ab74a81296abfeb80ca5f2d1f003ea7833ac922acf00fb6cf0a087729')

build() {
  cmake -B build -S "$pkgname" \
    -DCMAKE_BUILD_TYPE='None' \
    -DCMAKE_INSTALL_PREFIX='/usr' \
    -Wno-dev
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
