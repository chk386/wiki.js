---
title: neovim으로 개발환경 구축하기
description: 
published: true
date: 2022-04-16T14:13:23.559Z
tags: linux, vi, vim, nvim, neovim, lsp
editor: markdown
dateCreated: 2022-04-16T14:13:23.559Z
---

무거운 IDE가 싫어서 vim으로 정착해보려고 합니다. 이 문서는 wsl ubuntu 20.04.4 LTS 버전 기준으로 작성되었습니다.

vim보다는 neovim이 더 많은 확장 기능을 제공하며 활발한 커뮤니티 활동이 보이기에 neovim을 기준으로 셋팅을 시작해보겠습니다.

## Install
```bash
# neovim v0.7.0 설치
mkdir nvim
cd nvim
wget https://github.com/neovim/neovim/releases/download/v0.7.0/nvim-linux64.deb
sudo apt install ./nvim-linux64.deb
cd ..
rm -rf nvim



```

