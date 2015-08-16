#Maintainer: max-k <max-k AT post DOT com>

pkgname=guzzle
_pkgname=Guzzle
pkgver=3.9.0
pkgrel=1
pkgdesc='Object-oriented PHP HTTP Client for PHP 5.3+'
arch=('any')
url="http://docs.guzzlephp.org/en/latest/"
license=('MIT')
depends=('php>=5.3.3' 'symfony-event_dispatcher>=2.1.0' 'pear-channel-guzzlephp')
makedepends=('php-pear>=1.4.6')
options=('!strip')
noextract=(${_pkgname}-${pkgver}.tgz)
source=(http://guzzlephp.org/pear/get/${_pkgname}-${pkgver}.tgz http://guzzlephp.org/pear/channel.xml)
md5sums=('6b721a11df2fe94dbc6e420192eedc08'
         'b4102c294299fd3e89a770c2ae2f3204')

package() {
  cd ${srcdir}
  local _PEARDIR="${pkgdir}/usr/share/pear"
  local _PEAROPTS="-D php_dir=${_PEARDIR} -D doc_dir=${_PEARDIR}/doc"
  local _PEAROPTS="${_PEAROPTS} -D test_dir=${_PEARDIR}/test"
  local _PEAROPTS="${_PEAROPTS} -D data_dir=${_PEARDIR}/data"
  pear ${_PEAROPTS} channel-add channel.xml
  pear ${_PEAROPTS} install -O -n ${_pkgname}-${pkgver}.tgz
  rm -r ${_PEARDIR}/{.channels,.depdb*,.filemap,.lock}
  rm -r ${_PEARDIR}/.registry/{.channel.__uri,.channel.*.php.net}
}

