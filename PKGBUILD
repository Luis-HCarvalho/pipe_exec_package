# Maintainer: Luis Carvalho <luishenriquecm12@gmail.com>
pkgname=pipe_exec
pkgver=master
pkgrel=1
pkgdesc="Execute ELF binaries from pipes, stdin and ttys"
arch=('x86_64')
url="https://github.com/koraa/pipe_exec"
license=('MIT')
source=("${pkgname}-${pkgvar}.tar.gz::https://github.com/koraa/pipe_exec/archive/refs/heads/master.tar.gz"
	"$pkgname-$pkgver.patch")
sha256sums=('97291bef3985201a9f20bbcc6b2dbb2a5bb5500cf91cedd3dce4c35e3efa5e0e'
            '2cb8655242c508390db4d781354116bce02081c180b4558ebcc647fb942afb7c')

prepare() {
	patch -d "$pkgname-$pkgver" -Np1 -i "$srcdir/$pkgname-$pkgver.patch"
}

build() {
	cd "$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" PREFIX=/usr
}

package() {
	cd "$pkgname-$pkgver"
        install -Dm644 COPYING -t "${pkgdir}/usr/share/licenses/${pkgname}/"
        make DESTDIR="$pkgdir/" PREFIX=/usr install
}
