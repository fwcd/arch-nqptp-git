pkgname=nqptp-git
pkgver=1.1.r172.f7f731b
pkgrel=1
arch=("x86_64")
source=(
  "git+https://github.com/mikebrady/nqptp.git#branch=development"
)
sha1sums=("SKIP")

pkgver() {
  cd "$srcdir/nqptp"
  printf "1.1.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd "$srcdir/nqptp"
  autoreconf -fi
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/nqptp"
  make DESTDIR="$pkgdir/" install
}
