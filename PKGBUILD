# Maintainer: Jason Go <jasongo@jasongo.net>

pkgname=specify-cli
pkgver=0.4.2
pkgrel=2
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
optdepends=(
  'claude-code: Supported Agent'
  'codebuddy-cli: Supported Agent'
  'cursor-ide: Supported Agent, IDE-based'
  'gemini-cli: Supported Agent'
  'git-credential-manager-bin: For issues with Git authentication'
  'iflow-cli: Supported Agent'
  'kilocode-cli-bin: Supported Agent, IDE-based'
  'kimi-cli: Supported Agent'
  'kiro-cli: Supported Agent'
  'mistral-vibe: Supported Agent'
  'openai-codex: Supported Agent'
  'opencode: Supported Agent'
  'qodercli-bin: Suported Agent'
  'pi-coding-agent: Supported Agent'
  'qwen-code: Supported Agent'
  'shai: Supported Agent'
  'tabnine: Supported Agent'
  'visual-studio-code-bin: Visual Studio Code'
  'windsurf: Supported Agent, IDE-based'
)
options=(!debug)
source=("git+$url.git#tag=v$pkgver")
b2sums=('2ddb71f4f252e8493357ab6f45667ce96f3cb06a36afcc920fa7d23c49b422e0a1be3323ed476ae50aaf8dd4e787db9cd70bd2155503bbc7a7be7edaad393fc5')

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
