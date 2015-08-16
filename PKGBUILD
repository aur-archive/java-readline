# Maintainer: Markus Opitz <mastero23 at gmail dot com>

pkgname=java-readline
pkgver=0.8.0
pkgrel=3
pkgdesc="JNI-wrapper to readline"
arch=('i686' 'x86_64')
url="http://java-readline.sourceforge.net/"
license=('LGPL')
depends=('readline' 'termcap' 'java-environment')
source=(http://sourceforge.net/projects/$pkgname/files/libreadline-java-$pkgver-src.tar.gz)
md5sums=('501720ddded45eaedf429b7cc356107c')

build() {
  cd "$srcdir/libreadline-java-$pkgver"
  make jar
  make build-native
  make apidoc
}

package() {
  cd "$srcdir/libreadline-java-$pkgver"
  install -D libreadline-java.jar "$pkgdir/usr/share/java/java-readline/libreadline-java.jar"
  install -D libJavaReadline.so "$pkgdir/usr/lib/libJavaReadline.so"
  mkdir -p "$pkgdir/usr/share/doc/java-readline"
  cp -r api/* "$pkgdir/usr/share/doc/java-readline/"
}
