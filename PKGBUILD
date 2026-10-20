pkgname=unios-update
pkgver=1.0.0
pkgrel=1
pkgdesc="An interactive update notifier & applier for UniOS that assists you with important pre / post update tasks (including a systray applet and extensive CLI)."
arch=('any')
url="https://github.com/open-source-uom/unios-update"
license=('GPL-3.0-or-later')

depends=(
  'bash'
  'curl'
  'diffutils'
  'fakeroot'
  'glib2'
  'glibc'
  'hicolor-icon-theme'
  'htmlq'
  'libgcc'
  'pacman'
  'pacman-contrib'
  'archlinux-contrib'
  'systemd'
  'util-linux'
  'xdg-utils'
)

makedepends=(
  'cargo'
  'make'
  'pkgconf'
  'scdoc'
)

checkdepends=(
  'bats'
)

optdepends=(
  'flatpak: Flatpak packages support'
  'libnotify: Desktop notifications on new updates'
  'alhp-utils: Check for ALHP build queue or outdated mirrors'
  'sudo: Privilege elevation'
  'sudo-rs: Alternative privilege elevation'
  'opendoas: Alternative privilege elevation'
  'vim: Default diff tool for pacdiff'
  'neovim: Diff tool for pacdiff if EDITOR=nvim'
)

source=("git+https://github.com/open-source-uom/unios-update.git")
sha256sums=('SKIP')

build() {
  cd "$pkgname"
  make PREFIX=/usr
}

check() {
  cd "$pkgname"
  make test
}

package() {
  cd "$pkgname"
  make DESTDIR="$pkgdir" PREFIX=/usr install
}
