---
parrent: [[sqlmap]]
date: 2022-06-28
modified: 2022-07-08
---
- [[#Options|Options]]
	- [[#Options#-v, verbose 詳細程度|-v, verbose 詳細程度]]
- [[#Target|Target]]
	- [[#Target#`-d url` 直接連線目標資料庫|`-d url` 直接連線目標資料庫]]
	- [[#Target#`-u url` 使用漏洞，需要有 query|`-u url` 使用漏洞，需要有 query]]
- [[#Request|Request]]
- [[#Optimization|Optimization]]
- [[#Injection|Injection]]
	- [[#Injection#`-p TESTPARAM`|`-p TESTPARAM`]]
	- [[#Injection#`--skip=SKIP` 跳過參數|`--skip=SKIP` 跳過參數]]
	- [[#Injection#`--dbms=DBMS` 指定目標資料庫類型|`--dbms=DBMS` 指定目標資料庫類型]]
	- [[#Injection#`--os=OS`|`--os=OS`]]
	- [[#Injection#`--prefix=PREFIX`, `--suffix=SUFFIX` 指定前後綴|`--prefix=PREFIX`, `--suffix=SUFFIX` 指定前後綴]]
	- [[#Injection#`--tamper=TAMPER`|`--tamper=TAMPER`]]
- [[#Detection|Detection]]
	- [[#Detection#`--level=LEVEL`, `--risk=RISK` 這裡好像有錯|`--level=LEVEL`, `--risk=RISK` 這裡好像有錯]]
- [[#Techniques|Techniques]]
	- [[#Techniques#`--technique=TECH` 指定使用的 sqli 類型|`--technique=TECH` 指定使用的 sqli 類型]]
- [[#Fingerprint `-f`, `--fingerprint`|Fingerprint `-f`, `--fingerprint`]]
- [[#Enumeration 列舉|Enumeration 列舉]]
	- [[#Enumeration 列舉#`-a`, `--all` 全部|`-a`, `--all` 全部]]
	- [[#Enumeration 列舉#`-b`, `--banner` 拿回資料庫系統 (DBMS) 的 banner|`-b`, `--banner` 拿回資料庫系統 (DBMS) 的 banner]]
	- [[#Enumeration 列舉#`--current-user`, `--current-db`, `--host-name`|`--current-user`, `--current-db`, `--host-name`]]
	- [[#Enumeration 列舉#`--users`, `--passwords`, `--privileges`|`--users`, `--passwords`, `--privileges`]]
	- [[#Enumeration 列舉#`--roles` 看看有什麼角色,|`--roles` 看看有什麼角色,]]
	- [[#Enumeration 列舉#`--dbs`, `--tables`, `--schema`, `--dump`, `--dump-all`|`--dbs`, `--tables`, `--schema`, `--dump`, `--dump-all`]]
	- [[#Enumeration 列舉#`--D DB` 指定從某個資料庫|`--D DB` 指定從某個資料庫]]
	- [[#Enumeration 列舉#`--T TBL` 指定某個表格|`--T TBL` 指定某個表格]]
	- [[#Enumeration 列舉#`--sql-query=QUERY`, `--sql-shell`|`--sql-query=QUERY`, `--sql-shell`]]
- [[#Brute force|Brute force]]
- [[#User-defined function injection|User-defined function injection]]
- [[#File system access|File system access]]
- [[#Operating system access|Operating system access]]
- [[#Windows registry access|Windows registry access]]
- [[#General|General]]


# Basic
## Options

### -v, verbose 詳細程度
通常我都用 `-v 3`，看 payload

## Target 
### `-d url` 直接連線目標資料庫
`-d "mysql://user:password@192.168.75.128:3389/databasename"`
### `-u url` 使用漏洞，需要有 query
`-u https://myphp/index?id=123`

## Request
* `--method=METHOD` 指定方法 `--method=GET`, `--method=POST`
* `--data=DATA` 用於POST時所帶的參數 `-u https://myphp/index?id=123 --data="id=admin&password=admin"`
* `--param-del=PARAMD` 參數分割字 `-u https://myphp/index?id=123 --data="id=admin;password=admin" --param-del=";"`
* 同前二，相關 Cookie 操作也在此分類
* `--user-agent=AGENT`, `--random-agent` 各式 user
* `--force-ssl`
* `--eval=CODE` 執行一段指定 python
## Optimization
* `-o` 開啟 `--predict-output，--keep-alive， --null-connection`
* `--threads=1~10` 多執行緒，預設為1，與 `--predict-output` 不相容
## Injection
### `-p TESTPARAM`
- [ ] 看不太懂
知道测试的参数，使用这个的话--level 参数就会失效。例： -p "user-agent,refere"
### `--skip=SKIP` 跳過參數
`--skip="id,uid"`
### `--dbms=DBMS` 指定目標資料庫類型
`--dbms="MySQL<5.0>"`
資料庫認證
`--dbms-cred="name:password"`
### `--os=OS`
### `--prefix=PREFIX`, `--suffix=SUFFIX` 指定前後綴
- [ ] 看不太懂
指定payload前缀，有时候我们猜到了服务端代码的闭合情况，需要使用这个来指定一下。例： -u "www.abc.com/index?id=1" -p id --prefix")" --suffix "and ('abc'='abc"
### `--tamper=TAMPER`

## Detection

### `--level=LEVEL`, `--risk=RISK` 這裡好像有錯
`--level=1~5` `--risk=1~4` 
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

**DOC** 有更多詳細指定參數

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