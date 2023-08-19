# Setting up a new Mac
Just a checklist of things to install when setting up a new laptop

## Install Command Line Tools for Xcode

```sh
xcode-select --install
```

## Install homebrew:

https://docs.brew.sh/Installation

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

## Install pyenv and pyenv-virtualenv

```sh
brew install pyenv
brew install pyenv-virtualenv
```

Add the following to `~/.zshrc`:
```
export PYENV_ROOT="$HOME/.pyenv"
command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

Restart shell and install first python (`pyenv install -l` to see versions):
```sh
pyenv install 3.10.12
```

## Setup SSH keys for github

```sh
ssh-keygen -t ed25519 -C "XXX@gmail.com"
pbcopy < ~/.ssh/id_ed25519.pub
```

Paste key into github settings on website

Add the following to `~/.ssh/config`:

```
Host github.com
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_ed25519
```
Add the key to the ssh-agent:
```
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

## Install Oh My Zsh!
https://github.com/ohmyzsh/ohmyzsh

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Install SPF13 for Vim

```sh
curl http://j.mp/spf13-vim3 -L -o - | sh
```

## Install VSCode

https://code.visualstudio.com/download

