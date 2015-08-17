## Contributor: nullren
## Contributor: Izumi Natsuka
pkgname=symlinks-git
pkgver=1.4.3git20140416.e22cde5
pkgrel=2
pkgdesc='Scan and change symbolic links (git version)'
arch=('i686' 'x86_64' 'armv7h')
depends=('glibc')
provides=("${pkgname%-*}")
conflicts=("${pkgname%-*}")
url="https://github.com/brandt/${pkgname%-*}"
license=('MIT')
source=("git://github.com/brandt/symlinks.git")
sha1sums=('SKIP')

pkgver() {
	cd "${srcdir}/${pkgname%-*}"
	echo $(git describe --always | sed 's|v||')git$(git log -1 --format="%cd" --date=short | sed 's|-||g').$(git rev-parse --short HEAD)
}

build() {
	cd "${srcdir}/${pkgname%-*}"
	make
}

package() {
	cd "${srcdir}/${pkgname%-*}"
	install -d "${pkgdir}/usr/bin"
	install -d "${pkgdir}/usr/share/licenses/${pkgname%-*}"
	install -d "${pkgdir}/usr/share/${pkgname%-*}"
	install -d "${pkgdir}/usr/share/man/man8"
	install -Dm644 Readme.md "${pkgdir}/usr/share/${pkgname%-*}/README.md"
	install -m644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname%-*}/"
	install -m755 symlinks "${pkgdir}/usr/bin/"
	install -m644 symlinks.8 "${pkgdir}/usr/share/man/man8"
}