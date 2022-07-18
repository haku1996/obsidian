---

date: 2022-07-15
modified: 2022-07-15
---
## Metadata
up:: [[graphQL]]
status:: init

---
## Info
```ad-info
title: =

[github](https://github.com/dolevf/graphw00f)
```
---
## Usage
```bash
$ cd /path/to/graphw00f
$ python3 main.py -h
$ python3 main.py -d -f -t https://www.caco.com.tw/ims030/ims/storeinventory/graphql/listbyd1r1storeitemno



Authorization : Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJ1cG4iOiLpurbllaXwo4Cw6Kac8Kq4h_CXnI_mvYfwoIG58KatjfCrtazwl4SD8JGareqZqvCjsIDikIIiLCJzdWIiOiJTRUNVUklUWV9MT0dJTl9URU1QIiwiZ3JvdXBzIjpbInRlbXBvcmFyeSJdLCJjbXB1aWQiOiJCMTBGMDAwMDIxIiwic3RvcmV1aWQiOiJCMTBGMDAwMFhEIiwidWlkIjoi6bq25ZWl8KOAsOimnPCquIfwl5yP5r2H8KCBufCmrY3wq7Ws8JeEg_CRmq3qmarwo7CA4pCCIiwiZW50YWNjdHVpZCI6ImNvbS5jYWNvLmVycCIsIndlYnNpdGV1aWQiOiJKclZOdkhtU0I4NmR5VmZ4IiwidXNlcmlkIjoidGVtcG9yYXJ5IiwidXNlcm5hbWUiOiJ0ZW1wb3JhcnkiLCJpYXQiOjE2NTgxMTI5NzUsImV4cCI6MTY1ODE0MTc3NSwianRpIjoiZTQ4YzNlNDUtYWNkMC00MDliLWE2NGEtOTUxY2JmMDI4YzMxIiwiaXNzIjoiaHR0cHM6Ly93d3cuY2Fjby5jb20vaXNzdWVyIiwiYXVkIjoiYWxsIn0.nOzSxyp6aKVrVx33aXQxI-_S5EdpB5X4Kt_wRXNAC26ZnMbFkgq9bsMucboZrGsjDtlHpfZJSxnamDM7N6sBgk86Yc7OJWuZbRaBc23_HZ4LjAK4Ccp8o1H0En02OqB3nyipocGZw3mK6W0nxJebn3nQstCcA-J0uG3wVuO88iuskQKSnVyF8HOx8lI20WUBxjJXdCNPTGrNuZjOUWsC67LLd_mrgMF1pWtF7kUzV8phMAafuxYsLBD6PCNFuMEBCyTMvOXK3EcGwf4UvgjtS-QFDFFSWJFyBczaLUUyp_-7DC0W0oFLf7tROm-G2Dmnn-aFXvV37QCZX0F36XSq9g
```
## Note
Header, Cookies 要到 /graphw00f/conf.py 改



### ALL Param
```txt
Usage: main.py -d -f -t http://example.com

Options:
  -h, --help            show this help message and exit
  -r, --noredirect      Do not follow redirections given by 3xx responses
  -t URL, --target=URL  target url with the path
  -f, --fingerprint     fingerprint mode
  -d, --detect          detect mode
  -T TIMEOUT, --timeout=TIMEOUT
                        Request timeout in seconds
  -o OUTPUT_FILE, --output-file=OUTPUT_FILE
                        Output results to a file (CSV)
  -l, --list            List all GraphQL technologies graphw00f is able to
                        detect
  -w WORDLIST, --wordlist=WORDLIST
                        Path to a list of custom GraphQL endpoints
  -v, --version         Print out the current version and exit.
```