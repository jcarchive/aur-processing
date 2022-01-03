# Maintainer: Jose C.

pkgname=processing
pkgver=4.0b2
pkgrel=1
pkgdesc="flexible software sketchbook and a language for learning how to code within the context of the visual arts"
arch=('x86_64')
options=('!strip')
url='https://processing.org/'
license=('Commercial')
provides=('processing')

_filename="processing-$pkgver-linux64.tgz"
_filextract="processing-$pkgver"


source=("https://github.com/processing/processing4/releases/download/processing-1277-4.0b2/processing-4.0b2-linux64.tgz" 
  "$pkgname.desktop")

sha256sums=('a72d93a33a7b1c49ac34935f231e936e985baedc9a1daf2b16d8a45bf6d7544d'
  '612d720aa419f917d92af70de7cb0c50362d092fe5efc7e0d5dba4baa73a887e')

package() {
	cd "${srcdir}"

	#Create directories with permission rwxr-xr-x
	install -d -m755 "${pkgdir}/usr/share" "${pkgdir}/usr/bin" "${pkgdir}/usr/share/applications"

	#Copy files to pkg destination
	cp -a "${_filextract}" "${pkgdir}/usr/share/${pkgname}"
	chown -R root:root "${pkgdir}/usr/share/${pkgname}"

  ln -s "/usr/share/${pkgname}/processing" "$pkgdir/usr/bin/processing"
  ln -s "/usr/share/${pkgname}/processing-java" "$pkgdir/usr/bin/processing-java"

  install -m644 "$srcdir/$pkgname.desktop" "$pkgdir/usr/share/applications"

}
