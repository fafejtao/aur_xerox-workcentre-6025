# Maintainer: Ondrej Fafejta <fafejtao at gmail dot com>

pkgname=xerox-workcentre-6025
pkgver=1.0
pkgrel=25
pkgdesc="Xerox WorkCentre 6025"
arch=('x86_64')
url="https://www.support.xerox.com/cs-cz/product/workcentre-6025/downloads?platform=linux&category=&language=en_GB"
license=('custom')
depends=('cups')
source=('LICENSE'
        "$pkgname.zip::https://download.support.xerox.com/pub/drivers/WC6025/drivers/linux/pt_BR/xerox-workcentre-6025_${pkgver}-${pkgrel}.zip"
)
sha256sums=('af5852333e592a9782140397763e15cd1959f7248e74f6d3aa4c0f48120c2a6e'
            '4c7450f80ee970fbb277e5706657ec534843f336ffef9f1d810bb9b01bc265a6')

prepare() {
    cd "$srcdir"
    ar x "${pkgname}_${pkgver}-${pkgrel}_amd64.deb"
    tar xzf data.tar.gz
    gunzip -f usr/share/cups/model/Xerox/Xerox_WorkCentre_6025.ppd.gz
}

package() {
    cd "$srcdir"
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
    install -Dm644 usr/share/cups/model/Xerox/Xerox_WorkCentre_6025.ppd "$pkgdir/usr/share/cups/model/Xerox/Xerox_WorkCentre_6025.ppd"
    install -Dm644 usr/share/cups/Xerox/dlut/xcthp3mlut.dat "$pkgdir/usr/share/cups/Xerox/dlut/xcthp3mlut.dat"
    install -Dm644 usr/lib/xcthp3macl.so "$pkgdir/usr/lib/xcthp3macl.so"
    install -Dm755 usr/lib/cups/filter/xcthp3m "$pkgdir/usr/lib/cups/filter/xcthp3m"
}
