# Maintainer: rodriguezst <git@rodriguezst.es>

pkgname=firmware-nabu
_firmcommit=60bcc8485fe3b36861a4b18bfd87d4784f285716
pkgver=20240821
pkgrel=1
pkgdesc="Additional firmware for Xiaomi Pad 5"
arch=('any')
url="https://github.com/map220v/nabu-firmware"
license=('custom')
makedepends=('git')
options=('!strip')
source=("git+https://github.com/map220v/nabu-firmware.git#commit=$_firmcommit")

sha256sums=('SKIP')

package() {

  # install novatek touchscreen driver
  install -Dm644 "$srcdir/nabu-firmware/novatek_nt36523_fw.bin" "$pkgdir/usr/lib/firmware/novatek/novatek_nt36523_fw.bin"
  
  # install qcom drivers (qcom/sm8150/xiaomi/nabu)
  install -Dm644 "$srcdir/nabu-firmware/a640_zap.mbn" "$pkgdir/usr/lib/firmware/qcom/sm8150/xiaomi/nabu/a640_zap.mbn"
  install -Dm644 "$srcdir/nabu-firmware/adsp.mbn" "$pkgdir/usr/lib/firmware/qcom/sm8150/xiaomi/nabu/adsp.mbn"
  install -Dm644 "$srcdir/nabu-firmware/cdsp.mbn" "$pkgdir/usr/lib/firmware/qcom/sm8150/xiaomi/nabu/cdsp.mbn"
  install -Dm644 "$srcdir/nabu-firmware/modem.mbn" "$pkgdir/usr/lib/firmware/qcom/sm8150/xiaomi/nabu/modem.mbn"
  install -Dm644 "$srcdir/nabu-firmware/venus.mbn" "$pkgdir/usr/lib/firmware/qcom/sm8150/xiaomi/nabu/venus.mbn"
  install -Dm644 "$srcdir/nabu-firmware/wlanmdsp.mbn" "$pkgdir/usr/lib/firmware/qcom/sm8150/xiaomi/nabu/wlanmdsp.mbn"
  install -Dm644 "$srcdir/nabu-firmware/modemuw.jsn" "$pkgdir/usr/lib/firmware/qcom/sm8150/xiaomi/nabu/modemuw.jsn"
  # install qcom drivers (qcom)
  install -Dm644 "$srcdir/nabu-firmware/a630_sqe.fw" "$pkgdir/usr/lib/firmware/qcom/a630_sqe.fw"
  install -Dm644 "$srcdir/nabu-firmware/a640_gmu.bin" "$pkgdir/usr/lib/firmware/qcom/a640_gmu.bin"
  # make symlink to mdt extension
  cd "$pkgdir/usr/lib/firmware/qcom/sm8150/xiaomi/nabu"
  ln -s a640_zap.mbn a640_zap.mdt
  ln -s adsp.mbn adsp.mdt
  ln -s cdsp.mbn cdsp.mdt
  ln -s modem.mbn modem.mdt
  ln -s venus.mbn venus.mdt
  ln -s wlanmdsp.mbn wlanmdsp.mdt
  cd "$pkgdir/usr/lib/firmware/qcom"
  ln -s sm8150/xiaomi/nabu/a640_zap.mbn a640_zap.mdt
  cd "$srcdir"
  
}
