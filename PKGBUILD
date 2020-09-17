#Maintainer: matyklug
pkgname=novix
pkgver=0.0.1
pkgrel=1
pkgdesc=""
arch=(i686 x86_64)
url='https://novavita.github.io'
license=('MIT')
makedepends=( xorriso nasm binutils grub mtools qemu )

source=(https://github.com/novavita/Novix/archive/master.tar.gz)
sha256sums=('SKIP')

build(){
cd Novix-master
make
}
package(){
cd Novix-master
install -Dvm757 _build/novavita.iso $pkgdir/usr/bin/novix/novavita.iso
echo "
  #!/bin/bash
  qemu-system-i386 /usr/bin/novix/novavita.iso -m 1G
" >> $pkgdir/usr/bin/novix_run
chmod +x $pkgdir/usr/bin/novix_run
}
