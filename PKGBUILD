# Maintainer: jonathanh
# Contributor: dszryan
# Contributor: Bryce Beagle <first dot last at gmail dot com>
# Contributor: Giampaolo Mancini <mancho at trmpln dot com>
# Contributor: wenLiangcan <boxeed at gmail dot com>
# Contributor: Dustin Falgout <dustin@falgout.us>
# Contributor: Gifts <gifts.antichat@gmail.com>
# Contributor: Andrey Vlasovskikh <andrey.vlasovskikh@gmail.com>

pkgname=rider-eap
eapver=2022.1
eaprelease=7
pkgver=221.5080.29
_dlver="${eapver}-EAP${eaprelease}-${pkgver}.Checked"
pkgrel=1
epoch=1
pkgdesc="A cross-platform .NET IDE by JetBrains."
arch=('any')
options=('!strip' 'staticlibs')
url="https://www.jetbrains.com/rider/eap/"
license=("custom")
optdepends=('mono: .NET runtime' 'msbuild: build .NET Core projects')
provides=("rider-eap")
groups=("development" "IDE" "editor" "jetbrains")

source=("https://download.jetbrains.com/rider/JetBrains.Rider-${_dlver}.tar.gz"
        "${pkgname}.desktop"
        "ResharperHost-runtime-folder.sh")
sha256sums=('e0d3f83a11e43577cde3f921ccb8c691a40ea99095b87447ca6f47234dc1a7f5'
            'ada362803d6d2b5ff84680277694d0ecdcb97d46f85d140f79850500966f1ecf'
            '4bc086ff245cf18c5fd2351008b05a0d0e792e8af0394fb094a9118c312c373d')

package() {
    cd "${srcdir}"
    install -dm 755 \
        "${pkgdir}/usr/share/${pkgname}" \
        "${pkgdir}/usr/bin/" \
        "${pkgdir}/usr/share/applications/" \
        "${pkgdir}/usr/share/licenses/${pkgname}/"

    cp -R --no-preserve=ownership "${srcdir}/JetBrains Rider-${pkgver}/"* "${pkgdir}/usr/share/${pkgname}"
    cp -R --no-preserve=ownership "${srcdir}/JetBrains Rider-${pkgver}/license/"* "${pkgdir}/usr/share/licenses/${pkgname}"

    install -m644 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications/"
    ln -s "/usr/share/${pkgname}/bin/rider.sh" "${pkgdir}/usr/bin/rider-eap"
}
