# Maintainer: Bryce Beagle <first dot last at gmail dot com>
# Contributor: Giampaolo Mancini <mancho at trmpln dot com>
# Contributor: wenLiangcan <boxeed at gmail dot com>
# Contributor: Dustin Falgout <dustin@falgout.us>
# Contributor: Gifts <gifts.antichat@gmail.com>
# Contributor: Andrey Vlasovskikh <andrey.vlasovskikh@gmail.com>

pkgname=rider-eap
pkgver=201.5985.59
_dlver="2020.1-EAP2-${pkgver}.Checked"
pkgrel=1
epoch=1
pkgdesc="A cross-platform C# IDE by JetBrains."
arch=('any')
options=('!strip')
url="https://www.jetbrains.com/rider/eap/"
license=("custom")
optdepends=('mono: .NET runtime' 'msbuild-15-bin: build .NET Core projects')
provides=("rider")
conflicts=("rider")
groups=("development" "IDE" "editor" "jetbrains")

source=("https://download.jetbrains.com/rider/JetBrains.Rider-${_dlver}.tar.gz"
        "${pkgname}.desktop")
sha256sums=('70a93f57a038d84b6e052f2b7f165748f1748b54b5805ca74c1a401b3217e192'
            'cbb7c9b847c92c95403be237ab01183eb0516b4a9b46c8ba27c87243fed8cbb8')

package() {
    cd "${srcdir}"
    install -dm 755 \
        "${pkgdir}/opt/${pkgname}" \
        "${pkgdir}/usr/bin/" \
        "${pkgdir}/usr/share/applications/"

    cp -R --no-preserve=ownership "${srcdir}/JetBrains Rider-${pkgver}/"* "${pkgdir}/opt/${pkgname}"

    install -m644 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications/"
    ln -s "/opt/${pkgname}/bin/rider.sh" "${pkgdir}/usr/bin/rider-eap"
}
