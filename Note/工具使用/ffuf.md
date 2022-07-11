---
parrent: ['999 工具地圖']
date: 2022-07-11
modified: 2022-07-11
---
```ad-info
title: 在 URL, headers, POST data 裡的任何使用 關鍵字"FUZZ"定義測試 

A Web Fuzzer by Golang
[Github: ffuf/ffuf](https://github.com/ffuf/ffuf)
[Doc](https://codingo.io/tools/ffuf/bounty/2020/09/17/everything-you-need-to-know-about-ffuf.html)
字典 Wordlists [Github: danielmiessler/SecLists](https://github.com/danielmiessler/SecLists/)
```
## Usage
```
```
![[Pasted image 20220711101454.png]]
### Official Usage Example
```sh
# fuzz, match 全部的狀態碼，過濾掉 size=42 的 response，詳細且上色
$ ffuf -w wordlist.txt -u https://example.org/FUZZ -mc all -fs 42 -c -v

# fuzz Header:Host，並只要 status code:200 的 response
$ ffuf -w hosts.txt -u https://example.org/ -H "Host: FUZZ" -mc 200

# fuzz 指定使用 POST，帶指定 HEADERS，FUZZ 在 name 上，過濾掉含有 "error" 字元的 response
ffuf -w entries.txt -u https://example.org/ -X POST -H "Content-Type: application/json" -d '{"name": "FUZZ", "anotherkey": "anothervalue"}' -fr "error"

# Fuzz multiple locations. Match only responses reflecting the value of "VAL" keyword. Colored.
$ ffuf -w params.txt:PARAM -w values.txt:VAL -u https://example.org/?PARAM=VAL -mr "VAL" -c
```

## Note
### Basic
`-v` verbose 打開詳細模式
`-w /path/to/wordlist` 指定關鍵字與參數，還可以用分號分開指定`'/path/to/wordlist:KEYWORD'`
`-u https://target/FuzzTest` 指定路徑，不用引號


rq = request, r = response
* **FILTER OPTIONS**:
		`-fc` filter r's HTTP status code
		`-fl` filter by r's 行數
		`-fr` regexp
		`-fs` filter r's size
		`-ft` Filter by number of milliseconds to the first response byte, either greater or less than. EG: >100 or <100
		`-fw` Filter by amount of words in response. Comma separated list of word counts and ranges
* **MATCHER OPTIONS:**
		`-mc` 預設: 200,204,301,302,307,401,403,405,500，`-mc 200` `-mc all` 只匹配200或全部都來
    `-ml` Match amount of lines in response
    `-mr` Match regexp
    `-ms` Match HTTP response size
    `-mt` Match how many milliseconds to the first response byte, either greater or less than. EG: >100 or <100
    `-mw` Match amount of words in response

```sh
#Typical directory discovery
$ ffuc -w /path/to/wordlists -u https://target/FUZZ

# GET parameter fuzzing
	# defining the `FUZZ` keyword as a part of the URL. This also assumes an response size of 4242 bytes for invalid GET parameter name.
$ ffuf -w /path/to/paramnames.txt -u https://target/script.php?FUZZ=test_value -fs 4242

	# 已知參數名稱。This example assumes a wrong parameter value returning HTTP response code 401.
$ ffuf -w /path/to/values.txt -u https://target/script.php?valid_name=FUZZ -fc 401


# POST data fuzzing
	# fuzzing only part of the POST request. We're again filtering out the 401 responses.
$ ffuf -w /path/to/postdata.txt -X POST -d "username=admin\&password=FUZZ" -u https://target/login.php -fc 401

# Maximum execution time
	# This stops **the entire** process after a given time (in seconds)
$ ffuf -w /path/to/wordlist -u https://target/FUZZ -maxtime 60
	# When working with recursion, you can control the maxtime **per job** using `-maxtime-job`. This will stop the current job after a given time (in seconds) and continue with the next one. New jobs are created when the recursion functionality detects a subdirectory.
$ ffuf -w /path/to/wordlist -u https://target/FUZZ -maxtime-job 60 -recursion -recursion-depth 2

It is also possible to combine both flags limiting the per job maximum execution time as well as the overall execution time. If you do not use recursion then both flags behave equally.
```
### ALL Param
*For A better Read-exp* **[Get to Github](https://github.com/ffuf/ffuf#usage)**
There are param usage and interactive mode usage.

```sh
Fuzz Faster U Fool - v1.3.0-dev

HTTP OPTIONS:

GENERAL OPTIONS:
-ac    Automatically calibrate filtering options (default: false)
-acc   Custom auto-calibration string. Can be used multiple times. Implies -ac
-c     彩色 output (default: false)

MATCHER OPTIONS:


FILTER OPTIONS:


INPUT OPTIONS:


OUTPUT OPTIONS:

```


```
EXAMPLE USAGE:
  Fuzz file paths from wordlist.txt, match all responses but filter out those with content-size 42.
  Colored, verbose output.
  
    ffuf -w wordlist.txt -u https://example.org/FUZZ -mc all -fs 42 -c -v

  Fuzz Host-header, match HTTP 200 responses.
    ffuf -w hosts.txt -u https://example.org/ -H "Host: FUZZ" -mc 200

  Fuzz POST JSON data. Match all responses not containing text "error".
    ffuf -w entries.txt -u https://example.org/ -X POST -H "Content-Type: application/json" \
      -d '{"name": "FUZZ", "anotherkey": "anothervalue"}' -fr "error"

  Fuzz multiple locations. Match only responses reflecting the value of "VAL" keyword. Colored.
    ffuf -w params.txt:PARAM -w values.txt:VAL -u https://example.org/?PARAM=VAL -mr "VAL" -c

  More information and examples: https://github.com/ffuf/ffuf

```

## Installation
```sh
$ sudo apt install ffuf
$ ffuf -v
```