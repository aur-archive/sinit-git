_gitname=sinit
pkgname=${_gitname}-git
pkgver=0.9.r10.gb15e988
pkgrel=1
pkgdesc="A simple init"
url="http://tools.suckless.org/sinit/"
arch=('i686' 'x86_64')
license=('MIT')
makedepends=('git')
provides=('sinit')
conflicts=('sinit')
install=sinit.install
source=('git+http://git.suckless.org/sinit')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$_gitname"
  git describe --long --tags | sed -r 's/^v//;s/([^-]*-g)/r\1/;s/-/./g'
}

build() {
  cd "$srcdir/$_gitname"
  make
}

package() {
  cd "$srcdir/$_gitname"
  make DESTDIR="$pkgdir" PREFIX=/usr install
  install -m644 -D LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -m644 -D README "$pkgdir/usr/share/doc/$pkgname/README"
}
