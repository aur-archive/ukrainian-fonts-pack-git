# Maintainer: Localizator <localizator@ukr.net>

pkgname=ukrainian-fonts-pack-git
pkgver=20120215
pkgrel=1
pkgdesc="Ukrainian fonts pack for ukrainian users."
arch=(any)
groups=(x11)
url="http://www.localizator.pp.ua/p/ukfp.html"
license=('GPL')
depends=('fontconfig')
makedepends=('git')
install=ukfp.install
_realname=ukrainian-fonts-pack
_gitroot="git://github.com/localizator/${_realname}.git"
_gitname="${_realname}"

build() {
  cd ${srcdir}

  msg "Connecting to GIT server...."

  if [ -d ${_gitname} ]; then
    cd ${_gitname} && git pull origin
    msg "The local files are updated."
  else
    git clone ${_gitroot}
  fi

  msg "GIT checkout done or server timeout"
}

package() {
  cd ${srcdir}/${_realname}
	install -d $pkgdir/usr/share/fonts/truetype/
  cp -R * $pkgdir/usr/share/fonts/truetype/
}