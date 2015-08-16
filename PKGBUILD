# Maintainer: Adrián Pérez de Castro <aperez@igalia.com>
pkgname=mitro-cli
pkgver=0.1.3
pkgrel=2
pkgdesc="Manage your Mitro passwords from a command line interface"
arch=('i686' 'x86_64' 'arm')
url='https://github.com/ruyadorno/mitro-cli'
license='MIT/X11'
depends=('nodejs')
builddepends=('python2')
optdepends=()
source=("http://registry.npmjs.org/${pkgname}/-/${pkgname}-${pkgver}.tgz")
noextract=("${pkgname}-${pkgver}.tgz")
sha512sums=('6ff7142c6ff775c33963587ec09672d380a5611da86c22ff5a43fda749e23526e96ee0942b63c3de8d6b0ee0542b09875385e253e4935b1b6aff26dd4950a359')

package() {
	export PYTHON='python2'
	cd "${srcdir}"
	local _npmdir="${pkgdir}/usr/lib/node_modules/"
	install -m755 -d "${_npmdir}"
	cd "${_npmdir}"
	npm install -g --prefix "${pkgdir}/usr" "${pkgname}@${pkgver}"
	chown -R root.root "${pkgdir}"
}
