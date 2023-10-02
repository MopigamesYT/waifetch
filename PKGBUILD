# Maintainer: Mopigames <mopigames@proton.me>
pkgname='waifetch'
pkgver=0.1
pkgrel=1
pkgdesc="Neofetch but with waifus"
arch=('x86_64')
url="https://github.com/MopigamesYT/waifetch/"
license=('GPL')
depends=('neofetch' 'w3m' 'chafa' 'jq' 'curl' 'bash' 'sed' 'grep')
makedepends=('git')
checkdepends=()
optdepends=('imagemagick: Thumbnail creation'
	'w3m-img: sometimes bundled together with w3m'
	'iTerm2: Image support is built into Terminology, iTerm2 and kitty, and doesnt require w3m-img.'
	'Terminology: Image support is built into Terminology, iTerm2 and kitty, and doesnt require w3m-img.'
	'kitty: Image support is built into Terminology, iTerm2 and kitty, and doesnt require w3m-img.'
	'libsixel: Image support for kitty'
	'termpix: Image support for kitty'
	'pixterm: Image support for kitty'
	'catimg: Image support for kitty'
	'jp2a: Image support for kitty'
	'caca-utils: Image support for kitty'
	'libcaca: Image support for kitty')
provides=('waifetch')
conflicts=()
changelog=CHANGELOG.md
# source=("$pkgname-$pkgver.tar.gz"
#         "$pkgname-$pkgver.patch")
source=("waifetch::git://github.com/MopigamesYT/waifetch.git")
noextract=()
md5sums=('SKIP')

pkgver() {
	cd "$pkgname"
	printf "%s" "$(git describe --long --tags | sed 's/\([^-]*-\)g/r\1/;s/-/./g')"
}

# prepare() {
# 	cd "$pkgname-$pkgver"
# 	patch -p1 -i "$srcdir/$pkgname-$pkgver.patch"
# }

build() {
	cd "$pkgname"
	./configure --prefix=/usr
	make
}

package() {
	cd "$pkgname"
	install -Dm755 waifetch "$pkgdir/usr/bin/waifetch"
	install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
	install -Dm644 README.md "$pkgdir/usr/share/doc/$pkgname/README.md"
}

# package() {
# 	cd "$pkgname-$pkgver"
# 	make DESTDIR="$pkgdir/" install
# }
