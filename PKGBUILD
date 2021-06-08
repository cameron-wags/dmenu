pkgname=dmenu
pkgver=5.0
pkgrel=1
epoch=
pkgdesc="dmenu with fuzzy matching patch"
arch=("any")
url="https://github.com/cameron-wags/dmenu"
license=("MIT")
depends=()
source=("$pkgname-$pkgver.tar.gz::https://dl.suckless.org/tools/$pkgname-$pkgver.tar.gz"
        "$pkgname-fuzzymatch-4.9.diff::https://tools.suckless.org/$pkgname/patches/fuzzymatch/$pkgname-fuzzymatch-4.9.diff")
md5sums=("614404940441e36fef8ecc533ad9ba96"
         "10f1d55f242fd34aae6b72b51fd50915")

prepare() {
    mv "$pkgname-fuzzymatch-4.9.diff" "$pkgname-$pkgver/"
    cd "$pkgname-$pkgver"
    git apply "$pkgname-fuzzymatch-4.9.diff"
}

package() {
    cd "$pkgname-$pkgver"
    make X11INC="/usr/include/X11" X11LIB="/usr/lib" DESTDIR="$pkgdir" install
}
