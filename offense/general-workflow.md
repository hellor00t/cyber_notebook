# General Workflow

## Recon - Portscan

```
$ sudo masscan -p1-65535 -iL targets.list --max-rate 1800 -oG masscan.log
```



## Recon - Endpoints

```bash
$ ~/go/bin/gobuster dir -u 10.10.10.180 -w ~/tools/wordlists/SecLists/Discovery/Web-Content/common.txt
```

Ref: [https://book.hacktricks.xyz/](https://book.hacktricks.xyz/)

