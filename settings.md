---
title: oh-my-zsh 우분투 설치 & 플러그인 셋팅
description: 
published: true
date: 2022-04-16T16:17:41.256Z
tags: settings, shell, ubuntu, zsh
editor: markdown
dateCreated: 2022-04-15T15:48:09.502Z
---

mac, windows, linux 뭐든 쉘은 zsh이 취향입니다. shell을 이쁘게 해주며 편리한 기능을 추가 할 수 있습니다.

> 이 문서는 Windows 10 WSL ubuntu 20.04.4 LTS 기준으로 작성되었습니다. 아마도 Linux ubuntu에서도 큰 문제 없을 것입니다.
{.is-info}

## zsh install
```bash
sudo apt install zsh

zsh --version
# zsh 5.8 (x86_64-ubuntu-linux-gnu)

# 현재 사용중인 Shell
echo $SHELL
# /bin/bash

# 쉘 변경
chsh -s /usr/bin/zsh

# oh my zsh 설치, 테마, 플러그인
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

vi ~/.zshrc
# ZSH_THEME 변경, 
ZSH_THEME="agnoster"

# 적용
source ~/.zshrc
```

## Utilities
### command-line fuzzy finder
[fzf](https://github.com/junegunn/fzf#using-linux-package-managers)

```bash
sudo apt-get install fzf
# ~/.zshrc 플러그인 추가
plugins=(  fzf   )
```
### bat & fd
```bash
sudo apt install bat
# Set alias cat='batcat' in ~/.zsrhc

sudo apt install fd-find
ln -s $(which fdfind) ~/.local/bin/fd
# .zshrc 수정 
export PATH=$HOME/.local/bin:$PATH

```


### zsh plugins
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
# ~/.zshrc 플러그인 추가
plugins=(  zsh-autosuggestions zsh-syntax-highlighting   )

# Powerlever10K
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
# Set ZSH_THEME="powerlevel10k/powerlevel10k" in ~/.zshrc.
```

### exa v0.10.1
```bash
sudo apt install exa #  wsl ubuntu 20.04.4는 apt에 없다. 아래로 대체하자.
mkdir ~/exa
wget https://github.com/ogham/exa/releases/download/v0.10.1/exa-linux-x86_64-v0.10.1.zip
cd ~/exa
unzip exa-linux-x86_64-v0.10.1.zip
sudo mv ./bin/exa /usr/local/bin
sudo mv ./man/* /usr/share/man/man1/
cd ..
rm -rf exa

# 아이콘이 나오도록 nerd-fonts를 설치하자.
git clone --depth 1 https://github.com/ryanoasis/nerd-fonts
# powershell에서 윈도우에 fonts를 추가하자
cd nerd-fonts
./install.ps1

```