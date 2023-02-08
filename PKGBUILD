# Maintainer: https://github.com/Voron-Orel
# Contributor: https://github.com/Voron-Orel

pkgname=atlasvpn-bin
pkgver=1.0.3
pkgrel=1
arch=(x86_64)
pkgdesc='Package to install AtlasVPN'
url=https://atlasvpn.com/
license=(custom)
install=atlasvpn.install
source_x86_64=("atlasvpn_${pkgver}_amd64.deb::https://repo.atlasvpn.com/debian/pool/main/a/atlasvpn/atlasvpn_${pkgver}_amd64.deb" "atlasvpn.install")
sha256sums_x86_64=('969fd91120b29ec3e618118fbd3d0c5a16006cc2bc1819026d7d4defc8bd7b3c' '425e199172eccfb2865829354bd4b6841ba450fbc4815397fd7031c0474f2acd')

package() {
  # Extract the debian package
  echo "Extracting debian package"
  ar vx $srcdir/atlasvpn_${pkgver}_amd64.deb
  mkdir $srcdir/data
  tar xf "data.tar.xz" -C "${srcdir}/data"
  
  chmod -R 755 ${pkgdir}
# Configure systemd service
  echo "Configuring systemd service"
  install -Dm644 "${srcdir}/data//usr/lib/systemd/system/atlasvpnd.service" -t "${pkgdir}/usr/lib/systemd/system/"
  install -Dm644 "${srcdir}/data//usr/lib/systemd/system/atlasvpnd.socket" -t "${pkgdir}/usr/lib/systemd/system/"
  
# Configure binary and license
  echo "Configuring binary and license"
  install -Dm755 "${srcdir}/data/usr/bin/atlasvpn" -t "${pkgdir}/usr/bin/"
  install -Dm755 "${srcdir}/data/usr/sbin/atlasvpnd" -t "${pkgdir}/usr/bin/"
}
