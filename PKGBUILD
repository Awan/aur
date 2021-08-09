# Maintainer: Johannes Pfrang <johannespfrang+arch @ gmail.com>
# Co-Maintainer: Emanuele 'Lele aka eldios' Calo' <xeldiosx@gmail.com>
# Co-Maintainer: Ariel AxionL <arielaxionl@gmail.com | axionl@aosc.io>

_pkgname=teleport
pkgname=teleport-bin
pkgver=6.2.8
pkgrel=1
pkgdesc="Modern SSH server for teams managing distributed infrastructure"
arch=('x86_64' 'armv7h' 'aarch64')
url="https://github.com/gravitational/teleport"
license=('Apache')
depends=()
provides=('teleport' 'tctl' 'tsh')
install=teleport.install

source=("teleport.service"
        "teleport@.service"
        "teleport.install")

source_x86_64=("teleport-bin-${pkgver}-x86_64.tar.gz::https://get.gravitational.com/teleport-v${pkgver}-linux-amd64-bin.tar.gz")
source_armv7h=("teleport-bin-${pkgver}-armv7h.tar.gz::https://get.gravitational.com/teleport-v${pkgver}-linux-arm-bin.tar.gz")
source_aarch64=("teleport-bin-${pkgver}-aarch64.tar.gz::https://get.gravitational.com/teleport-v${pkgver}-linux-arm64-bin.tar.gz")

sha256sums=('22fd1ee136e9422458740811c9946de447105f26e87dbbc8daa35d17bd1f3894'
            '21ca4e56c9c5e1ce11570894e85ded853e26e91cc2e16ed9114b3d6a2c5c22ef'
            'ce2dd61cae3c0c3684e7e629f98b77551e66ddedca2194250a34f0efbc674f3a')
sha256sums_x86_64=('6ecbda4bde9844cdbd77773874d6151ac76d4b5c00d41e7dc8d77ade9a298d5d')
sha256sums_armv7h=('a310be1093d9190597a46f17db919b52559af3a391ee4f958d7c73889369e06f')
sha256sums_aarch64=('cbe79fa29a64008f08232b2c8c6a04fdad690afab22466b6ca309a4992a4f5f5')

options=(!strip)

package() {
    cd "${srcdir}/${_pkgname}"

    # Install binaries
    install -Dm755 teleport "${pkgdir}/usr/bin/teleport"
    install -Dm755 tctl "${pkgdir}/usr/bin/tctl"
    install -Dm755 tsh "${pkgdir}/usr/bin/tsh"

    # Install services
    install -Dm644 ${srcdir}/teleport.service "${pkgdir}/usr/lib/systemd/system/teleport.service"
    install -Dm644 ${srcdir}/teleport@.service "${pkgdir}/usr/lib/systemd/system/teleport@.service"

    # Copy example files
    install -dm755 "${pkgdir}/usr/share/teleport"
    cp -r examples "${pkgdir}/usr/share/teleport/"
}
