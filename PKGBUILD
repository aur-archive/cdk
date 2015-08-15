# Maintainer: drm00 <jasmintee at gmx dot de>

pkgname=cdk
pkgver=1.4.11
pkgrel=1
pkgdesc="A Java library for structural chemo- and bioinformatics."
arch=('any')
url="http://sourceforge.net/projects/cdk/"
license=('LGPL2.1')
depends=('java-runtime')
makedepends=('java-environment' 'apache-ant')
install="cdk.install"
source=("http://downloads.sourceforge.net/project/cdk/cdk/${pkgver}/cdk-src%2Blibs-${pkgver}.tar.gz" "cdk.install")
md5sums=('3612e0c050ac662ff4ed2a0df3244c32' 'efce8d8c46951240fb8a9242978fbc8c')

build() {
  cd "${srcdir}/cdk-src+libs-${pkgver}"
  # build single jar
  /usr/bin/ant dist-large
  # build documentation
  /usr/bin/ant -buildfile javadoc.xml html
}

package() {
  cd "${srcdir}/cdk-src+libs-${pkgver}"
  install -d ${pkgdir}/usr/share/java/cdk/
  install -m644 dist/jar/cdk-${pkgver}.jar ${pkgdir}/usr/share/java/cdk/
  install -d ${pkgdir}/usr/share/doc/cdk/
  cp -R doc/${pkgname}-javadoc-${pkgver}/* -t ${pkgdir}/usr/share/doc/cdk/
}


