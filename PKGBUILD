# Maintainer: TBK <aur at jjtc dot eu>
# Contributor: TBK <aur at jjtc dot eu>

pkgname=hyphen-da
pkgver=20070903
pkgrel=1
pkgdesc="Danish hyphenation rules"
arch=(any)
url="https://www.openoffice.org/lingucomponent/"
license=('LGPL-2.0-or-later')
optdepends=('hyphen: offers hyphenation library functions')
source=(https://www.mirrorservice.org/sites/download.openoffice.org/contrib/dictionaries/hyph_da_DK.zip)
sha512sums=('c7a75b42da48f34874332c71f4919f845c1e5730e02f8d5db2c25efb06f3c91d940cbef784f650c6aaf1d674e04e0df0a421e98b5cf370ee7d57ec3f6ef9b58f')

package() {
  cd "$srcdir"
  install -dm755 "${pkgdir}"/usr/share/hyphen
  cp -p hyph_da_??.* "$pkgdir"/usr/share/hyphen

  # the symlinks
  install -dm755 "${pkgdir}"/usr/share/myspell/dicts
  pushd "$pkgdir"/usr/share/myspell/dicts
    for file in "$pkgdir"/usr/share/hyphen/*; do
      ln -sv /usr/share/hyphen/$(basename $file) .
    done
  popd
  
  # docs
  install -dm755 "${pkgdir}"/usr/share/doc/$pkgname
  cp -p README_hyph_da_DK.txt "$pkgdir"/usr/share/doc/$pkgname
}
