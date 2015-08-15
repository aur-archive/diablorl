# Maintainer: Perberos <perberos@gmail.com>
pkgname=diablorl
pkgver=0.5.0
_pkgver=050
pkgrel=3
pkgdesc="DiabloRL is a relatively simple Roguelike that attempts to present the game Diablo by Blizzard as a Roguelike: without graphics, turn based, and with perma-death, but otherwise using the same game mechanics."
url="http://diablo.chaosforge.org/"
arch=('i686' 'x86_64')
license=('freeware')
source=('http://diablo.chaosforge.org/file_download/12/diablorl-linux-i386-050.tar.gz'
        'diablorl.sh')
md5sums=('eb1e0ceefd73af6eac8de8d7b4429f2a'
         'SKIP')
depends=('libx11')
install=diablorl.install

if [[ $CARCH == x86_64 ]]; then
  source[0]='http://diablo.chaosforge.org/file_download/13/diablorl-linux-x64-050.tar.gz'
  md5sums[0]='894dc2324f16d2b9879c241472105531'
  zipdir="diablorl-linux-x64-$_pkgver"
else
  zipdir="diablorl-linux-i386-$_pkgver"
fi

build() {
  cd "$srcdir"
}

package() {
  cd "$srcdir"

  install -dm775 "${pkgdir}/opt/diablorl"
  chown -R root:games "${pkgdir}/opt/diablorl"

  install -D -m644 "${zipdir}/rl"              "${pkgdir}/opt/diablorl/rl"
  install -D -m644 "${zipdir}/diablorl.mpq"    "${pkgdir}/opt/diablorl/diablorl.mpq"
  install -D -m644 "${zipdir}/font10x18.png"   "${pkgdir}/opt/diablorl/font10x18.png"
  install -D -m644 "${zipdir}/config.lua"      "${pkgdir}/opt/diablorl/config.lua"
  install -D -m644 "${zipdir}/keybindings.lua" "${pkgdir}/opt/diablorl/keybindings.lua"
  install -D -m644 "${zipdir}/manual.txt"      "${pkgdir}/opt/diablorl/manual.txt"
  install -D -m644 "${zipdir}/readme.txt"      "${pkgdir}/opt/diablorl/readme.txt"
  install -D -m644 "${zipdir}/version.txt"     "${pkgdir}/opt/diablorl/version.txt"

  # shortchut
  install -D -m644 "${srcdir}/diablorl.sh"    "${pkgdir}/usr/bin/diablorl"

  chmod +x "${pkgdir}/usr/bin/diablorl"
  chmod +x "${pkgdir}/opt/diablorl/rl"
}
