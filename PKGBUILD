# $Id: PKGBUILD 91448 2013-05-22 23:10:20Z dwallace $
# Maintainer: Daniel Wallace <danielwallace at gtmanfred dot com>
# Contributor: Giovanni Scafora <giovanni@archlinux.org>

pkgname=python2-beautifulsoup4-4.1
pkgver=4.1.3
pkgrel=2
pkgdesc="A Python HTML/XML parser designed for quick turnaround projects like screen-scraping"
arch=('any')
url="http://www.crummy.com/software/BeautifulSoup/index.html"
conflicts=('python2-beautifulsoup4')
provides=('python2-beautifulsoup4')
license=('PSF')
makedepends=('python2-distribute')
source=("http://www.crummy.com/software/BeautifulSoup/bs4/download/${pkgver%.*}/beautifulsoup4-${pkgver}.tar.gz")

build() {
  cd "${srcdir}/beautifulsoup4-${pkgver}"
  python2 setup.py build
}

package() {
  optdepends=('python2-chardet: universal encoding detector'
              'python2-lxml: pythonic binding for the libxml2 and libxslt libraries')

  cd "${srcdir}/beautifulsoup4-${pkgver}"
  python2 setup.py install --root="${pkgdir}/" --optimize=1 --skip-build

  rm -rf ${pkgdir}/usr/lib/python2.7/site-packages/bs4/tests
}

md5sums=('5aece3c0b8a080658155958111fa2fa9')
