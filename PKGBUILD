# Package maintainer: airwoodix <airwoodix at posteo dot me>

pkgname=python-numtypes-git
pkgver=r34.g818133e
pkgrel=1
pkgdesc="Custom (experimental) data types for numpy"
arch=('i686' 'x86_64')
url="https://github.com/WarrenWeckesser/numtypes"
license=('BSD')
depends=('python-numpy')
makedepends=('git')
source=("${pkgname%-git}::git+https://github.com/airwoodix/numtypes.git#branch=fix-link-npymath")
md5sums=('SKIP')
sha256sums=('SKIP')

pkgver() {
    cd "${pkgname%-git}"
    printf "r%s.g%s" "$(git rev-list --count HEAD)" \
	   "$(git rev-parse --short HEAD)"
}

build() {
    cd "${srcdir}/${pkgname%-git}"
    python setup.py build
}

package() {
    cd "${srcdir}/${pkgname%-git}"
    python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
    install -Dm 644 -t "${pkgdir}/usr/share/licenses/python-numtypes-git" "LICENSE"
}
