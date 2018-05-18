# Maintainer: asthrp <thomas at blenderlab dot fr>
pkgname=fluxus-git
pkgver=r2.0d
pkgrel=1
epoch=
pkgdesc="A Live coding environment for Visual Artists."
arch=('i686' 'x86_64')
url="https://github.com/AsTHrO/fluxus.git"
license=('GPL')
categories=()
groups=()
depends=('scons')
makedepends=('git')
optdepends=()
checkdepends=()
provides=()
conflicts=("${pkgname%-*}")
replaces=()
backup=()
options=()
changelog=
install=
source=("$pkgname::git+https://github.com/AsTHrO/fluxus.git")
noextract=()
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd "$srcdir/$pkgname"
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/$pkgname"
  make DESTDIR="$pkgdir/usr" install
  install -Dm644 README $pkgdir/usr/share/doc/${pkgname%-*}/README
  sed '145,171!d' README > LICENSE
  install -Dm644 LICENSE $pkgdir/usr/share/licenses/${pkgname%-*}/LICENSE
}

