---
title: lua 설치 및 기본
description: 
published: true
date: 2022-04-23T17:28:50.509Z
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

# 문법 & 특징
## Global&Local Scope
[참고](https://www.youtube.com/watch?v=tiJlxyGumS0&t=133s)
```lua
a = 3 -- global
print(a)

if true then
	local a = 20
  print(a)
end

print(a)

-- 3
-- 20
-- 3
```

## Type
|Type			|Description			|
|---			|---							|
|nil			|null							|
|boolean	|true or false		|
|string		|문자열						|
|number		|Integer, Float		|
|function	|함수를 변수에 할당할수 있고 type이 function|
|table		|Array? Map? Group? 숫자, 문자, 함수, 다른 테이블 모두 포함 할수 있다.			|


```lua
local b = function() return "b" end
print(type(b))
-- function
```

## Operation
~~!=이 아니고~~ **~=**
~~||, &&, !이 아니고~~ **and, or, not**

## Etc
```lua
local a = {"hello", "world"}
print(a[1].."======="..a[2]) -- string concatenation
-- a[0]이 시작이 아니네?
print(#a) -- length
```

## Loop
```lua
a=1

while(a<10)
do
	print("a = ", a)
  a = a + 1
end

for i = 10,20,1 -- for(i=10, i<=20, i++)
do
	print(i)
end

```

## IF statement 
```lua
local a = 1 -- 1,2,3 바꿔서 실행해보자

if (a == 1)
then
	print(1)
else if (a == 2)
	then
  	print (2)
  else
  	print (3)
  end
end

```

## Function
```lua
local function say(text)
	local tmp = "say : "..text
  print(tmp)
  return tmp
end

say("hello") -- run this function
print(type(say)) -- show type
print(say) -- show function address 
```
> higher order function 특징을 가지고 있음

## string
```lua
str = "Shopby"

print(string.upper(str))
print(string.format("Date %02d/%02d/%04d", 24, 4, 2022))
print(string.rep("Shopby ", 10))
```

## array
```lua
ary = {1,2,3}

for i=1, #ary
do
	print(ary[i]) -- index가 1부터 시작, #ary는 ary.length와 같다
end
```

```lua
-- 10*10 2차 배열 선언
ary = {}; tmp = 1
for i=1, 10 
do
	ary[i] = {}
  for j=1, 10
  do
  	ary[i][j] = tmp
    tmp = tmp + 1
  end
end

for i=1, 10
do
	for j=1, 10
  do
  	print(ary[i][j])
  end
end
```

## Table
```lua
t = {"Shopby", key='value', "Platform", 1,2,3} -- type이 달라도 가능
print(t[2]) -- Platform
print(t.key) -- value

for k, v in pairs(t) 
do 
	print(k, v) 
end
```

## Module





