pkgname=kshutdown
pkgver=3.99.1
pkgrel=1
pkgdesc='Shutdown Utility for KDE'
arch=('x86_64')
url='http://kshutdown.sourceforge.net/'
license=('GPL')
depends=('kde-common' 'qt5-base' 'libdbusmenu-qt5' 'kdbusaddons' 'kconfigwidgets' 'kconfig' 'kglobalaccel' 
'gettext' 'ki18n' 'kidletime' 'knotifications' 'knotifyconfig' 'kxmlgui' 'extra-cmake-modules')
makedepends=('cmake' 'ninja')
source=("https://sourceforge.net/projects/kshutdown/files/KShutdown/3.99.1%20Beta/kshutdown-source-3.99.1beta.zip/download")
#https://sourceforge.net/p/kshutdown/bugs/24/
sha256sums=('36533e9abd40a25d227e3a9cf1163269ac1120993c6ab50dcd45b7846b5f24f3')

build() {
  mkdir build
  cd build
  cmake "../$pkgname-3.99.1beta" \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DKS_KF5=ON \
    -GNinja
  ninja
}

package() {
  DESTDIR="$pkgdir" ninja -C build install
}

# vim:set ts=2 sw=2 et:
