# Maintainer:  Spotlight <spotlight@joscomputing.space>

actualname=libunistring
pkgname=ppc-$actualname
pkgver=0.9.10
pkgrel=4
pkgdesc='Library for manipulating Unicode strings and C strings'
url='https://www.gnu.org/software/libunistring/'
arch=(any)
license=(GPL)
source=(https://ftp.gnu.org/gnu/$actualname/${actualname}-${pkgver}.tar.xz{,.sig})
validpgpkeys=('462225C3B46F34879FC8496CD605848ED7E69871') # Daiki Ueno <ueno@unixuser.org>
sha256sums=('eb8fb2c3e4b6e2d336608377050892b54c3c983b646c561836550863003c05d7'
            'SKIP')
b2sums=('25d162d9d510cc35ad4209acceb9b06bcc0553b8ce56e94f8df12c4df64d91abfc4a9e15b50b5c8d5b9672939305a394a7e83f1892258defb7ae5ac2ccf79dfb'
        'SKIP')

build() {
  source ${DEVKITPRO}/ppcvars.sh

  cd $actualname-$pkgver
  ./configure --prefix="${PORTLIBS_PREFIX}" --host=powerpc-eabi \
    --disable-shared --enable-static
  make
}

package() {
  source ${DEVKITPRO}/ppcvars.sh

  make -C $actualname-$pkgver DESTDIR="$pkgdir" install
}
