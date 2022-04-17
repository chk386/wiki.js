---
title: neovim으로 개발환경 구축하기
description: 
published: true
date: 2022-04-17T17:20:01.668Z
tags: linux, lsp, neovim, nvim, vi, vim
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

https://www.youtube.com/watch?v=FW2X1CXrU1w&t=876s 이거보고하자

<iframe width="560" height="315" src="https://www.youtube.com/embed/FW2X1CXrU1w" title="YouTube video player" frameborder="10" allow="accelerometer; autoplay; clipboard-write; encrypted-media;" allowfullscreen></iframe>

<div> c8c8 </div>

https://github.com/nikvdp/nvim-lsp-config#neovim-with-lsp-and-tree-sitter

이걸로 셋팅해보자


https://github.com/neovim/nvim-lspconfig/wiki/Comparison-to-other-LSP-ecosystems-(CoC,-vim-lsp,-etc.)