# Maintainer: BlackIkeEagle

pkgname=docker-ce-bin
_rpmfile=docker-ce-18.06.1.ce-3.fc27.x86_64.rpm
pkgver=18.06.1
pkgrel=1
pkgdesc='Pack, ship and run any application as a lightweight container, using official binaries'
arch=('x86_64')
url='https://www.docker.com/'
license=('Apache')
provides=('docker')
conflicts=('docker' 'docker-git')
replaces=('docker-bin')
depends=('bridge-utils' 'iproute2' 'device-mapper' 'sqlite' 'systemd' 'libseccomp')
optdepends=('btrfs-progs: btrfs backend support'
            'lxc: lxc backend support')
# don't strip binaries! A sha1 is used to check binary consistency.
options=('!strip')
source=(
  "https://download.docker.com/linux/fedora/27/x86_64/stable/Packages/$_rpmfile"
  "docker.sysusers")
sha512sums=('67e7ca5f793c37eaf50e5cc7c115c5c949348257765ffa6ade9e9f3ac657643e38fb86ea468d194bfa6f0b4a17d580f3df15c4913f17934a3736b3d656088a9d'
            '5791272636736b70509ae5ddd29ba94caba52ba7cc90190e20b867d926a47f1fd062fe8c00cb5585e4def39814bfc7a2d5d191fed46b26847b0206f65647309d')

package() {
  cp -a {etc,usr} "$pkgdir"
  mv "$pkgdir/usr/share/zsh/"{vendor-completions,site-functions}
  install -Dm644 "$srcdir/docker.sysusers" \
    "$pkgdir/usr/lib/sysusers.d/docker.conf"
}

# vim:set ts=2 sw=2 et:
