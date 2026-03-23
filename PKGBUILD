# Maintainer: Jason Go <jasongo@jasongo.net>

pkgname=specify-cli
pkgver=0.4.0
pkgrel=1
pkgdesc='Bootstrap and manage Spec Kit projects'
arch=('x86_64' 'aarch64')
url='https://github.com/github/spec-kit'
license=('MIT')
depends=(
  'python'
  'python-click'
  'python-httpx'
  'python-json5'
  'python-packaging'
  'python-pathspec'
  'python-platformdirs'
  'python-pyyaml'
  'python-readchar'
  'python-rich'
  'python-truststore'
  'python-typer'
)
makedepends=(
  'git'
  'python-build'
  'python-installer'
  'python-hatchling'
  'python-wheel'
)
options=(!debug)
source=("git+$url.git#tag=v$pkgver")
b2sums=('576576b76de3874a6c486124959c4d59793e5e4227dbe12d86555f0bc3dc1a5b8c9ef00bc5365e2d24737bdd7002af9db604cc6a5ca30072e264ce674b6f7cb8')

build() {
  cd spec-kit
  python -m build --wheel --no-isolation
}

package() {
  cd spec-kit
  python -m installer --destdir="$pkgdir" dist/*.whl
  install -Dm644 -t "$pkgdir/usr/share/licenses/specify-cli/" LICENSE
  install -Dm644 -t "$pkgdir/usr/share/doc/specify-cli/" {AGENTS.md,CHANGELOG.md,CODE_OF_CONDUCT.md,CONTRIBUTING.md,README.md,SECURITY.md,SUPPORT.md}
}
