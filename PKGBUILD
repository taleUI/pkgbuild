pkgname=gh-desktop
pkgver=1
pkgrel=1
pkgdesc='Grasshopper desktop - DEBUG VERSION'
arch=('any')
license=('GPL')
makedepends=('pnpm' 'npm' 'git')
sha512sums=('SKIP')

prepare() {
    if [[ "$CI" == "true" ]]; then
        git clone ${{ secrets.SECRET_GH_CLONEURL }}/taleUI/electron-wm ${srcdir}/electron-wm
    else
        git clone https://github.com/taleUI/electron-wm ${srcdir}/electron-wm
    fi
    cd ${srcdir}/electron-wm && pnpm install && pnpm build && cd -
}

package() {
    mkdir -p ${pkgdir}/usr/share/gh-desktop ${pkgdir}/usr/bin ${pkgdir}/usr/share/xsessions
    cp ${srcdir}/runewm ${pkgdir}/usr/bin
    chmod +x ${pkgdir}/usr/bin/runewm
    cp ${srcdir}/gh-desktop.desktop ${pkgdir}/usr/share/xsessions
    cp -r ${srcdir}/electron-wm ${pkgdir}/usr/share/gh-desktop/
}