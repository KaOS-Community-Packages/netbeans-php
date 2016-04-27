pkgname=netbeans-php
pkgver=8.1
_pkgver=201511021428
pkgrel=1
pkgdesc="A dedicated PHP coding environment and complete integration with web standards"
arch=('x86_64')
url="https://netbeans.org/features/php/index.html"
category=Development
screenshot=http://i.imgur.com/SFUoLTK.png
license=('GPL2')
depends=('java-runtime')
source=("http://bits.netbeans.org/netbeans/${pkgver}/community/zip/netbeans-${pkgver}-${_pkgver}-php.zip" "netbeans-php.desktop")
md5sums=('f7efc4f63ba198f94e32853240a4ac7b'
         'd78d84da8587e80391d60bc984460d56')

options=(!strip)

prepare() {
    echo -en '#!/bin/sh\nexec "/usr/share/netbeans-php/bin/netbeans" "$@"' > $srcdir/$pkgname
}

package() {
    install -dm755 $pkgdir/usr/bin \
    $pkgdir/usr/share/applications \
    $pkgdir/usr/share/${pkgname} \
    $pkgdir/usr/share/pixmaps
    cp -a $srcdir/netbeans/*  $pkgdir/usr/share/$pkgname/
    install -Dm644 $srcdir/$pkgname "${pkgdir}/usr/bin/"
    chmod   +x $pkgdir/usr/bin/$pkgname
    install -Dm644 $srcdir/netbeans/nb/netbeans.png $pkgdir/usr/share/pixmaps/netbeans.png
    install -Dm644 $srcdir/$pkgname.desktop "${pkgdir}/usr/share/applications/${pkgname}.desktop"
}
