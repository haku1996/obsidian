---
date: 2022-06-28
modified: 2022-07-14
---
## Metadata
up:: [[sqlmap]]

---
## Info
```ad-info
title:看這個再去翻原文比較好找
```
---
# ParaNote
## Options

 **`-v`, verbose 詳細程度**
通常我都用 `-v 3`，看 payload

## Target 
直接連線目標資料庫 `-d <URL>`
`-d "mysql://user:password@192.168.75.128:3389/databasename"`
使用漏洞，需要有 query `-u <URL>`
`-u https://myphp/index?id=123`

## Request
指定HTTP方法 `--method=METHOD` 
`--method=GET`, `--method=POST`

用於POST時所帶的參數 `--data=DATA` 
`-u https://myphp/index?id=123 --data="id=admin&password=admin"`

參數分割字 `--param-del=PARAMD`
```bash
$ sqlmap -u https://myphp/index/post --method=POST --data="id=admin;password=admin" --param-del=";"
```
Cookie 操作也在此分類
`--user-agent=AGENT`, `--random-agent` 各式 user
`--force-ssl`
`--eval=CODE` 執行一段指定 python
## Optimization
`-o` 開啟 `--predict-output，--keep-alive， --null-connection`
`--threads=1~10` 多執行緒，預設為1，與 `--predict-output` 不相容
## Injection
 `-p TESTPARAM`
- [ ] 看不太懂
知道测试的参数，使用这个的话--level 参数就会失效。例： -p "user-agent,refere"
**跳過參數** `--skip=SKIP`
`--skip="id,uid"`
 **指定目標資料庫類型(版本也行)** `--dbms=DBMS` 
`--dbms="MySQL<5.0>"`
**資料庫登入**
`--dbms-cred="name:password"`
指定目標機作業系統 `--os=OS`
**指定前後綴** `--prefix=PREFIX`, `--suffix=SUFFIX` 
- [ ] 看不太懂
指定payload前缀，有时候我们猜到了服务端代码的闭合情况，需要使用这个来指定一下。例： -u "www.abc.com/index?id=1" -p id --prefix")" --suffix "and ('abc'='abc"

### `--tamper=TAMPER`
[[sqlmap.Temper]]
## Detection

`--smart` 滿好用的

**Both Default = 1**
`level 2`：cookie
`level 3`：user-agent，refere
`level 5`：host
`risk 2`：基于事件的测试
`risk 3`：or语句的测试
`risk 4`：update的测试

## Techniques
### `--technique=TECH` 指定使用的 sqli 類型
Default: All
B: Boolean
E: Error
U: Union
S: File System, OS
T: Time

**[[sqlmap#ALL Param]]** 有更多詳細指定參數

## Fingerprint `-f`, `--fingerprint`
## Enumeration 列舉
### `-a`, `--all` 全部
### `-b`, `--banner` 拿回資料庫系統 (DBMS) 的 banner
### `--current-user`, `--current-db`, `--host-name`
### `--users`, `--passwords`, `--privileges`
### `--roles` 看看有什麼角色,
### `--dbs`, `--tables`, `--schema`, `--dump`, `--dump-all`
### `--D DB` 指定從某個資料庫
### `--T TBL` 指定某個表格
### `--sql-query=QUERY`, `--sql-shell`

## Brute force

## User-defined function injection

## File system access

## Operating system access

## Windows registry access

## General


# 待整理


' and '1'='1
' and '1'='2

-   --safe-url: 隔一会就访问一下的安全URL
-   --safe-post: 访问安全URL时携带的POST数据
-   --safe-req: 从文件中载入安全HTTP请求
-   --safe-freq: 每次测试请求之后都会访问一下的安全URL


AND boolean based found reflective values
![[2022-07-07_12-28.png]]