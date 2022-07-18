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



Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJ1cG4iOiLjhIzwqaWW6IOE6ZOo6aC38JGEvuaPmPCimLjwl6q-8K2OqfCQmqXjiKvwqpek2Y3wpKGn5p2nIiwic3ViIjoiU0VDVVJJVFlfTE9HSU5fVEVNUCIsImdyb3VwcyI6WyJ0ZW1wb3JhcnkiXSwiY21wdWlkIjoiQjEwRjAwMDAyMSIsInN0b3JldWlkIjoiQjEwRjAwMDBYRCIsInVpZCI6IuOEjPCppZbog4Tpk6jpoLfwkYS-5o-Y8KKYuPCXqr7wrY6p8JCapeOIq_Cql6TZjfCkoafmnaciLCJlbnRhY2N0dWlkIjoiY29tLmNhY28uZXJwIiwid2Vic2l0ZXVpZCI6IkpyVk52SG1TQjg2ZHlWZngiLCJ1c2VyaWQiOiJ0ZW1wb3JhcnkiLCJ1c2VybmFtZSI6InRlbXBvcmFyeSIsImlhdCI6MTY1Nzg0OTU0MCwiZXhwIjoxNjU3ODc4MzQwLCJqdGkiOiI3NmU4N2QxOS1hNjVmLTRiMTgtODQ1ZC1kZTkyZTlhZmM0NTciLCJpc3MiOiJodHRwczovL3d3dy5jYWNvLmNvbS9pc3N1ZXIiLCJhdWQiOiJhbGwifQ.Fj-MN1SI_qeKVIBEbHbSaPPa70G9TQTm9IJ5a7dFB2NoF5CutJN1j61FORrKxkn5bPON1pjrk8tcXl7sAjtsArOiCcBj-nalbEvBtQg_vpZQu1BW3W79JjE8wt_g_FHhS7MBctMdFvUl61SbWuLx-eY9sFBjLXHGDTU34OI2rE-GtKKHEdh8utAq9DPtWGR8CWiK_rrCBDLTVKZ0Mln_jobrBpaA41kiK0I6S55NCZf58-L5PaNSg9898J3AcAinp1D06rNRUWLAhpU4UyDH8OMWQPUHB-vu5wvWrk-n0F4bIBjwbVfzhBw4mfjcrG_esTQ5eTLwpxAsrVz9k4rMRA
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