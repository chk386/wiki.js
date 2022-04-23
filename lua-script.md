---
title: lua 설치 및 기본
description: 
published: true
date: 2022-04-23T15:56:39.406Z
tags: 
editor: markdown
dateCreated: 2022-04-23T15:56:39.406Z
---

# 설치
```bash
sudo apt install lua5.1
lua -v
# Lua 5.1.5  Copyright (C) 1994-2012 Lua.org, PUC-Rio


echo 'print("hello lua!")' >> hello.lua
lua hello.lua
```

# 다른 언어와 다른점 정리
```lua
a = 3 -- global
print(a)

if true then
	local a = 20
  print(a)
end

print(a)
```


