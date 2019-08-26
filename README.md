# osx init setup v201908

## osx common setting

- 音量 -> 消音
- キーボード -> 修飾キー -> Caps Lock→Control
- キーボード -> ショートカット -> Spotlight 表示　ctrl+enter
- トラックパッド -> その他ジェスチャー　全てチェック
- Dock -> 画面上の位置　左　サイズ小
- 時計 -> 日付の表示
- ソフトウェアアップデート -> Macを最新の状態に保つ

## app install

brewでinstallできるが、予め以下のappのみインストールしておく

- chrome -> ダウンロード/インストール
  - https://www.google.com/intl/ja_jp/chrome/
- google日本語入力 -> ダウンロード/インストール
  - https://www.google.co.jp/ime/
- iterm2 -> ダウンロード/インストール
  - https://www.iterm2.com/

## App Store Xcode setup

- AppStore -> Xcode -> ダウンロード/インストール

1度起動して同意しておく

## Xcode Command Line Tools setup

`xcode-select --install`

## homebrew setup

https://brew.sh

`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)”`

## anyenv setup

https://github.com/anyenv/anyenv

```
brew install anyenv
anyenv init
anyenv install —init
mkdir -p $(anyenv root)/plugins
git clone https://github.com/znz/anyenv-update.git $(anyenv root)/plugins/anyenv-update

echo 'eval "$(anyenv init -)"' >> ~/.zshrc
exec $SHELL -l

anyenv install rbenv
echo 'eval "$(ndenv init -)”' >> ~/.zshrc

anyenv install pyenv
echo 'eval "$(pyenv init -)"' >> ~/.zshrc

anyenv install nodenv
echo 'eval "$(nodenv init -)"' >> ~/.zshrc

anyenv install goenv
echo 'eval "$(goenv init -)"' >> ~/.zshrc

anyenv install jenv
echo 'eval "$(jenv init -)"' >> ~/.zshrc

anyenv install scalaenv
echo 'eval “$(scalaenv init -)"' >> ~/.zshrc

exec $SHELL -l
```

## prezto setup

```
brew install zsh zsh-completions
sudo vi /etc/shells
# add
/usr/local/bin/zsh
```

## zsh setup

`git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto”`

```
setopt EXTENDED_GLOB
for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
  ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
done
```

ターミナルを再起動しておく

## brewfile setup

`vim ~/Brewfile`

```
tap "homebrew/bundle"
tap "homebrew/cask"
tap "homebrew/cask-versions"
tap "homebrew/core"
tap "neovim/homebrew-neovim"
brew "anyenv"
brew "zsh"
brew "openssl"
brew "git"
brew "trash"
brew "wget"
brew "htop"
brew "tmux"
brew "lua"
brew "watch"
brew "coreutils"
brew "tig"
brew "jq"
brew "yq"
# brew "ag"
brew "ripgrep"
brew "kotlin"
brew "neovim"
cask "google-japanese-ime"
# cask "google-chrome"
# cask "iterm2"
cask "slack"
# cask "evernote"
# cask "docker"
cask "dropbox"
cask "atom"
cask "android-studio"
cask "visual-studio-code"
```

インストール

`brew bundle`


## vimrc and nvimrc setup

- 既存のvimrcがあるならそちらを利用する
- 面倒であれば以下からダウンロードする
- http://vim-bootstrap.com/

## docker setup

- brew installはせずに、公式からダウンロードしてインストールする
- https://hub.docker.com/editions/community/docker-ce-desktop-mac

