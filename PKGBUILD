# Maintainer: Bryce Beagle <first dot last at gmail dot com>
# Contributor: Giampaolo Mancini <mancho at trmpln dot com>
# Contributor: wenLiangcan <boxeed at gmail dot com>
# Contributor: Dustin Falgout <dustin@falgout.us>
# Contributor: Gifts <gifts.antichat@gmail.com>
# Contributor: Andrey Vlasovskikh <andrey.vlasovskikh@gmail.com>

pkgname=rider-eap
pkgver=202.5103.14
eapver=2020.2
eaprelease=2
_dlver="${eapver}-EAP${eaprelease}-${pkgver}.Checked"
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
sha256sums=('9a9edff60b64a716cc42a656b93e85e25f3e412525d81fbaef17013ab2f3b273'
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
