# Contributor: Guten <ywzhaifei@gmail.com>

pkgname=user-daemon-system
pkgver=20120114  
pkgrel=1
pkgdesc="A User based Daemon System for ZSH"
arch=("i686" "x86_64")
url="https://github.com/GutenYe/user-daemon-system"
license=("MIT-LICENSE")
groups=()
depends=()
makedepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=("home/$USER/etc/rc.conf")
options=()
changelog=

_gitroot="git://github.com/GutenYe/user-daemon-system"
_gitname="user-daemon-system"

build() {
  cd ${srcdir}
  msg "Connecting to GIT server...."

  if [ -d ${_gitname}/.git ] ; then
    cd ${_gitname}

    # Change remote url to anongit
    if [ -z $( git branch -v | grep anongit ) ] ; then
        git remote set-url origin ${_gitroot}
    fi
    
    git pull origin
    msg "The local files are updated."
  else
    git clone ${_gitroot} ${_gitname}
  fi
  msg "GIT checkout done or server timeout"
}


package() {
  cd $srcdir/$_gitname

  mkdir -p $pkgdir/home/$USER
  cp -r etc var $pkgdir/home/$USER/

  chown $USER:$USER -R $pkgdir
}


# vim:set ts=2 sw=2 et:
