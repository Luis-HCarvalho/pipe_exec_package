# Maintainer: Luis Carvalho <luishenriquecm12@gmail.com>
pkgname=pipe_exec
pkgver=master
pkgrel=1
pkgdesc="Execute ELF binaries from pipes, stdin and ttys"
arch=('x86_64')
url="https://github.com/koraa/pipe_exec"
license=('MIT')
source=("${pkgname}-${pkgvar}.tar.gz::https://github.com/koraa/pipe_exec/archive/refs/heads/master.tar.gz")
sha256sums=('db79bd9934120c0c06072650788a033e928615dc94e46e089569085201fa6317')

build() {
	cd "$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" PREFIX=/usr
}

package() {
	cd "$pkgname-$pkgver"
        install -Dm644 COPYING -t "${pkgdir}/usr/share/licenses/${pkgname}/"
        make DESTDIR="$pkgdir/" PREFIX=/usr install
}
