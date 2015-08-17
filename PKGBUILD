# $Id$
# Maintainer:  Chhatoi Pritam Baral <pritam@pritambaral.com>
# Contributor: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com> (Maintainer of ABS package)
# Contributor: Nicky726 (Nicky726 <at> gmail <dot> com)
# Contributor: Allan McRae (allan <at> archlinux <dot> org)
# Contributor: Alexander 'bas' Brovikov (bas <at> it-core <dot> org)

pkgname=wine-stable_gecko
trackingpkgname=wine_gecko
pkgver=2.21
pkgrel=1
pkgdesc="Wine (Stable branch)'s built-in replacement for Microsoft's Internet Explorer"
arch=(i686 x86_64)
url="http://wiki.winehq.org/Gecko"
license=(MPL)
depends=('wine>=1.5.31', 'wine<=1.7.2')
source=(http://downloads.sourceforge.net/project/wine/Wine%20Gecko/$pkgver/$trackingpkgname-$pkgver-x86{,_64}.msi)
md5sums=('432eb3a2d05c3f07df67864f53c87c60'
         '580bbabde1ec99ba9caa439c2dbca3f6')

if [[ $CARCH == i686 ]]; then
  # Strip x86_64 msi
  source=(${source[0]})
  md5sums=(${md5sums[0]})
fi

package() {
  _geckodir="$pkgdir/usr/share/wine/gecko"

  install -Dm644 $trackingpkgname-$pkgver-x86.msi "$_geckodir/$trackingpkgname-$pkgver-x86.msi"
  if [[ $CARCH == x86_64 ]]; then
    install -m644 $trackingpkgname-$pkgver-x86_64.msi "$_geckodir/"
  fi
}

