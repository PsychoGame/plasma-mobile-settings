# Maintainer: Bernhard Landauer <oberon@manjaro.org>

pkgname=plasma-mobile-settings
pkgver=20201130
pkgrel=2
arch=('any')
url="https://gitlab.manjaro.org/manjaro-arm/packages/community/plasma-mobile/$pkgname"
license=('GPL')
pkgdesc='Settings files for Plasma mobile'
makedepends=('git')
source=('applications-blacklistrc'
    'disable-random-mac.conf'
    'kdeglobals'
    'kwinrc'
    'sddm.conf'
    'packagekit-offline.sh'
    'ofono-fast-dormancy.sh')
sha256sums=('bcbe9a3e44016c71811c4323d14dbd79f259b93bae0830cfc26ebfdfdf6e1381'
            '490bd6bda16408da9bd9ac331f5dc344a4874f04f2b257a0a1083b969f7c857a'
            '45b91431730349d796e4452faaa98a467b54e5d3a7bb32e1490944ed183b30be'
            '68bc1f74168a8d4f9c3418b37b9373d5a46d3fe550c3d5357dd3d737114abdcf'
            '26829ea578b0007185dbd2d5f9f196c01de45532414ff48beb287a53f79e52cb'
            'e879ca7b637199e9ab5edd04c1b0c0da6b775ee925c21435f14fad426abe7e62'
            '187bd69ff45ddedb5a2f2152792bd65c0c46ee0082239e86a0d0aab654327617')

pkgver() {
    date +%Y%m%d
}

package() {
    xdg=$pkgdir/etc/xdg
    install -Dm644 applications-blacklistrc $xdg/applications-blacklistrc
    install -Dm644 disable-random-mac.conf $pkgdir/etc/NetworkManager/conf.d/disable-random-mac.conf
    install -Dm644 kdeglobals $xdg/kdeglobals
    install -Dm644 kwinrc $xdg/kwinrc
    install -Dm644 sddm.conf $pkgdir/etc/sddm.conf
    install -Dm755 packagekit-offline.sh $pkgdir/etc/profile.d/packagekit-offline.sh
    install -Dm755 ofono-fast-dormancy.sh $pkgdir/lib/systemd/system-sleep/ofono-fast-dormancy.sh
}
