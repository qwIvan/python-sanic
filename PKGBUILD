# Maintainer: Carl George < arch at cgtx dot us >

_name="sanic"
pkgname="python-${_name}"
pkgver="0.2.0"
pkgrel="1"
pkgdesc="A microframework based on uvloop, httptools, and learnings of flask"
arch=("any")
url="https://github.com/channelcat/sanic"
license=("MIT")
makedepends=("python-setuptools")
source=("https://github.com/channelcat/sanic/archive/${pkgver}.tar.gz")
sha256sums=('eda329ee2d4894e1564e40152203532291bec7ac764005946619825aaeee2985')

build() {
    cd "${srcdir}/${_name}-${pkgver}"
    python setup.py build
}

package() {
    depends=("python-uvloop>=0.5.3"
             "python-httptools>=0.0.9"
             "python-ujson>=1.35"
             "python-aiofiles>=0.3.0"
             "python-multidict>=2.0")
    cd "${srcdir}/${_name}-${pkgver}"
    python setup.py install --skip-build --root="${pkgdir}" --optimize=1
    install -Dm0644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
