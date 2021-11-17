pkgname=firmware-asus-x01ad
pkgver=0.1
pkgrel=0
pkgdesc="Firmware files for Asus Max M2"
url="https://postmarketos.org"
arch="aarch64"
license="proprietary"
depends="wcnss-wlan"
_repository="x01ad-firmware"
_commit="ef2d302b4ed71d1578d6a12be720767e7459fce6"
source="$pkgname-$_commit.tar.gz::https://github.com/danascape/x01ad-firmware/archive/$_commit.tar.gz"
options="!strip !check !archcheck !spdx"
builddir="$srcdir/x01ad-firmware-$_commit"

_files="wcnss.b00 wcnss.b01 wcnss.b02 wcnss.b03 wcnss.b04
	wcnss.b05 wcnss.b06 wcnss.b07 wcnss.b08 wcnss.b09
	wcnss.b10 wcnss.b11 wcnss.b12 wcnss.mdt
	adsp.b00 adsp.b01 adsp.b02 adsp.b03 adsp.b04
	adsp.b05 adsp.b06 adsp.b07 adsp.b08 adsp.b09
	adsp.b10 adsp.b11 adsp.b12 adsp.b13 adsp.b14 adsp.b15 adsp.mdt
	qdsp6m.qdb
	a506_zap.b00 a506_zap.b01 a506_zap.b02 a506_zap.elf a506_zap.mdt"
_files_prima="WCNSS_wlan_dictionary.dat
	WCNSS_qcom_cfg.ini
	WCNSS_qcom_wlan_nv.bin"

package() {
	# /lib/firmware/postmarketos
	for _i in $_files; do
		install -Dm0755 "$_i" \
			"$pkgdir"/lib/firmware/postmarketos/"$_i"
	done

	# /lib/firmware/postmarketos/wlan/prima
	for _i in $_files_prima; do
		install -Dm0755 wlan/prima/"$_i" \
			"$pkgdir"/lib/firmware/postmarketos/wlan/prima/"$_i"
	done
}

sha512sums="
fbf0e4bc755440542d2f924e1317973cc5f3039e633dd1593ed0da25f4d2a59bf6d92ff5954cd7bda9eb9ca12220bb8c397688d96b86d88562049ea9a78bdb34  firmware-asus-x01ad-ef2d302b4ed71d1578d6a12be720767e7459fce6.tar.gz
"
