pkgname='tokyonight-gtk-theme-git'
_reponame='Tokyo-Night-GTK-Theme'
pkgver=r93.93295bf8
pkgrel=1
pkgdesc='A GTK theme based on the Tokyo Night colour palette.'
arch=("any")
url="https://github.com/StratOS-Linux/${_reponame}"
license=("GPL3")
depends=("gnome-themes-extra")
optdepends=("gtk-engine-murrine")
makedepends=("git" "sassc" "rsync")
source=()
# sha256sums=('SKIP')
options=(!strip !debug) # trying to strip symbols from icons is too expensive
install=real.install
prepare() {
  cp -ra $startdir/extra $srcdir/
  cp -ra $startdir/icons $srcdir/
  cp -ra $startdir/themes $srcdir/
}
package() {
    dist="${pkgdir}/usr/share/themes"
    mkdir -p "${dist}"
    dist="${pkgdir}/usr/share/icons"
    mkdir -p "${dist}"
    cd ../icons
    for icontheme in */; do
        cp -r "$icontheme" "${dist}/$icontheme"
    done
    sudo ln -sf $srcdir/themes/gtkrc.sh /usr/local/bin/gtkrc.sh 2>/dev/null
    sudo ln -sf $srcdir/themes/install.sh /usr/local/bin/install.sh 2>/dev/null
    sudo chmod +x /usr/local/bin/gtkrc.sh /usr/local/bin/install.sh 2>/dev/null
}
