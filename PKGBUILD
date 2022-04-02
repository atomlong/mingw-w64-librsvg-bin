pkgname=mingw-w64-librsvg-bin
pkgver=2.54.0
pkgrel=1
pkgdesc="SVG rendering library (mingw-w64)"
arch=('any')
url="https://www.gnome.org"
license=('custom')
depends=('mingw-w64-gdk-pixbuf2' 'mingw-w64-pango' 'mingw-w64-cairo' 'mingw-w64-libxml2')
provides=('mingw-w64-librsvg')
conflicts=('mingw-w64-librsvg')
source=("http://repo.msys2.org/mingw/x86_64/mingw-w64-x86_64-librsvg-$pkgver-$pkgrel-any.pkg.tar.zst")
sha256sums=('77bdc96eba0c56d80274428edce39820672690d91e3ad950416a8d2beb96c0d5')

_architectures="x86_64-w64-mingw32"

package() {
  cd "${srcdir}/mingw64"
  for _arch in ${_architectures}; do
    mkdir -p ./* $pkgdir/usr/${_arch}/
    sed -i -e "s|/mingw64|/usr/${_arch}|" ./lib/pkgconfig/*
    cp -r ./* $pkgdir/usr/${_arch}/
  done
}