# Maintainer: Martin Rotter <rotter.martinos@gmail.com>
# Contributor: Petr Vanek <petr@scribus.info>

pkgname=rss-guard
pkgver=1.1.2
pkgrel=3
pkgdesc='A (very) tiny RSS & ATOM reader (stable version) developed using Qt framework.'
arch=('i686' 'x86_64')
url="http://code.google.com/p/rss-guard/"
license=('GPL3')
depends=(qt4 qtwebkit hicolor-icon-theme)
makedepends=(gcc cmake)
conflicts=(rss-guard-git)
source=(http://rss-guard.googlecode.com/files/rssguard-$pkgver-src.tar.gz)
md5sums=('03d59898a980d7901d2c707b6edd159d')

build() {
  cd $srcdir/$pkgname

  if [ ! -d "build" ]; then
    mkdir "build"
  fi
  
  cd "build"

  msg "Preparing files with cmake..."
  cmake ../ -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=release

  msg "Compiling files..."
  make DESTDIR=${pkgdir} install || return 1
  msg "All files were successfully compiled..."
}
