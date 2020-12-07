# Maintainer: Bernhard Landauer <oberon@manjaro.org>

pkgname=plasma-mobile-settings
pkgver=20201207
pkgrel=1
arch=('any')
url="https://gitlab.manjaro.org/manjaro-arm/packages/community/plasma-mobile/$pkgname"
license=('GPL')
pkgdesc='Settings files for Plasma mobile'
depends=('accountsservice' 'noto-fonts' 'breeze' 'breeze-gtk')
makedepends=('git')
source=('applications-blacklistrc'
    'disable-random-mac.conf'
    'kdeglobals'
    'kwinrc'
    'sddm.conf'
    'packagekit-offline.sh'
    'ofono-fast-dormancy.sh'
    '91_plasma-mobile.gschema.override'
    'plasmamobile.json'
    'Breeze.json'
    'BreezeDark.json'
    'settings.ini')
sha256sums=('bcbe9a3e44016c71811c4323d14dbd79f259b93bae0830cfc26ebfdfdf6e1381'
            '490bd6bda16408da9bd9ac331f5dc344a4874f04f2b257a0a1083b969f7c857a'
            'f7621041edd8dde4a2d15110c5c1d902a78ac1f57a4de6ceb250e12da5db7417'
            '68bc1f74168a8d4f9c3418b37b9373d5a46d3fe550c3d5357dd3d737114abdcf'
            '97200b73d2ff5c989f0b94d9d1189a81b4e54a6746420b389067a62934c148ad'
            'e879ca7b637199e9ab5edd04c1b0c0da6b775ee925c21435f14fad426abe7e62'
            '187bd69ff45ddedb5a2f2152792bd65c0c46ee0082239e86a0d0aab654327617'
            'fd5a89ce81197a912a9879aa5aa33daf68c8f80a4b70192fff89364ef9d18734'
            '42db6e099ab56aa4f6c01107fe83897a059bc371a389379cd3c260d4ab8fd2bc'
            '40000a44b03e7b9a4ffa61eb8cdaf194b21ccb2609fb0aa6386aa14ed3aadb9d'
            '1677f6b5b54ea43780b8683d36032f1bb3603d5072a51e058be8619e777c8790'
            'e3e671c730f7a4ed54011a1152a54e5ce11e6092850c379deb5641d88b5463bd')

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
    install -Dm755 ofono-fast-dormancy.sh $pkgdir/usr/lib/systemd/system-sleep/ofono-fast-dormancy.sh
    install -Dm644 "${srcdir}/91_plasma-mobile.gschema.override" -t "${pkgdir}/usr/share/glib-2.0/schemas"
    install -Dm644 "${srcdir}/plasmamobile.json" -t "${pkgdir}/usr/share/maliit/keyboard2/devices/"
    install -Dm644 "${srcdir}/settings.ini" -t "${pkgdir}/etc/skel/.config/gtk-3.0/"
    install -Dm644 "${srcdir}/Breeze.json" -t "${pkgdir}/usr/share/maliit/keyboard2/themes/"
    install -Dm644 "${srcdir}/BreezeDark.json" -t "${pkgdir}/usr/share/maliit/keyboard2/themes/"
}
