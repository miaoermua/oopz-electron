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

    mkdir -p "$pkgdir$_datadir"
    mkdir -p "$pkgdir$_bindir"

    cd "$srcdir/oopz-electron"
    cp -r main.js package.json "$pkgdir$_datadir/"

    cat > "$pkgdir$_bindir/oopz-electron" << 'EOF'
#!/bin/sh
APP_DIR="/usr/lib/oopz-electron"
cd "$APP_DIR"
echo "[Tip] 首次加载资源可能需要 10-20s"
exec electron main.js "$@"
EOF

    chmod +x "$pkgdir$_bindir/oopz-electron"
}