# Maintainer: Bernhard Landauer <oberon@manjaro.org>

pkgname=plasma-mobile-settings
pkgver=20211118
pkgrel=1
arch=('any')
url="https://gitlab.manjaro.org/manjaro-arm/packages/community/plasma-mobile/$pkgname"
license=('GPL')
pkgdesc='Settings files for Plasma mobile'
depends=('accountsservice' 'noto-fonts' 'breeze' 'breeze-gtk' 'systemd')
makedepends=('git')
source=('applications-blacklistrc'
    'disable-random-mac.conf'
    'kdeglobals'
    'kwinrc'
    'startkderc'
    'sddm.conf'
    'packagekit-offline.sh'
    '91_plasma-mobile.gschema.override'
    'plasmamobile.json'
    'settings.ini'
    'powerdevil.hook')
sha256sums=('db89a855aa5e6070fcfbe659f40497e048ec8a7e8624ee02e9a0bb967eaaf488'
            '490bd6bda16408da9bd9ac331f5dc344a4874f04f2b257a0a1083b969f7c857a'
            'f7621041edd8dde4a2d15110c5c1d902a78ac1f57a4de6ceb250e12da5db7417'
            '68bc1f74168a8d4f9c3418b37b9373d5a46d3fe550c3d5357dd3d737114abdcf'
            'bf14819bb36a95cbb465169ca3640d8a93f9a648881f9f52f6315a1ba40d273c'
            '97200b73d2ff5c989f0b94d9d1189a81b4e54a6746420b389067a62934c148ad'
            'e879ca7b637199e9ab5edd04c1b0c0da6b775ee925c21435f14fad426abe7e62'
            'fd5a89ce81197a912a9879aa5aa33daf68c8f80a4b70192fff89364ef9d18734'
            '42db6e099ab56aa4f6c01107fe83897a059bc371a389379cd3c260d4ab8fd2bc'
            'e3e671c730f7a4ed54011a1152a54e5ce11e6092850c379deb5641d88b5463bd'
            '42c4de4c9310904ada1c84e23a34e42fcf20f8318a5f798372468381965dbd18')

pkgver() {
    date +%Y%m%d
}

package() {
    xdg=$pkgdir/etc/xdg
    install -Dm644 applications-blacklistrc $xdg/applications-blacklistrc
    install -Dm644 disable-random-mac.conf $pkgdir/etc/NetworkManager/conf.d/disable-random-mac.conf
    install -Dm644 kdeglobals $xdg/kdeglobals
    install -Dm644 kwinrc $xdg/kwinrc
    install -Dm644 startkderc $xdg/startkderc
    install -Dm644 sddm.conf $pkgdir/etc/sddm.conf.d/00-default.conf
    install -Dm755 packagekit-offline.sh $pkgdir/etc/profile.d/packagekit-offline.sh
    install -Dm644 "${srcdir}/91_plasma-mobile.gschema.override" -t "${pkgdir}/usr/share/glib-2.0/schemas"
    install -Dm644 "${srcdir}/plasmamobile.json" -t "${pkgdir}/usr/share/maliit/keyboard2/devices/"
    install -Dm644 "${srcdir}/settings.ini" -t "${pkgdir}/etc/skel/.config/gtk-3.0/"
    # install alpm hook
    install -Dm644 "$srcdir/powerdevil.hook" "$pkgdir/usr/share/libalpm/hooks/90-powerdevil.hook"    
}
