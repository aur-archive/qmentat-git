# Maintainer: Michel Dusseault <mike dot dusseault at gmail dot com>
pkgname=qmentat-git
pkgver=0.9.0
pkgrel=1
pkgdesc='Mental Arithmetic Trainer'
arch=('i686' 'x86_64')
url='http://realgrep.github.io/QMentat/'
license=('GPL3')
depends=('qt4')
makedepends=('git' 'boost')
source=("$pkgname"::git+https://github.com/RealGrep/QMentat.git)
md5sums=('SKIP')

pkgver() {
	cd "$pkgname"
	git describe | sed 's/v//; s/-/./g'
}

build() {
	cd "$srcdir/$pkgname"
	lrelease-qt4 QMentat.pro
	qmake-qt4 QMentat.pro -r -spec linux-g++ CONFIG+=release
	make
}

package() {
	cd "$srcdir/$pkgname"
	make INSTALL_ROOT="$pkgdir/" install
	rm "$pkgdir/usr/share/QMentat/LICENSE"
}

