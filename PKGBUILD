# Maintainer: miaoermua <miaoermua@gmail.com>
pkgname=oopz-electron
pkgver=1.2.9
pkgrel=1
pkgdesc="Oopz Electron App (uses system electron)"
arch=('x86_64')
url="https://web.oopz.cn/"
license=('MIT')
depends=('electron')
makedepends=('git')
provides=($pkgname)
options=(!emptydirs)

source=(
    "git+https://github.com/miaoermua/oopz-electron.git#tag=v$pkgver"
)
sha256sums=('SKIP')

package() {
    _datadir="/usr/lib/$pkgname"
    _bindir="/usr/bin"
    _desktopdir="/usr/share/applications"
    _iconsdir="/usr/share/icons/hicolor"

    mkdir -p "$pkgdir$_datadir"
    mkdir -p "$pkgdir$_bindir"
    mkdir -p "$pkgdir$_desktopdir"
    mkdir -p "$pkgdir$_iconsdir/256x256/apps"

    cd "$srcdir/oopz-electron"
    cp -r main.js package.json "$pkgdir$_datadir/"

    cp icon.png "$pkgdir$_iconsdir/256x256/apps/$pkgname.png"

    cat > "$pkgdir$_bindir/oopz-electron" << 'EOF'
#!/bin/sh
APP_DIR="/usr/lib/oopz-electron"
cd "$APP_DIR"
echo "正在启动 Oopz... 首次加载可能需要 10-20 秒"
exec electron main.js "$@"
EOF
    chmod +x "$pkgdir$_bindir/oopz-electron"

    cat > "$pkgdir$_desktopdir/$pkgname.desktop" << EOF
[Desktop Entry]
Name=Oopz
Comment=Oopz Electron App
Exec=$pkgname
Icon=$pkgname
Terminal=false
Type=Application
Categories=Network;Chat;
StartupWMClass=oopz-electron
EOF
    chmod 644 "$pkgdir$_desktopdir/$pkgname.desktop"
}