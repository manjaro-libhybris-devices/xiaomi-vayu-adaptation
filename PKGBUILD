# Maintainer: Arman Ghamgosar <armgham92@gmail.com>

pkgname=xiaomi-vayu-adaptation
provides=(halium11-post-install)
conflicts=(halium11-post-install)
pkgver=1$(date +%y%m%d)
pkgrel=1
pkgdesc="Manjaro libhybris adaptation for xiaomi vayu"
arch=('any')
url="https://github.com/armgham/xiaomi-vayu-adaptation"
license=('GPL')
depends=('gzip' 'glibc-locales' 'wget' 'systemd')
makedepends=('git')
source=("xiaomi-vayu-adaptation::git+https://github.com/armgham/xiaomi-vayu-adaptation.git")
install=$pkgname.install
md5sums=('SKIP')

package() {
    mv "${srcdir}/xiaomi-vayu-adaptation/xiaomi-vayu-adaptation.sh" "${srcdir}/xiaomi-vayu-adaptation/xiaomi-vayu-adaptation"

    mkdir -p "${pkgdir}/usr/bin/"
    install -Dm755 "${srcdir}/xiaomi-vayu-adaptation/xiaomi-vayu-adaptation" -t "${pkgdir}/usr/bin/"

    mkdir -p "${pkgdir}/usr/lib/systemd/system/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/xiaomi-vayu-adaptation.service" -t "${pkgdir}/usr/lib/systemd/system/"

    mkdir -p "${pkgdir}/usr/lib/sysusers.d/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/android.conf" -t "${pkgdir}/usr/lib/sysusers.d/"

    cp -r "${srcdir}/xiaomi-vayu-adaptation/droid-vendor-overlay" -t "${pkgdir}/usr/lib/"

    mkdir -p ${pkgdir}/etc/phosh/
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/phoc.ini" -t "${pkgdir}/etc/phosh/"

    mkdir -p "${pkgdir}/etc/udev/rules.d/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/70-vayu.rules" -t "${pkgdir}/etc/udev/rules.d/"
    
    mkdir -p "${pkgdir}/etc/gst-droid/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/gstdroidcodec.conf" -t "${pkgdir}/etc/gst-droid/"

    mkdir -p "${pkgdir}/boot/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/boot.img" -t "${pkgdir}/boot/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/dtbo.img" -t "${pkgdir}/boot/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/vbmeta.img" -t "${pkgdir}/boot/"

    mkdir -p "${pkgdir}/usr/lib/systemd/system/bluebinder.service.d/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/10-after.conf" "${pkgdir}/usr/lib/systemd/system/bluebinder.service.d"

    mkdir -p "${pkgdir}/var/lib/bluetooth/"
    install -Dm644 "${srcdir}/xiaomi-vayu-adaptation/board-address" -t "${pkgdir}/var/lib/bluetooth/"

}

