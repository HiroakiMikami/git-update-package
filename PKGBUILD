# Maintainer: Your Name <youremail@domain.com>
pkgname=update-git-repository
pkgver=r3.c5577e1
pkgrel=1
pkgdesc=""
arch=("x86_64")
url=""
license=('MIT')
groups=()
depends=()
makedepends=('systemd')
provides=("${pkgname}")
conflicts=("${pkgname}")
replaces=()
backup=()
options=()
source=()
install=
noextract=()
md5sums=()

pkgver() {
  cd "$srcdir"

  # Git, no tags available
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  # Add systemd service
  cd "$startdir"
  mkdir -p "$pkgdir/usr/local/bin"
  mkdir -p "$pkgdir/etc/systemd/user"
  cp ./update-git-repository "$pkgdir/usr/local/bin"
  cp ./update-git-repository@.service "$pkgdir/etc/systemd/user/"
  cp ./update-git-repository@.timer "$pkgdir/etc/systemd/user/"
}
