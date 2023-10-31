pkgname=plymouth-theme-grasshopper
pkgver=1
pkgrel=1
pkgdesc='Grasshopper bootsplash'
arch=('any')
license=('GPL')
install="${pkgname}.install"
source=("$pkgbase::git+https://github.com/taleUI/plymouth_themes_grasshopper-splash.git")
sha512sums=('SKIP')

package() {
  cd "$srcdir/$pkgbase"
  mkdir -p $pkgdir/usr/share/plymouth/themes/grasshopper-splash
  install -Dm644 * "${pkgdir}"/usr/share/plymouth/themes/grasshopper-splash
}
